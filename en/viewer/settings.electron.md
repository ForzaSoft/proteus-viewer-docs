# Settings

The Settings dialog lets you configure how the application behaves and how it connects to your PACS. Open it with the <BiCog /> **Settings** button in the toolbar.

Settings are organized into two tabs: **General** and **DICOM**. Click **Save** to apply your changes, or **Cancel** to discard them.

## General

General settings control overall application behavior.

- **Logs Level**: Controls how much detail the application records in its logs. Choose **Info** for normal use, **Debug** for detailed troubleshooting, or **Error** to record only failures.
- **Local DICOM Storage Path (read-only)**: Shows the folder where studies stored on this computer are kept. The location is fixed by the application and cannot be edited, but the text can be selected and copied.

## DICOM

The DICOM tab configures the local node and the remote PACS Locations used to query and retrieve studies.

### Local node

These settings identify this application on the DICOM network. Remote PACS must be configured to accept this node.

- **Local AE Title**: The Application Entity Title that identifies this node to remote PACS.
- **Local SCP Port**: The port this node listens on for incoming DICOM associations.

### PACS Locations

A **Location** is a remote PACS that the application can query and retrieve studies from. To connect to a new PACS you must add a Location with its connection details.

To add a Location:

1. Click **+ Location**.
2. Fill in the row:
   - **Name**: A label to identify the Location.
   - **IP**: The hostname or IP address of the remote PACS.
   - **Port**: The port the remote PACS listens on.
   - **AE Title**: The Application Entity Title of the remote PACS.
3. Click **Save**.

To remove a Location, click the <RiDeleteBin7Fill /> delete button on its row.

> **The remote PACS must support DICOM C-GET.** Studies are retrieved using the C-GET service. If the PACS only supports C-MOVE, retrieval will fail.
