# Toolbar

The toolbar provides quick access to layout, visualization, and image manipulation tools in MPR mode.

## Screen

- <RiGridFill /> **Grid**: Adjusts the viewport layout. Available configurations:
  - 2 Columns [2|1], 2 Columns [1|2], 3 Columns
  - 2 Rows [2|1], 2 Rows [1|2], 3 Rows

- <RiInformationLine /> **Display Info**: Toggles display of DICOM annotations. Its dropdown provides additional options:
  - **Show Annotations**: Shows or hides DICOM text overlaid on the images.
  - **Show Measures**: Shows or hides measurement annotations.

## Mouse Mode

- <RiStackFill /> **Browse Series**: Switches to Series mode, allowing navigation through slices.

- <RiContrastFill /> **Image Window**: Switches to Window/Level mode, allowing adjustment of brightness and contrast.

- <RiDragMove2Fill /> **Move**: Switches to Move mode, allowing repositioning of the image within the active viewport.

- <RiZoomInLine /> **Zoom**: Switches to Zoom mode, allowing adjustment of the magnification level.

- <RiRulerFill /> **Measures**: Switches to Measures mode, providing measurement tools. See the [Viewer Toolbar](../viewer/toolbar.md) for the full list of available measurement tools.

## Other Tools

- <RiArrowGoBackFill /> **Reset**: Resets the active viewport to its initial state (zoom, pan, window/level).

- <RiExpandHeightFill /> **Render Mode**: Sets the projection mode for the active viewport. Its dropdown provides the following options:
  - **MPR**: Standard multi-planar reconstruction.
  - **MIP**: Maximum Intensity Projection — highlights the highest-value voxels along each ray.
  - **MinIP**: Minimum Intensity Projection — highlights the lowest-value voxels along each ray.
  - **Avg**: Average Intensity Projection — averages all voxel values along each ray.

## Help

- **Help**: Opens the Help panel. Its dropdown also provides access to the keyboard **Shortcuts** reference for MPR mode.
