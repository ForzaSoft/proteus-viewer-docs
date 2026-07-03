# Key Objects (Selected Images)

Key Objects (KO) is a DICOM standard feature that allows you to mark and save significant images or frames for later review. These selected images help you quickly identify and navigate to the most important findings in a study.

## What are Key Objects?

Key Objects are special markers that highlight important images within a DICOM study. When you mark an image as a Key Object, it becomes part of a named group that can be easily accessed later. This is particularly useful for:

- Creating a collection of images for reporting
- Marking images for comparison or follow-up
- Organizing images for presentations or consultations

## Creating Key Object Groups

You can create one or more Key Object groups within a study. Each group has a unique name and can contain images from different series within the same study.

### To Mark an Image as a Key Object:

1. Navigate to the image you want to mark
2. Click the <RiKey2Fill /> **Toggle KO** button in the toolbar, or use its dropdown and select **Toggle KO with Windowing** to preserve the current window settings
3. Enter a title for your Key Object group (or select an existing group)
4. The image will be marked with a visual indicator

### Multiple Groups

You can organize your selected images into multiple groups, each with its own descriptive name. For example:
- "Main Findings"
- "Pre-treatment"
- "Follow-up Comparison"
- "Abnormalities"

Each group can contain images from different series within the study, making it easy to collect related findings across multiple imaging sequences.

## Managing Key Objects

### Editing Key Objects

Click the <RiEditFill /> **Edit KOs** button in the toolbar to open the Key Objects editor. In this editor, you can:

- Create new Key Object groups
- Rename existing groups
- Add or remove images from groups
- Delete entire groups
- Organize your selections

### Navigating Between Key Objects

Once you have marked images as Key Objects, you can quickly navigate between them using the <RiEditFill /> **KO Edition** dropdown:

- **Skip KO backward**: Navigate to the previous Key Object in the current group
- **Skip KO forward**: Navigate to the next Key Object in the current group

### Saving Key Objects

After creating or modifying your Key Object selections, click the <RiSave2Fill /> **Save KOs** button to save your changes. The Key Objects are stored as DICOM files with the KO modality.

## Viewing Key Objects

### In the Navigation Bar

When Key Objects are present in a study, each Key Object group appears as its own series at the top of the navigation bar, showing a thumbnail of its first key image, the group name, the number of key images and a colored <RiKey2Fill /> key icon. A selection circle marks the active group — the one **Toggle KO** adds images to; click the circle to switch groups.

Click a Key Object series to load its key images into the active viewport, where they can be browsed like a regular series. To manage the selections, use the <RiEditFill /> **KO Edition** button in the toolbar.

### Visual Indicators

Images that are part of a Key Object selection are marked with visual indicators in both the viewport and the navigation bar thumbnails, making them easy to identify at a glance.

### Exporting to Film Editor

You can easily send all images in a Key Object group to the Film Editor for printing or saving. Click the <RiCameraLine /> **Film Editor** button in the toolbar and select **KO Images**.

## Key Object Workflow

A typical workflow for using Key Objects:

1. **Review the study** and identify important images

2. **Mark images** using the <RiKey2Fill /> **Toggle KO** button (or **Toggle KO with Windowing** from its dropdown)

3. **Organize** images into named groups using the <RiEditFill /> Edit KOs editor

4. **Navigate** between selected images using the KO Back/Forward buttons

5. **Save** your selections with the <RiSave2Fill /> Save KOs button

6. **Review** your Key Objects by selecting groups from the navigation bar
