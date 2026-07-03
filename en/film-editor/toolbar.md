# Toolbar

The toolbar provides quick access to layout, editing, and printing tools in the Film Editor.

## Layout

- <RiGridFill /> **Templates**: Opens the template selector to choose a layout for the film. A list of configurable templates is available, each defining the number and arrangement of image cells on the page.

## Mouse Mode

- <BiSquareRounded /> **Selection**: Switches to Selection mode, allowing you to click and interact with individual image cells.

- <RiContrastFill /> **Image Window**: Switches to Window/Level mode, allowing adjustment of the brightness and contrast of the selected image.

- <RiDragMove2Fill /> **Move**: Switches to Move mode, allowing repositioning of the image within a cell.

- <RiZoomInLine /> **Zoom**: Switches to Zoom mode, allowing adjustment of the magnification level of the selected image.

- <RiDeleteBinLine /> **Delete**: Switches to Delete mode. Clicking an image cell removes its content.

## Other Tools

- <RiArrowGoBackFill /> **Reset**: Resets the selected image cell to its initial state (zoom, pan, window/level).

- <RiAnticlockwiseLine /> **Rotate**: Toggles the film orientation between Portrait and Landscape. The current orientation is shown in the status label at the top right of the toolbar.

- <BiCog /> **Printers**: Opens the printer selector. Two groups are available depending on configuration:
  - **PDF**: Browser-based paper sizes (A4, A3).
  - **DICOM**: Configured DICOM printers.

- <RiSave2Fill /> **Save** *(if save is enabled)*: Saves the current film to the PACS.

- <RiFilePdf2Fill /> **PDF** *(PDF printer only)*: Generates and downloads the film as a PDF file.

- <RiPrinterFill /> **Print**: Sends the film to the selected printer.
