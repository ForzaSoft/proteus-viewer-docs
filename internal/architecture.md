# Architecture: Deployment Modes and Sources

This viewer ships in three deployment modes. Each mode reaches DICOM data
through a different transport, so the codebase models the differences as
**Source** types (where data lives) and **StudyReq** kinds (how to fetch one
study). The mappings below are the contract every consumer should respect.

## Deployment modes

### 1. WADO client (web, attached to Protues PACS)

The viewer is served by, and authenticated against, a hospital PACS. It
fetches studies directly from that PACS over **WADO-RS** (HTTP). No native
backend, no intermediate router. Mode constant: `MODE.SESSION` /
`MODE.DEFAULT`.

### 2. Cloud viewer (web, S3 + Cloudflare)

The viewer is hosted on an S3 + Amplify deployment behind Cloudflare. Studies
are pulled directly from S3 (no PACS, no WADO). Auth and routing are handled
upstream; the viewer only receives a repository id + cloud token per study.
Mode constant: `MODE.CLOUD`.

### 3. Electron app (DICOM-only)

A desktop build that ships its own **native backend** (Rust napi addon, see
`native/backend`). The backend speaks raw DICOM (DIMSE) — it does **not**
expose WADO-RS. It owns:

- A local SQLite store of received studies (C-STORE SCP listens on port
  11112 by default).
- A persistent DICOM object Repository on disk under `userData/Repository`.
- The ability to act as a router/SCU to remote DICOM peers.

The renderer talks to the backend exclusively through the Electron preload
bridge (`window.backendAPI`, see `electron/preload.ts`). Mode constant:
`MODE.ELECTRON`.

## Sources

`Settings.sources` is a heterogeneous list typed as
`Source = WADOSource | DICOMSource | LocalSource`. They are discriminated
structurally (presence of `pacsUrl` / `ip` / `kind: 'local'`); type guards
`isWadoSource` / `isDicomSource` / `isLocalSource` live in
`src/contexts/commonExt.tsx`.

| Source        | Transport                   | Mode     | Identified by                             |
| ------------- | --------------------------- | -------- | ----------------------------------------- |
| `WADOSource`  | HTTP / WADO-RS              | Web      | `name` (free text)                        |
| `DICOMSource` | TCP / DIMSE via backend     | Electron | `name` (free text)                        |
| `LocalSource` | backend SQLite + filesystem | Electron | the sentinel string `'local'` (no `name`) |

`LocalSource` is a singleton — at most one entry per `Settings`. Electron
defaults inject it automatically (see `defSettings` and `readSettings`).

The S3 cloud path is **not** modeled as an entry in `sources`. The cloud
viewer receives its repository id and token per study via URL parameters
and constructs a `StudyReq` of kind `'s3'` directly (see
`src/contexts/viewer.tsx` / `mobile.tsx` / `film.tsx`).

## StudyReq kinds

Each study to be opened is described by a discriminated `StudyReq`. The four
kinds match the four ways the viewer can reach data, one per transport:

| Kind    | Used by mode | Carries                                   | Fetch path                                      |
| ------- | ------------ | ----------------------------------------- | ----------------------------------------------- |
| `wado`  | Web (PACS)   | `studyIuid`, `pacsToken`, `sourceName`    | WADO-RS through the named `WADOSource`          |
| `dicom` | Electron     | `studyIuid`, `sourceName`                 | Backend routes DIMSE to the named `DICOMSource` |
| `local` | Electron     | `studyIuid`                               | Backend reads its local SQLite + Repository     |
| `s3`    | Web (cloud)  | `studyIuid`, `repositoryId`, `cloudToken` | Direct S3 fetch via the cloud repository        |

See `src/study/types.ts` for the canonical definitions.

## How the cloud mode uses `StudyReq`

Unlike the other modes, the cloud viewer has no source dropdown and no
persisted config of where studies live — everything is encoded in URL params
and the network layer points at a single hosted endpoint
(`VITE_CLOUD_BASE_URL`). The lifecycle of an `s3` `StudyReq`:

1. **URL → `StudyReq[]`.** The viewer is opened with `?ids=…` where each id
   is `studyIuid:repositoryId`, plus a single `auth` token shared by every
   id. `ViewerProvider` (`src/contexts/viewer.tsx`) splits each pair and
   produces an `S3StudyReq`:

   ```ts
   { kind: 's3', studyIuid, repositoryId, cloudToken: params.auth }
   ```

   The same construction lives in `mobile.tsx` and `film.tsx` for those
   layouts. There is no fallback to `sources` — cloud mode never reads
   `Settings.sources`.

2. **Per-req fetch.** The navbar's load loop branches on `studyRef.kind`:
   for `'s3'` it calls `getCloudStudy(studyRef, hangingProtocols)` instead
   of the WADO/DICOM paths. `getCloudStudy` builds URLs as

   ```
   ${CLOUD_BASE_URL}/remote/${repositoryId}/studies/${studyIuid}
   ${CLOUD_BASE_URL}/remote/${repositoryId}/studies/${studyIuid}/series
   ```

   and sends `cloudToken` as a Bearer auth header (see `src/study/cloud.ts`).

3. **Per-instance fetch.** Series metadata is expanded via
   `getCloudInstances(iuids, repositoryId, cloudToken)`, hitting
   `…/studies/<uid>/series/<uid>/instances`. Each returned
   `SeriesMetadata` carries the same `S3StudyReq` back into the viewer, so
   downstream code (download, KO save, viewport rendering) can re-derive
   the cloud URL from the req alone — `pacsPath` is left empty for cloud
   instances because there is no WADO base path to substitute.

In short: in cloud mode, `StudyReq` is the only persistent identity for a
study. It both _opens_ the study (steps 1–2) and _follows_ the study around
the app for any subsequent operation that needs to call back to S3.
