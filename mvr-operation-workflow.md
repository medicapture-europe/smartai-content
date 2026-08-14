# MVR and MTR device operation workflow

Typical workflow of the MVR device operation:

- Start the device.
- Start a new Study by entering Patient Information, procedure description, and physician name.
- During the Active Study: capture images, record videos, and review recordings.
- Finish the Study, confirm the automatic export of recordings, and print the auto-generated report.
- Archive recordings: edit and annotate images and videos, generate and print reports, and send recordings to NAS or PACS.
- Change device Settings when necessary.
- Power Off the device.

## Start device

The typical start-up procedure is to supply power to the device - the device boots within 45 seconds when a new patient folder can be created. The front LED ring(s) enclosing the button(s) flash, and the MediCapture logo is displayed during the boot sequence. The device is expected to remain powered on (constant operation), allowing recordings to be taken instantaneously at any time. After booting, the Home screen is displayed, offering three options: Start, Archive, and Information. When User Accounts are enabled, you will need to enter correct credentials to get access to the device.

There is a Power icon in the top right corner of the Start screen that shows the Power menu:

- Shutdown: finish work with the device, recommended before turning on the main power.
- Reboot: restart the device.
- Logout: log out the current user, keep the device running, ready for the next user.
- Clean screen: Use this feature when you need to clean and disinfect the screen before the next procedure without turning off the device. It activates the screen mode that is intolerant of random touch actions, allowing physical screen cleaning without worrying about accidentally altering device mode or settings. After cleaning is complete, follow the on-screen instructions to connect 4 points in the sequence 1-2-3-4 to exit clean mode. Alternative function is to allow emergency reset to factory defaults, especially when passwords are lost and there is no way to login and enter Advanced Settings. In Cleaning mode, connect dots in the “8” shape: 1-4-2-3-1. The confirmation will pop up: RESET SETTINGS TO DEFAULTS. Are you sure? You may want to backup settings first. Buttons: Backup settings, Reset (it will activate reset to factory defaults).

## Start New Study

Tap the Start button to start a new Study.

The Study starts with entering patient data or selecting a patient from a worklist (DICOM feature activation is required). The desired data input type can be selected on the STUDY INFO SETTINGS screen: Off, Human, Veterinary.

While Study Info is not required (Off), "Auto Start new Study" option can be used. It starts new Study automatically after the device is ready after power on and video input is available. When Study is finished manually, it will not restart automatically until the next power on.

Optional worklist search is available when Study Info is set to Human or Veterinary. Worklist search feature require DICOM package to be activated. However, DEMO worklist is available at any time for training and education.

A new folder with a unique name is created at the enabled Storage, and all recordings for the current Study will be placed in this folder. Ensure the correct date, time, and time zone are set. We suggest checking the correct date and time before the Start of a Study and including this in the checklist to prepare for the surgical operation.

Settings are not available during active Study. Change Settings before starting Study.

## During the Active Study

### Preview and Select Video Source

A live image from an external camera is displayed during the active Study and is overlaid with control icons. The position of the icons in the live view can be arranged to your preferred location. Simply swipe the icons to the left or the right for a position change. If you do not wish to see the icons on your monitor, you can easily swipe them out of the visible monitor area. Swipe the icons with one finger when using a touchscreen monitor.

Use the VIDEO INPUT SETTING screen to select input sources, name them, and select the resolution for the USB camera.

A date and time text overlay can be enabled over the video signal, which will be captured and recorded in the video file by enabling the Stamp function and selecting the stamp position to any of the four corners of the screen. Patient information can be added to the text overlay (all, ID, Personal (name, date of birth), None); however, it is not recommended due to privacy concerns.

If more than one camera is connected, the image source can be toggled by tapping the Source icon.

Two video sources can be combined into one video PIP (Picture-In-Picture) or Split View style, enabling simultaneous recording and capture into a single video or image. Picture-In-Picture allows selecting the corner position and size (10%, 15%, 20%, 25%). The Split view combines two video inputs side by side.

Parallel recording records both inputs simultaneously, but in two separate files within the same folder. You can see only one input in the live view screen; the second input is recorded and captured as well.

The Area Of Interest (AOI) feature allows selecting a rectangular area of the input signal, so that only that area is captured in images and videos. To activate AOI, tap and hold on the live (real-time) screen until the AOI guide symbols appear. Adjust the AOI size by dragging a corner handle; move the AOI rectangle by dragging the move handle. Confirm the AOI selection by tapping “✓”. To cancel (deactivate) AOI, tap “X”.

AOI can be selected independently for each input. AOI is taken into account when inputs are combined using PIP or Split view.

### Capturing images

Tap the Photo icon to capture the image.

The LED on the power button is illuminated Blue when the device is ready to capture images. Goes out briefly when capturing images. A confirmation sound will be played at the current audio output. The sequential number of the current recording will be displayed next to the icon.

When Snapshot Preview is enabled, the captured image will be displayed in a window for a few seconds and then minimized to a thumbnail. Tap on the thumbnail to Review current recordings.

Freeze on capture allows for an unlimited full-screen freeze that requires a second tap (capture) to unfreeze.

To trigger image capture remotely, you can connect a standard foot switch or any “normally open” switch to the REMOTE port on the back of the device using the provided Split Remote Cable Adapter, for still and motion connections.

Images are captured at the natural input resolution and stored as JPEG or PNG. The PHOTO SETTINGS screen allows the selection of image format JPEG or PNG, and options like Freeze on capture, Snapshot preview, and optional Noise reduction.

JPEG option offers fast capture, good quality, small file size.

PNG option offers lossless quality, bigger file size, longer save time.

Freeze on capture option: Image freeze after taking snapshot. It doez not affect video recording. Press Capture again to unfreeze.

Snapshot preview option: Captured image will be shown for a few seconds (can be set from 1 to 10 seconds) in a corner of the main sceen (any corner from 4 can be selected).

Enabling both “Freeze on capture” and “Snapshot preview” will use full-screen freeze limited by “freeze seconds” (1 to 10).

Noise reduction option allows to reduce noise amount in the captured image using bilateral noie filtering. To understand the results of the noise reduction, select Demo mode when noise is reduced only for the right half of the image, leaving left half in original state. Capture several images in the actual conditions with Demo mode enabled, review captured results to decide on the noise filter usage.

### Recording Videos

Start the video recording by tapping the Video icon.

The LED on the power button will flash Blue to indicate that the recording is in progress. A confirmation sound will be played at the current audio output. The icon will flash while the video recording is in progress. The current recording time and the sequential number of the current recording will be displayed next to the icon.

Tap again to stop the video recording. A confirmation sound will be played at the current audio output.

Note: To trigger video recording remotely, another standard footswitch or "normally open" switch can be connected to the REMOTE port at the device's rear panel via the provided Y-split cable.

Images can be captured without interruption during the video recording. At the moment of image capture, a Tag will be created in the video that can be easily found later during Review.

Video recording can be paused and resumed. The pause function can be enabled in Video Settings. It is possible to Pause recording multiple times to eliminate unwanted parts. A Tag will be created in the video during the Pause. Tags are helpful during the Review to identify the different sections of the video. Video recording will pause automatically when the input signal is disrupted or disconnected, and resume when the input signal is restored.

Video recording will automatically stop when no free space remains. Long recordings are automatically split into 4GB files to keep the file size manageable. The process is seamless. When playing back a long recording using "continuous play" (a feature in most media players), there will be no gaps in playback.

By default, video is recorded without sound. Sound recording can be enabled, and an audio source (wired microphone, line in, USB microphone, or HDMI audio) can be selected in Audio Settings.

Videos are recorded as MP4 files. The VIDEO RECORDING QUALITY screen allows selection of the codec (H.264 or HEVC) and quality level (Normal for documentation or Super for presentations). HEVC (High Efficiency Video Coding) provides the same quality at half the file size as H.264 codec. HEVC is generally recommended, especially for 4K recordings. H.264 may provide wider compatibility with older video players, but with a larger file size.

The RECORDINGS OPTIONS screen allows setting:

- Video Time Limit (Off, 1 min, 2 min, 3 min, 5 min, 10 min); video recording stops after the time limit.

- Time Lapse Speed (Off, 4x, 12x, 60x, 300x, 900x, 3600x); recorded videos will play faster and take less disk space. Example: x60 will speed up video playback 60 times (1 hour of recording will be played in 1 minute). It is useful for recording complete, long-running operations or processes that are very slow or last for a very long time.

- Pause Function option: enable the Pause button and function during recording.

- On-screen Tally Light option: Shows a larger recording confirmation indicator. Once enabled and active, tap on the indicator to adjust its size.

- The "Hold to record" option controls how the remote video trigger works. When “Off”: pressing the remote video trigger toggles the start/stop of the video recording. When “On”: press and hold the remote trigger to record video and release to stop recording. This can be useful for integration with C-Arm, an X-ray-based medical imaging device, for example.

- Auto record: Off/On.
  Auto Recording ("Black Box" Mode) You can enable the Auto record function by tapping its slider in the RECORDINGS OPTIONS screen. When enabled, video recording begins automatically as soon as a new Study starts and a video input signal is detected.

- Recording Quality and Storage: Auto recording saves directly to the Internal Storage in the high-efficiency HEVC 720p30 format. If a video recording is triggered manually, it will override this default and record using your custom quality and storage settings.

- Operation and Control: All standard on-screen indicators and buttons behave normally. You can manually stop an auto-recording at any time by tapping the Video icon.

- Signal Disruption: If the camera signal is lost or disconnected, an auto-recording will immediately save and close the current file. It will automatically start a new recording file once the signal is restored. (This differs from manual recording, which simply pauses during signal loss).

- Unsupervised Recording: For continuous, hands-free documentation (ideal for "just in case" footage without manual file maintenance), enable both Auto record and Auto start of Study. Old recordings are automatically managed and deleted by the device's Storage Rules (e.g., deleting files older than 28 days or when less than 50GB of free space remains).

- Storage Capacity: Recording at HEVC 720p30 (approx. bitrate: 2 Mbps) produces about 0.9 GB of video per hour. With intense regular use, the 1TB internal drive can hold roughly 1 to 3 years of video recordings before the automatic storage rules need to delete old files.
  Note: The Auto start of Study feature only works when the Patient Information setting is turned "Off". This ensures that automatic, continuous black-box recordings do not contain identifiable personal data.

### Storage for recordings

There are three possible storage types for recordings: USB, Internal, or Network. Selection is available on the STORAGE SETTINGS screen. One or two Storage types can be enabled to save recordings. Maximum recorded video resolution (2160p, 1080p, 720p, images only) can be selected for each Storage type. Select “images only” to disable video recording for a certain Storage type. When the resolution of the input signal exceeds the maximum setting, recording will be scaled down. Set 720p for archiving or dataset collection; recording will be performed at 1280x720p30, providing good quality, minimal camera noise, and very long recording times.

Internal Storage is the most reliable destination for recordings, acting as a high-speed buffer. It is required for features like DICOM/PACS export. It is recommended to record to the Internal Storage only and later Send to NAS or copy to USB.

Network Storage (NAS): Allows recording directly to a shared folder on your hospital network via SMB/Samba. Record directly to the Network Storage when you have a fast, reliable LAN connection; use the Send to NAS feature otherwise. Access to the Network Storage can be set in Personal mode, where the same user’s credentials are used to log in to the device and access the NAS.

USB Storage: Supports portable flash drives, SSDs, and HDDs. Compatible file systems include FAT32, exFAT, and NTFS. Due to the wide variety of underlying technologies, USB versions, and the quality of external cables and connectors, it is recommended to test the actual recording speed of the desired USB Storage prior to use. Speed can be tested at the INFORMATION screen by tapping on the USB stick icon. The most reliable usage scenario of the USB Storage is to record to the Internal Storage and Copy to USB after Finish Study instead of the direct recording to USB Storage. It is possible to disable USB Storage when the use of the removable media is prohibited by security rules or regulations.

Note: When you stop a video recording, the capture of the video signal ends immediately, but the data may still be transferring to the USB storage, and the USB icon flashes to indicate that the write process is still in progress. Wait until the USB icon returns to its steady state before removing the USB flash drive or external hard drive. Removing media while the write indicator is active can cause file corruption, though our Automatic Video Repair (AVR) feature is designed to help protect and recover files in such instances.

Icons of the enabled Storages will be displayed during the active Study, with the number indicating the estimated recording time until Storage is full.

The Current Storage for the recordings is represented by one of the three distinctive icons: USB, Internal, Network Storage.

Available Storage capacity is displayed under the Storage icon as the remaining recording time or storage capacity. Toggle the display type by tapping on the icon. The remaining recording time is calculated based on the selected video recording quality and resolution.

It is recommended to check the remaining recording time right after the Start of the Study to ensure enough free storage space for the entire surgical Study.

### Checklist for the Active Study

Before the Study Starts:

- Ensure the correct date, time, and time zone are set.

- Select video inputs.

- Select image format and video recording quality.

- Select Storage for recordings.

- Set up web streaming if desired.
  Right after the Study Starts:

- Check the live video source quality.

- Capture and review testing images.

- Record and review a short testing video.

- Ensure correct Storage is selected for the recordings and that the remaining recording time is sufficient for the entire Study.

### Web streaming of the Study

Streaming allows external viewers to watch live studies with high quality and low latency using a standard web browser. When required, streaming can be enabled in the REMOTE ACCESS screen. The MVR operator has full control to allow a viewer to join the stream, see a list of connected viewers, and disconnect any viewer at any time.

## Finish the Study

Tap on the Back icon to Finish the current Study. The confirmation dialogue will show options to return to Study or Review recordings before the Study Finish. The finish of the Study may trigger the automatic export of recordings and the printing of the auto-generated report. The Review feature provides an opportunity to ensure that all necessary events have been captured and to edit, annotate, or delete recordings before the automatic export and reporting. The Archive function allows you to add more recordings to the Study after it has been closed. In Archive, navigate to the Study folder, open it, and tap the Append button.

## Available features in Archive:

- Change the active Storage by tapping the Storage icon in the top-right corner of the screen.

- Search for a Study by typing the patient's name or ID.

- Browse through the recorded Studies, select multiple Studies.

- Backup Studies from the Internal Storage to the USB drive.

- Copy selected studies to USB drive or NAS.

- Edit patient information.

- Report: automatically generate a report for the Study.

- Delete empty Studies.

- Tap the Study card to enter Review mode.

- In the Study Review mode:
  In the Study Review mode:
  
  - Scroll through the recordings and select one or multiple recordings for Report, Copy, Delete, or Send to NAS or Send to PACS.
  - Append: Add new images or videos to the current Study.
  - Notes: Add notes to the images that will be printed in the Report.
  - Report: selected images will be included in an automatically generated professional medical report, following the preset template, in PDF format, directly in the current Study folder.
  - Merge selected video fragments into a single video file.
  - Tap on the main preview to enter Edit mode for the selected image, video, or report.

- Image Edit mode allows you to manage and enhance captured still images before finalizing a study or archiving. The following features are available in Image Edit mode:
  Image Edit mode allows you to manage and enhance captured still images before finalizing a study or archiving. The following features are available in Image Edit mode:
  
  - Annotation: You can draw or add marks directly onto the image to highlight specific clinical findings.
  - Image Notes: You can add textual notes or comments to an image. These notes are saved with the image and can be automatically included in the final PDF report.
  - Zoom and Pan: You can zoom in on specific details and pan across the image.
  - Cropping (AOI): While the Area of Interest (AOI) is typically set during live capture, the system allows you to manage how the captured area is presented.
  - Saving as New: When you edit an image (such as adding annotations), the system saves it as a new file with an appended fragment number (e.g., I0001-001.jpg) to preserve the original, unaltered image.
  - Deletion: You can delete unwanted images directly from the review/edit screen.

- Video Edit mode provides a suite of tools for reviewing, trimming, splitting, and combining your medical recordings directly on the device. The following features are available in Video Edit mode:
  Video Edit mode provides a suite of tools for reviewing, trimming, splitting, and combining your medical recordings directly on the device. The following features are available in Video Edit mode:
  
  - Zoomed Playback and Panning.
  - Adjustable Playback Speed.
  - Frame-by-Frame Review.
  - Snapshots from Video.
  - Video trimming and splitting, multi-video merging; edited video is saved in a separate file.

- In Report Edit mode, you can finalize and customize the medical report before saving it as a PDF or printing it. The following features and customization options are available:
  In Report Edit mode, you can finalize and customize the medical report before saving it as a PDF or printing it. The following features and customization options are available:
  
  - Layout and view options: orientation & grid.
  
  - Reporting modes:
    Reporting modes:
    
    - Default: Includes all patient information, study details, and selected images.
    - Anonymize: Automatically hides all patient-identifiable information (Name, ID, DOB) for privacy-compliant sharing.
    - Only Images: Generates a clean layout containing only the captured visuals, without text.
  
  - Report Notes: You can add or edit clinical observations in the "Report Notes" section. This field supports Markdown formatting for professional text styling.
  
  - Branding and Sign-off:
    Branding and Sign-off:
    
    - Institutional Branding: The report automatically includes the Hospital Name, Department, and Location as configured in our system settings.
    
    - Custom Graphics:
      Custom Graphics:
      
      - Header Image: Displays your facility's logo at the top of the report.
      - End Image: Allows you to include a digital signature or an institutional stamp at the bottom of the document.
  
  - Finalization Actions:
    Finalization Actions:
    
    - Save to PDF: Generates a high-quality PDF file and saves it directly into the current study folder on the internal or USB storage.
    - Print: Sends the formatted report to a compatible connected printer.
    - Preview: Allows you to scroll through the pages of the report to verify the layout and content before finalizing.
  
  - Report customization is available in Settings ➤ Archive ➤ Report Settings. Available options are a custom header image (hospital logo), default Notes text, a custom footer text, and a footer image (signature). Text can be structured using Markdown formatting.
  
  - Note: To enable printing, ask your IT administrator to connect a network printer and configure the printer properties.

## DICOM package

DICOM package, enabled via the AKDICOM activation key, is designed to integrate MTR recorder seamlessly into the hospital’s imaging network. Key Features include:

- PACS Connectivity: Once activated, MTR can automatically or manually send captured images and videos directly to your Picture Archiving and Communication System (PACS) for long-term storage and review.
- Modality Worklist (MWL): This feature allows the recorder to retrieve patient schedules and procedure details directly from the hospital information system.
- Data Traceability: Every DICOM file generated includes essential metadata, such as the unique DeviceID, ensuring full traceability of the recorder used for each study.
- Offline Support: If the network is temporarily unavailable, MTR can temporarily store patient worklists and queue captures for upload once the connection is restored.
- HL7 Integration: The package also supports an HL7 message listener (port 2575) that can bridge hospital messages to the Modality Worklist, enabling a fully automated workflow.
  It is possible to evaluate DICOM features before purchasing the activation key. MTR includes a demo worklist and trial capabilities that let you test the workflow and network compatibility in the actual environment.

To begin using these features, enter the AKDICOM activation key in the system settings. Once the key is applied, you will need to configure your PACS server and Modality Worklist (MWL) server settings (such as AE Title, IP address, and Port) to establish communication with your hospital network.

Once the DICOM feature is activated with the AKDICOM key, it is a permanent license that never expires, ensuring continued integration for the life of the device.

## 3.11 System and Security

MTR recorder is designed with a robust security architecture and comprehensive system management features to ensure data integrity and compliance within medical environments.

### 3.11.1 Firmware Update Procedure

To ensure your MTR recorder remains secure and up to date, MediCapture regularly provides firmware updates on the website https://medicapture.com/portal/firmware/.

- Once the new version is available, download the update file and copy it to the root of the USB drive.
- Insert the USB drive into any available USB port on the MTR recorder.
- Go to Settings ➤ Advanced ➤ System ➤ Update & Default. Select Update firmware. Select the update file. The file will be copied to the device.
- Remove the USB drive and confirm the update action.
- The device will restart.
- The system will automatically detect the file, validate its digital signature to ensure it is an authentic, untampered update from MediCapture, and install it.
- Completion: Once the update is applied, the MTR recorder will reboot automatically. You can verify the new version number in the INFORMATION screen.

### 3.11.2 Automatic Video Repair Function

MTR device features an Automatic Video Repair Function, patented by MediCapture® (US patent 11,750,784 B2).

- Functionality: The system automatically detects and repairs corrupted MP4 video files. This occurs both when the device is powered on (scanning internal storage) and when a USB drive containing a damaged file is inserted.
- User Notification: The device provides a pop-up message to inform the user of the repair progress and success, ensuring the video is ready for playback.
- Corruption Causes: accidental removal of USB media while the write indicator is active, sudden power loss, or turning the device off during an active recording session.
  This feature is a core part of our commitment to data reliability in critical medical environments, ensuring that important procedural footage is preserved even in the event of technical or operational interruptions.

## Remote Operation and Control

The MTR offers flexible options for remotely managing recorders to suit different clinical and technical needs.

- It is possible to control the device directly from an Android tablet using our dedicated MVR Remote App, which lets you manage recordings, take snapshots, and review the study archive.
- For advanced system integration, MTR supports remote control via a comprehensive API over either a LAN (HTTP) or RS232 serial connection, enabling automated workflows for starting studies, capturing media, and managing PACS communication. Contact MediCapture for API documentation.
- Additionally, IT administrators can utilize the remote web configuration interface through a standard browser to securely manage device settings, network parameters, and system status from any workstation on the network.
- All remote services are disabled by default for security reasons. When necessary, enable and assign passwords for the remote access.
