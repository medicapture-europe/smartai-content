# Folder and File Naming Rules for MVR-series and MTR-series Video Recorders

## Folder Naming Rules

### Current Naming Rule (Stamp Folder Names: ON)

Folders are named using timestamps and device or patient information to ensure proper sorting and identification.

- **Without Patient ID**:  
  `YYYYMMDD_HHMMSS_DeviceID`  
  *Example*: `20240521_161633_20bd4b50`  
    
- **With Patient ID**:  
  `YYYYMMDD_HHMMSS_PatientID_DeviceID`  
  *Example*: `20240521_162707_AV35674_20bd4b50`

**Notes**:

- `YYYYMMDD_HHMMSS` helps in sorting folders chronologically.  
- `DeviceID` (8 hex digits) distinguishes recordings from different devices, which is crucial when multiple devices record to the same storage location.  
- Always verify the device's date and time before starting a study.

### Legacy Naming Rule (Stamp Folder Names: OFF)

Under the legacy system, folders were named sequentially:

- **Folder Names**: `CASE0001`, `CASE0002`, ..., up to `CASE9999`.  
- After `CASE9999`, the folder name resets to `CASE10000`, and while you can capture images and videos, they cannot be reviewed from the archive.  
- Subsequent studies after `CASE9999` will overwrite previous `CASE10000` contents.

**Recommendation**: Use the current naming rule with **Stamp Folder Names: ON** to avoid overwriting and ensure archive functionality.

## File Naming Rules

Each recording (image, video, or report) follows a specific naming convention for easy identification and management.

### File Name Structure

`PSSSS[–FFF].EXT`

- **P**: One-letter prefix indicating the type and source of the recording.  
- **SSSS**: Sequential Capture Number (`0001`–`9999`), reflecting the order of recordings.  
- **–FFF**: Optional Fragment Number (`001`–`999`), used for long recordings or edited files.  
- **EXT**: File extension (`jpg`, `png`, `mp4`, `pdf`, `dcm`).

### Prefix Definitions

- **I**: Image from the primary video channel.  
- **J**: Image from the secondary video channel.  
- **V**: Video from the primary video channel.  
- **W**: Video from the secondary video channel.  
- **R**: Imaging reports.

**Note**: The primary and secondary channels can be swapped during recording. Recordings are made from the primary channel unless parallel recording is enabled.

### Sequential Capture Number

- Increments with each recording, regardless of type.  
- Reflects the chronological order of all captures and recordings.  
- **Example Sequence**:  
  - `I0001.jpg`  
  - `V0002.mp4`  
  - `I0003.jpg`  
  - `R0004.pdf`

### Fragment Numbers

- **Purpose**:  
    
  - Created when a recording exceeds the file size limit (e.g., 4GB).  
  - Saving edits of images or videos.  
  - Capturing images from recorded videos during playback.


- **Format**: Appended to the original file name with a dash, e.g., `V0001–001.mp4`.

### Recording Formats

- **Image Formats**: JPEG (`.jpg`), PNG (`.png`), DICOM (`.dcm`).  
  - Default image format is JPEG.  
- **Video Formats**: MP4 (`.mp4`), DICOM (`.dcm`).  
- **Report Formats**: PDF (`.pdf`), DICOM (`.dcm`).

## Examples

### Capturing Images and Videos

**Example**: Capturing images before, during, and after video recordings.

1. **Capture an image**  
   → `I0001.jpg`  
     
2. **Start video recording**  
   → `V0002.mp4`  
     
3. **Capture images during recording**  
     
   - Image 1 → `I0003.jpg`  
   - Image 2 → `I0004.jpg`

   

4. **Stop video recording**  
     
5. **Capture another image**  
   → `I0005.jpg`

### Long Recordings (File Size Exceeds 4GB)

When a video recording exceeds 4GB, new fragment files are created automatically.

- **Example**:  
    
  - Original video file: `V0001.mp4`  
  - Fragments:  
    - `V0001–001.mp4`  
    - `V0001–002.mp4`  
    - ...

### Parallel Recording

Recording from two video sources simultaneously (primary and secondary channels).

**Example**:

1. **Start parallel recording**  
     
   - Primary channel (foreground) → `V0001.mp4`  
   - Secondary channel (background) → `W0001.mp4`

   

2. **Capture images during recording**  
     
   - Primary channel image → `I0002.jpg`  
   - Secondary channel image → `J0002.jpg`

   

3. **Stop recording**  
     
4. **Switch channels**  
     
   - Secondary becomes primary, and vice versa.

   

5. **Start new recording**  
     
   - New primary channel → `V0003.mp4`  
   - New secondary channel → `W0003.mp4`

### Appending to Closed Studies

Add additional recordings to an existing study via the Archive.

**Example**:

- **Existing Files**: `I0001.jpg`, `V0002.mp4`, `I0003.jpg`  
- **Append Actions**:  
  1. Capture image → `I0004.jpg`  
  2. Start recording → `V0005.mp4`  
  3. Stop recording

### Editing Images and Videos

Edited files are saved with fragment numbers to preserve the original files.

**Example**:

1. **Edit an image (`I0001.jpg`)**  
     
   - Save edited image → `I0001–001.jpg`

   

2. **Edit the edited image**  
     
   - Save as → `I0001–002.jpg`

   

3. **Capture image from video (`V0002.mp4`)**  
     
   - Saved image → `I0002–001.jpg`

   

4. **Save a video clip from original video**  
     
   - New clip → `V0002–002.mp4`

### Generating PDF Reports

Reports are integrated into the study sequence with the prefix `R`.

**Example**:

1. **Generate a report**  
   → `R0004.pdf`  
     
2. **Append to study and capture image**  
     
   - New image → `I0005.jpg`

   

3. **Generate another report**  
   → `R0006.pdf`

## Archiving and Copying

### Copying Options

- **As PNG/MP4/JPG**: Original file formats.  
- **As DICOM (`.dcm`)**: Converts files to DICOM format during copy.

### Copying to USB or NAS

- **Folder Naming During Copy**:  
    
  - If copying multiple times, a timestamp is appended to the folder name to prevent overwriting.  
  - *Example*: `CASE0001–202405221435`


- **File System Considerations**:  
    
  - For USB drives, use NTFS to support long folder names and large files.  
  - FAT32 may not support long names and large files (\>4GB).

**Example**: Copying as DICOM to USB

- **Original Folder**: `CASE0001` with `I0001.jpg`, `V0002.mp4`  
- **After Copy**:  
  - USB:  
    - `CASE0001/I0001.dcm`  
    - `V0002.dcm`

**Example**: Copying as PNG/MP4/JPG to NAS with Stamp Folder Names ON

- **Original Folder**: `20240522_152927_20bd4b50` with `I0001.png`, `V0002.mp4`  
- **After Copy**:  
  - NAS:  
    - `20240522_152927_20bd4b50/I0001.png`  
    - `V0002.mp4`

### Sending to NAS

Transfers the study folder directly to the NAS without changing file formats.

**Example**:

- **Original Folder**: `CASE0001` with `I0001.png`, `V0002.mp4`, `patient_info.json`  
- **After Sending to NAS**:  
  - NAS:  
    - `CASE0001/I0001.png`  
    - `V0002.mp4`  
    - `patient_info.json`

**Note**: The `patient_info.json` file may not appear in some cases, depending on system settings.

## Notes

- **Device Time Settings**: Ensure the device's date and time are correct before starting a study for accurate chronological sorting.  
- **Storage Compatibility**: Use appropriate file systems (e.g., NTFS) for external storage to handle long folder names and large file sizes.  
- **Sequential Number Limits**: The Sequential Capture Number ranges from `0001` to `9999`. Exceeding this limit may prevent further captures or recordings.  
- **Review Functionality**: Certain folder naming conventions or copying methods may affect the ability to review studies on the device.

