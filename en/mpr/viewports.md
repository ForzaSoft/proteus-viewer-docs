# Viewports

The MPR screen is divided into up to three viewports, each showing the volume reconstructed along a different anatomical plane.

## Planes

- **Axial**: Horizontal cross-sections (top-down view).
- **Sagittal**: Vertical cross-sections (side view).
- **Coronal**: Vertical cross-sections (front view).

## Layout

Use the <RiGridFill /> **Grid** button in the toolbar to choose how the three viewports are arranged on screen. The available layouts are:

- **2 Columns [2|1]** / **2 Columns [1|2]**: Two-column layouts with one larger and one smaller viewport.
- **3 Columns**: All three viewports displayed side by side.
- **2 Rows [2|1]** / **2 Rows [1|2]**: Two-row layouts with one larger and one smaller viewport.
- **3 Rows**: All three viewports stacked vertically.

## Maximizing a Viewport

Double-click any viewport to expand it to full screen. Double-click again to restore the multi-viewport layout.

## Render Mode

Each viewport has an independent render mode, set with the <RiExpandHeightFill /> **Render Mode** button in the toolbar while that viewport is active:

- **MPR**: Standard multi-planar reconstruction.
- **MIP**: Maximum Intensity Projection — shows the brightest voxels along each ray, useful for highlighting dense structures (e.g. vessels, bones).
- **MinIP**: Minimum Intensity Projection — shows the darkest voxels along each ray, useful for highlighting air-filled structures.
- **Avg**: Average Intensity Projection — averages all voxel values along each ray.
