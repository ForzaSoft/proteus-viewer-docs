# 3D Volume

The 3D Volume view renders a CT series as an interactive three-dimensional volume. Open it from the viewer with the <BsFillBadge3dFill /> **3D Volume** toolbar button — the selected series opens in a new window. The volume loads progressively; the footer shows the download progress until every slice is available.

## Toolbar

- <RiDownload2Fill /> **Download Image**: Saves the current 3D view as a PNG image.

- <RiInformationLine /> **Display Info** (**Shift + A**): Shows or hides the on-screen annotations.

### Mouse Modes

Select a tool and then click and drag over the volume:

- <LuRotate3D /> **3D Rotate** (**R**): Rotates the volume in three dimensions.

- <RiContrastFill /> **Image Window** (**W**): Adjusts the window to change which tissue densities are visible.

- <LuRotateCcw /> **Roll** (**T**): Rotates the volume around the viewing axis.

- <RiDragMove2Fill /> **Move** (**M**): Repositions the volume within the window.

- <RiZoomInLine /> **Zoom** (**Z**): Enlarges or reduces the volume.

### View

- <RiArrowGoBackFill /> **Reset** (**Shift + R**): Returns the volume to its initial orientation, position, zoom and window.

- <RiPaletteLine /> **3D Presets**: Selects the rendering preset, which controls the colors and opacity applied to the different tissue densities:
  - **Soft and Skin** (default): Soft tissue rendering with the skin surface.
  - **Bone and Skin**: Bone structures with a translucent skin surface.
  - **Airways**: Air-filled structures such as the trachea and bronchi.
  - **Bones**: Bone structures only.
  - **Shading**: Toggles surface shading for the current preset, adding depth to the rendering.
