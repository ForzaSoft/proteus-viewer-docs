# Volume loading pipeline — download to render

How a 3D volume series goes from metadata to an on-screen ray-marched render.
Each step is tagged with where it runs:

- **[FE]** frontend — main-thread React/TypeScript
- **[WK]** download web worker — TypeScript + the `worker` WASM crate
- **[BE]** backend — the `volume` WASM crate (Rust), runs on the **main thread**

The key design point: **downloading/decoding happens off the main thread (workers),
and uploading slices to the GPU is pumped in small batches** so the UI never freezes.
Slices stream into the volume texture *while the series is still downloading*.

---

## 1. Bring up the WASM module — [FE]

`src/contexts/volume.tsx`

- `init()` loads the `volume` WASM module, then `VolumeShared.create()` builds the
  shared state object. It's wrapped in an error-handling proxy and injected into a
  new `DownloadLink` (`window.Link`).
- The `VolumeShared` instance lives on the **main thread** for the whole session.

## 2. Fetch series metadata — [FE]

`src/contexts/volume.tsx` (effect keyed on the selected study/series)

- Depending on the source, calls `getSeriesMetadata` (WADO), `getLocalSeriesMetadata`,
  or `getRemoteTmpSeriesMetadata`. Result is a list of instance descriptors, each
  carrying its raw DICOM tags (`.raw`).

## 3. Register the series + plan the download — [FE] → [BE]

`planVolumeDownload()` in `src/contexts/volume.tsx`

- `shared.setInstances(json)` **[BE]** parses the metadata, sets `total_frames`
  (multiframe: frame count of the first instance; single-frame: instance count)
  and `instance_count`, and clears any previous frames.
- `shared.downloadPlan()` **[BE]** returns either:
  - `null` — download every instance (the common case), or
  - a subset of instance indices — only for **single-frame** series deeper than
    `MAX_VOLUME_DEPTH` (2048). Those extra slices would be dropped by depth
    subsampling at render time, so there's no point downloading them.
- If a subset is returned, the instance list is filtered and `setInstances` is
  called again with the reduced list (so `total_frames` matches what will arrive).

> Multiframe series are never subsampled at download time — their frames are
> decoded inside the shared worker, which MPR/Viewer also use. They are still
> subsampled at upload time in the backend (see step 7).

## 4. Start the download — [FE] → [WK]

`DownloadLink.download / downloadLocal` in `src/download/link.ts`

- Splits instances into `WORKERS_COUNT` (4) groups and posts a `FetchRequest`
  to each `link-worker.ts` worker. For volume/MPR the order is centre-outward, so
  the middle slices arrive first.
- A per-group callback is registered that forwards decoded frames to
  `shared.pushFrames(...)`.

## 5. Fetch + decode each instance — [WK]

`src/download/link-worker.ts` + `wasm/worker/src/lib.rs`

- Each worker fetches its instances (HTTP / S3 / native bridge) and decodes the
  pixel data in the `worker` WASM crate.
- Each decoded slice becomes a `VolumeFrame` carrying `frame_no` (its z-position),
  `pixels`, `rescale` (modality LUT slope/intercept), `size`, and format.
- Frames are batched and posted back to the main thread as `frames` messages.

## 6. Receive frames — [WK] → [BE]

`VolumeShared::push_frames` in `wasm/volume/src/shared.rs`

- Deserializes the batch and appends to the `frames` buffer. Frames may arrive in
  **any order** (4 workers, centre-outward); each frame knows its own `frame_no`.
- No GPU work happens here — that's driven by `pump` (step 8).

## 7. Attach the GPU — [FE] → [BE]

`Screen.tsx` effect → `VolumeShared::attach`

- As soon as the `<canvas>` mounts (well before the download finishes), the canvas
  drawing buffer is sized to display × DPR and `shared.attach(canvas)` is called.
- `attach` **[BE]** brings up wgpu (`Gpu::new`) and stores the device/queue/surface.
  Idempotent — safe to call once.

## 8. Pump slices into the texture — [FE] ↔ [BE]

`Screen.tsx` `pump()` loop → `VolumeShared::pump`

The frontend calls `shared.pump()` every ~100 ms. Each call **[BE]**:

1. **Lazily builds the `Renderer`** on the first pump that has both the GPU and at
   least one frame. `Renderer::new`:
   - reads the first frame's dimensions/format,
   - fits the volume to GPU limits — depth subsampled to `min(max_texture_dimension_3d, MAX_VOLUME_DEPTH)`, in-plane downscaled to respect the axis cap and `max_buffer_size`,
   - allocates the 3D `R16Float` texture **once**,
   - builds a `frame_no → z-layer` map (drops subsampled-out frames).
2. **Uploads up to `UPLOADS_PER_PUMP` (8) not-yet-resident slices.** Per slice:
   grayscale resize (if downscaling) → apply rescale to real Hounsfield values →
   encode as half-float → `write_texture` to its z-layer → flush.
3. **Redraws** once if anything was uploaded, so the volume visibly builds up.
4. Returns upload progress `0..100` (`uploaded / target_depth`).

Because each pump does a bounded amount of work and yields back to the event loop,
the **main thread stays responsive** and the overlay shows live progress. The loop
keeps pumping (draining any remaining frames) until progress reaches 100%.

## 9. Render — [BE]

`Gpu::draw_volume` in `wasm/volume/src/gpu.rs`

- Ray-marches the 3D texture from an orbit camera (a trackball quaternion centred
  on the cube) and composites each sample through the tissue transfer-function LUT.
- The Image Window (`window_center` / `window_width`) sets the HU range the LUT spans.

## 10. Interaction — [FE] → [BE]

After the first draw the `Renderer` stays alive, so these re-render without
re-uploading the volume:

- `rotate(dx, dy)` — trackball orbit (`Screen.tsx` pointer drag).
- `window(dx, dy)` — adjust Image Window centre/width.
- `setLut(points)` — rebuild the transfer-function LUT from the editor's control
  points (`ConfigBox.tsx`); the full LUT is interpolated backend-side.
- `resize(w, h)` — reconfigure the surface when the panel resizes the view.
- `reset()` — restore the initial camera + Image Window.

---

## Data-flow summary

```
[FE] metadata ─setInstances/downloadPlan→ [BE] total_frames, plan
[FE] download(filtered) ─postMessage→ [WK] fetch + decode ─frames→ [BE] push_frames (buffer)
[FE] attach(canvas) ─────────────────────────────────────────────→ [BE] Gpu::new
[FE] pump() every 100ms ─────────────────────────────────────────→ [BE] upload ≤8 slices + draw
                                                          repeat until 100%
```

## Tunables

- `MAX_VOLUME_DEPTH` (`shared.rs`) — z-slice cap; kept in sync with `downloadPlan`.
- `UPLOADS_PER_PUMP` (`shared.rs`) — slices uploaded per tick (responsiveness vs. speed).
- pump interval (`Screen.tsx`, ~100 ms) — how often the frontend drives uploads.
