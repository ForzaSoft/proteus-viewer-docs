# Toolbar

The toolbar provides quick access to various tools and functions for manipulating and analyzing DICOM images.

## Export

- <RiDownload2Fill /> **Export**: Exports the current DICOM study. The main button (or **ctrl + e**) exports the study in its original format. Its dropdown provides:
  - **DICOM**: Exports the study as DICOM files, in **Original** or **Uncompressed** format
  - **Images**: Opens a dialog to export images as JPEG, BMP or animated GIF (current image, series or study)
  - **Secondary Capture**: Saves a Secondary Capture of the current image to the PACS (**ctrl + shift + s**). Only available when logged in.

- <RiPrinterFill /> **Browser Print**: Prints the current image using the browser's print dialog (**ctrl + p**).

- <RiHistoryLine /> **Patient History**: Opens the patient history panel to view prior studies (**ctrl + h**). Only available when logged in.

## Screen

- <RiGridFill /> **Grid**: Adjusts the viewport layout to display multiple series simultaneously. Supports configurations up to a maximum of 16 viewports. Its dropdown provides additional options:
  - **Grid**: Reopens the grid layout picker.
  - **Split Series**: Spreads the series of the active group across the available panels.
  - **Series Group**: Submenu to select which series group is displayed.
  - **Close All Panels**: Clears every panel and returns to the single-panel layout.
  - **Grid presets**: A list of configurable fixed grid layouts.
  - **Full Screen mode**: Toggles full screen (**F11**).

- <RiLinkM /> **Sync Mode**: The synchronization feature lets you apply the same settings (slice position, zoom & pan, window) to the series of images opened in multiple panels.

  There are three synchronization modes available:
  - <RiLinkMAuto /> **Auto**: Automatically synchronizes settings across all panels
  - <RiLinkMManual /> **Manual**: Requires manual activation to synchronize settings
  - <RiLinkUnlinkM /> **Disabled**: Synchronization is turned off

  Its dropdown also provides options to control what is synchronized:
  - **Sync Slice Position**: Synchronizes the slice position across panels
  - **Sync Zoom and Pan**: Synchronizes zoom and pan settings across panels
  - **Sync Window Setting**: Synchronizes window/level settings across panels (disabled by default)

- <RiInformationLine /> **Display Info**: Toggles display of DICOM annotations. Its dropdown provides additional options:
  - **Show Annotations**: Shows or hides DICOM text information displayed on the images
  - **Show DICOM Overlay**: Shows or hides the DICOM overlay data
  - **Show Measures**: Shows or hides measurement annotations
  - **Show DICOM Tags**: Opens the DICOM tag viewer for the current image

## Mouse Mode

- <RiStackFill /> **Browse Series**: Switches to Series mode, allowing navigation through the series of images. Its dropdown provides additional navigation actions:
  - **Previous Image**: Go to the previous image in the series.
  - **Next Image**: Go to the next image in the series.
  - **Skip Images Backward**: Jump several images backward.
  - **Skip Images Forward**: Jump several images forward.

- <RiContrastFill /> **Image Window**: Switches to Window/Level mode, allowing adjustment of the Window and Level settings to optimize the visibility of specific tissue densities. Its dropdown provides preset window options:
  - **Default Window**: Restores the default window/level for the series.
  - **Full Dynamic**: Applies the full dynamic range of the image.
  - **Preset windows**: A list of configurable fixed window presets (e.g. Soft Tissue, Lung, Bone for CT).
  - **Negative**: Inverts the image (negative mode).

- <RiDragMove2Fill /> **Move**: Switches to Move mode, allowing repositioning of the image within the active viewport to adjust the viewing area.

- <RiZoomInLine /> **Zoom**: Switches to Zoom mode, allowing adjustment of the magnification level to enlarge or reduce the image size. Its dropdown provides preset zoom options:
  - **Fill Viewport**: Scales the image to fill the entire viewport.
  - **Preset zoom levels**: A list of configurable fixed zoom levels.

- <RiRulerFill /> **Measures**: Switches to Measures mode, providing measurement tools. The icon reflects the last selected tool:
  - <RiRulerFill /> **Length**: Measures the distance between two points.
  - <BiCircle /> **Ellipse**: Measures the area of an ellipse and calculates the ROI volume.
  - <TbAngle /> **Angle**: Measures the angle between two lines.
  - <TbAngle /> **Cobb Angle**: Measures the Cobb angle between two lines.
  - <RiArrowRightDownLine /> **Arrow**: Places a directional arrow annotation.
  - <RiText /> **Text**: Places a free text annotation.
  - <TbPolygon /> **Polygon**: Draws a polygon and measures its area.
  - <RiCrosshair2Line /> **Crosshair**: Places a crosshair annotation.
  - <RiDeleteBin7Fill /> **Delete**: Deletes the selected measurement.
  - <RiDeleteBin7Fill /> **Delete All**: Deletes all measurements in the current viewport.

## Other Tools

- <RiArrowGoBackFill /> **Reset**: Resets the series to its initial state (zoom, pan, window/level).

- <MdRotate90DegreesCcw /> **Transformations**: The main button rotates the image 90° counter-clockwise. Its dropdown provides:
  - **Rotate 90° CCW**: Rotates the image 90° counter-clockwise (**ctrl + [**).
  - **Rotate 90° CW**: Rotates the image 90° clockwise (**ctrl + ]**).
  - **Flip Horizontal**: Flips the image horizontally (**ctrl + shift + [**).
  - **Flip Vertical**: Flips the image vertically (**ctrl + shift + ]**).

- <BiCameraMovie /> **Play/Stop**: Toggles playback of the image sequence (Cine mode). You can speed up playback with the **arrow up + alt** key and slow down with the **arrow down + alt** key. Press the **spacebar** to toggle between play and pause.

## Key Objects (KO)

- <RiKey2Fill /> **Toggle KO**: Toggles Key Object (KO) selection for the current image. Its dropdown also includes:
  - **Toggle KO with Windowing**: Toggles KO selection preserving the current window settings.

- <RiEditFill /> **KO Edition**: Opens the Key Object editor for the current study. Its dropdown also includes:
  - **Skip KO Backward**: Navigates to the previous Key Object.
  - **Skip KO Forward**: Navigates to the next Key Object.

- <RiSave2Fill /> **Save KO**: Saves the modified Key Objects.

## Advanced

- <RiCameraLine /> **Film Editor** *(Logged in only)*: Opens a menu to send images to the Film Editor:
  - **Selected Image**: Sends the current image
  - **Series Batch**: Sends the entire series
  - **KO Images**: Sends Key Object images

- <RiBox3Fill /> **MPR**: Opens the Multi-Planar Reconstruction view. Its dropdown provides additional options:
  - **3D MPR**: Opens the full 3D MPR view.
  - **Coronal**: Generates an inline coronal reconstruction in the viewer.
  - **Sagittal**: Generates an inline sagittal reconstruction in the viewer.
  - **Axial**: Generates an inline axial reconstruction in the viewer.

- <BsFillBadge3dFill /> **3D Volume**: Opens the [3D volume rendering view](../volume/main.md) for the selected series.

## Narrow Windows

When the window is not wide enough to show every button, the toolbar collapses the tools into grouped menus. The Export, Browser Print, Patient History and Grid buttons stay visible, and every collapsed button keeps its own dropdown options inside its menu:

- <RiToolsFill /> **Tools**: Contains the mouse mode tools: Browse Series, Image Window, Move, Zoom and Measures.
- <RiEyeLine /> **View**: Contains Sync Mode, Display Info, Reset, Transformations and Play/Stop.
- **KO**: Contains the Key Object tools: Toggle KO, KO Edition and Save KO.
- <MdOpenInNew /> **Open**: Contains MPR, 3D Volume and the Film Editor.
