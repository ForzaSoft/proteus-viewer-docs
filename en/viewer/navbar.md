# Navigation Bar

The navigation bar (series preview bar) is located on the left side of the viewer and provides quick access to all studies, series, and images in your current session. It displays thumbnail previews and essential information for efficient navigation through DICOM data.

## Patient and Study Information

At the top of each study in the navigation bar, you'll find:

- **Patient Information**: Patient name and birth date
- **Study Details**: Study date and time, study description
- **Modality**: The imaging modality used (CT, MR, X-Ray, etc.)
- **Series Count**: Total number of series in the study

## Series Thumbnails

Each series is represented by a thumbnail image showing:

- **Preview Image**: A representative image from the series
- **Series Description**: The description of the series
- **Image Count**: Total number of images in the series (displayed as "frames")
- **Series Number**: The series number for identification

### Selecting a Series

Click on any series thumbnail to load it into the active viewport.

## Key Objects (KO)

When a study contains Key Objects, each Key Object group is shown as its own series at the top of the study, above the other series. Besides the usual series information, a Key Object series shows:

- **Preview Image**: A thumbnail of its first key image
- **Description**: The name of the Key Object group
- <RiKey2Fill /> **Key Icon**: A key with a distinct color per group
- **Image Count**: The number of key images in the group
- **Selection Circle**: When saving is enabled, a circle marks the active group — the one **Toggle KO** (**k**) adds images to. Click the circle to make a group the active one.

Click a Key Object series to load its key images into the active viewport, where they can be browsed like a regular series. When a study contains key images, its first Key Object series is loaded into the first viewport automatically.
