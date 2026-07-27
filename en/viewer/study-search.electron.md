# Study Search

The Study Search dialog is where studies are found and opened. Open it with the <RiDatabase2Fill /> **Study Search** button in the toolbar. The button has two scopes, and the same dialog is used for both:

- **Remote**: the PACS Locations configured in the Settings. This is what the button opens on a plain click.
- **Local**: the studies stored on this computer.

Clicking the button opens the Remote scope; use the arrow next to it to choose **Remote** or **Local**. The dialog title shows which scope is active, and switching scope clears the filters and the results.

## Filters

Both scopes share the same filters:

- **Source**: which node to query. On the Remote scope it lists the configured PACS Locations, and is empty when none is configured. On the Local scope it is fixed to **Local** and cannot be changed.
- **Modality**: check one or more modalities, or **All Modalities**.
- **Date range**: the Remote scope opens on **Today**, the Local scope on **All Dates**. Choose another preset range (Yesterday, Last Week, Last Month, Last Year), **Custom Date** for a single day, or **Custom Range** between two dates. The two date fields become editable only for the custom options.
- **Search field**: pick what to match on — Patient ID, Patient Name, Accession Number, Study Description, Referring Physician or Institution Name — and type the value. The text is matched as a partial value, so a fragment is enough.

Press **Search** (or Enter in the text field) to run the query, and **Clear** to reset every filter.

The Local scope lists every stored study as soon as the dialog opens, because the query is answered by the local database. The Remote scope waits for you to press **Search**: an unfiltered query against every PACS Location would be slow.

## Results

Matching studies are listed with patient, date, modalities, description and the source they came from. Select a study to list its series underneath.

To open a study:

- **Double-click** it, or select it and press **Open**.
- **Right-click** it for **Open study** (replaces what is open) or **Add study** (opens it alongside the current studies).

A study opened from a PACS Location is downloaded as you view it and is not kept after the application closes — see below for how to keep it.

## Saving studies to the local storage

- **Save to Local** (Remote scope): downloads the selected study straight into the local storage without opening it. A progress percentage is shown next to the button, and the study becomes available from the Local scope when it finishes.
- <RiSave3Fill /> **Save to Local** (toolbar): keeps the study you are currently viewing, when it came from a PACS Location or from files. The study stays open while it is saved.
- **Import** (Local scope): adds DICOM files from this computer to the local storage — **Import Files...** for one or more files, **Import Folder...** for a whole folder, which is scanned recursively. Files that are not DICOM are skipped. The study list refreshes when the import finishes.

Saving the same study twice is harmless: existing images are refreshed rather than duplicated.

## Deleting studies

**Delete** removes the selected study from the local storage, including its stored DICOM files. It is enabled only for studies that live there, and the action cannot be undone.

The folder holding these studies is shown, read-only, as **Local DICOM Storage Path (read-only)** in the [Settings](./settings.electron.md).
