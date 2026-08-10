#  MVR and MTR device operation workflow.

Typical workflow of the MVR device operation:

- Start the device.
- Start a new Study by entering Patient Information, procedure description, and physician name.
- During the Active Study: capture images, record videos, and review recordings.
- Finish the Study, confirm the automatic export of recordings, and print the auto-generated report.
- Archive recordings: edit and annotate images and videos, generate and print reports, and send recordings to NAS or PACS.
- Change device Settings when necessary.
- Power Off the device.

### Start device

The typical start-up procedure is to supply power to the device - the device boots within 45 seconds when a new patient folder can be created. The front LED ring(s) enclosing the button(s) flash, and the MediCapture logo is displayed during the boot sequence. The device is expected to remain powered on (constant operation), allowing recordings to be taken instantaneously at any time. After booting, the Home screen is displayed, offering three options: Start, Archive, and Information. When User Accounts are enabled, you will need to enter correct credentials to get access to the device.

There is a Power icon in the top right corner of the Start screen that shows the Power menu:

- Shutdown: finish work with the device, recommended before turning on the main power.
- Reboot: restart the device.
- Logout: log out the current user, keep the device running, ready for the next user.
- Clean screen: Use this feature when you need to clean and disinfect the screen before the next procedure without turning off the device. It activates the screen mode that is intolerant of random touch actions, allowing physical screen cleaning without worrying about accidentally altering device mode or settings. After cleaning is complete, follow the on-screen instructions to connect 4 points in the sequence 1-2-3-4 to exit clean mode. Alternative function is to allow emergency reset to factory defaults, especially when passwords are lost and there is no way to login and enter Advanced Settings. In Cleaning mode, connect dots in the “8” shape: 1-4-2-3-1. The confirmation will pop up: RESET SETTINGS TO DEFAULTS. Are you sure? You may want to backup settings first. Buttons: Backup settings, Reset (it will activate reset to factory defaults).

### Start New Study

Tap the Start button to start a new Study.

The Study starts with entering patient data or selecting a patient from a worklist (DICOM feature activation is required). The desired data input type can be selected on the STUDY INFO SETTINGS screen: Off, Human, Veterinary.

While Study Info is not required (Off), "Auto Start new Study" option can be used. It starts new Study automatically after the device is ready after power on and video input is available. When Study is finished manually, it will not restart automatically until the next power on.

Optional worklist search is available when Study Info is set to Human or Veterinary. Worklist search feature require DICOM package to be activated. However, DEMO worklist is available at any time for training and education.

A new folder with a unique name is created at the enabled Storage, and all recordings for the current Study will be placed in this folder. Ensure the correct date, time, and time zone are set. We suggest checking the correct date and time before the Start of a Study and including this in the checklist to prepare for the surgical operation.

Settings are not available during active Study. Change Settings before starting Study.

### During the Active Study

#### Preview and Select Video Source

A live image from an external camera is displayed during the active Study and is overlaid with control icons. The position of the icons in the live view can be arranged to your preferred location. Simply swipe the icons to the left or the right for a position change. If you do not wish to see the icons on your monitor, you can easily swipe them out of the visible monitor area. Swipe the icons with one finger when using a touchscreen monitor.

Use the VIDEO INPUT SETTING screen to select input sources, name them, and select the resolution for the USB camera.

A date and time text overlay can be enabled over the video signal, which will be captured and recorded in the video file by enabling the Stamp function and selecting the stamp position to any of the four corners of the screen. Patient information can be added to the text overlay (all, ID, Personal (name, date of birth), None); however, it is not recommended due to privacy concerns.

If more than one camera is connected, the image source can be toggled by tapping the Source icon.

Two video sources can be combined into one video PIP (Picture-In-Picture) or Split View style, enabling simultaneous recording and capture into a single video or image. Picture-In-Picture allows selecting the corner position and size (10%, 15%, 20%, 25%). The Split view combines two video inputs side by side.

Parallel recording records both inputs simultaneously, but in two separate files within the same folder. You can see only one input in the live view screen; the second input is recorded and captured as well.

The Area Of Interest (AOI) feature allows selecting a rectangular area of the input signal, so that only that area is captured in images and videos. To activate AOI, tap and hold on the live (real-time) screen until the AOI guide symbols appear. Adjust the AOI size by dragging a corner handle; move the AOI rectangle by dragging the move handle. Confirm the AOI selection by tapping “✓”. To cancel (deactivate) AOI, tap “X”.

AOI can be selected independently for each input. AOI is taken into account when inputs are combined using PIP or Split view.

#### Capturing images

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

#### Recording Videos

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

#### Storage for recordings

There are three possible storage types for recordings: USB, Internal, or Network. Selection is available on the STORAGE SETTINGS screen. One or two Storage types can be enabled to save recordings. Maximum recorded video resolution (2160p, 1080p, 720p, images only) can be selected for each Storage type. Select “images only” to disable video recording for a certain Storage type. When the resolution of the input signal exceeds the maximum setting, recording will be scaled down. Set 720p for archiving or dataset collection; recording will be performed at 1280x720p30, providing good quality, minimal camera noise, and very long recording times.

Internal Storage is the most reliable destination for recordings, acting as a high-speed buffer. It is required for features like DICOM/PACS export. It is recommended to record to the Internal Storage only and later Send to NAS or copy to USB.

Network Storage (NAS): Allows recording directly to a shared folder on your hospital network via SMB/Samba. Record directly to the Network Storage when you have a fast, reliable LAN connection; use the Send to NAS feature otherwise. Access to the Network Storage can be set in Personal mode, where the same user’s credentials are used to log in to the device and access the NAS.

USB Storage: Supports portable flash drives, SSDs, and HDDs. Compatible file systems include FAT32, exFAT, and NTFS. Due to the wide variety of underlying technologies, USB versions, and the quality of external cables and connectors, it is recommended to test the actual recording speed of the desired USB Storage prior to use. Speed can be tested at the INFORMATION screen by tapping on the USB stick icon. The most reliable usage scenario of the USB Storage is to record to the Internal Storage and Copy to USB after Finish Study instead of the direct recording to USB Storage. It is possible to disable USB Storage when the use of the removable media is prohibited by security rules or regulations.

Note: When you stop a video recording, the capture of the video signal ends immediately, but the data may still be transferring to the USB storage, and the USB icon flashes to indicate that the write process is still in progress. Wait until the USB icon returns to its steady state before removing the USB flash drive or external hard drive. Removing media while the write indicator is active can cause file corruption, though our Automatic Video Repair (AVR) feature is designed to help protect and recover files in such instances.

Icons of the enabled Storages will be displayed during the active Study, with the number indicating the estimated recording time until Storage is full.

The Current Storage for the recordings is represented by one of the three distinctive icons: USB, Internal, Network Storage.

Available Storage capacity is displayed under the Storage icon as the remaining recording time or storage capacity. Toggle the display type by tapping on the icon. The remaining recording time is calculated based on the selected video recording quality and resolution.

It is recommended to check the remaining recording time right after the Start of the Study to ensure enough free storage space for the entire surgical Study.

#### Checklist for the Active Study

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

#### Web streaming of the Study

Streaming allows external viewers to watch live studies with high quality and low latency using a standard web browser. When required, streaming can be enabled in the REMOTE ACCESS screen. The MVR operator has full control to allow a viewer to join the stream, see a list of connected viewers, and disconnect any viewer at any time.

### Finish the Study

Tap on the Back icon to Finish the current Study. The confirmation dialogue will show options to return to Study or Review recordings before the Study Finish. The finish of the Study may trigger the automatic export of recordings and the printing of the auto-generated report. The Review feature provides an opportunity to ensure that all necessary events have been captured and to edit, annotate, or delete recordings before the automatic export and reporting. The Archive function allows you to add more recordings to the Study after it has been closed. In Archive, navigate to the Study folder, open it, and tap the Append button.

### Available features in Archive:

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

### External Web Application

The External Apps feature lets you control external smart devices on your local network directly from the recorder's built-in web browser and acts as a shortcut to specific websites or web applications. It is designed to let medical professionals control devices such as:

- Video switch matrices
- Intelligent camera controllers
- Surgical light controllers
- Web-based help or guidance systems and others.
  To configure these applications, navigate to: Settings ➤ Advanced Settings ➤ Connections ➤ External apps. Toggle the "Enabled" slider. Tap the "+" icon to add a new app. You can specify the protocol (HTTP or HTTPS), the URL, or the IP address and port. You can select one application to be the "default home app," which will launch automatically when the device starts and a user logs in.

There is a default home web application running on the local host, http://localhost:3335, when enabled. This is a template web application, and it can be replaced with any custom web app. Create a custom web application, zip it, and copy it to a USB drive. Plug the USB drive into the device. Tap to edit the default home app in the EXTERNAL APPS screen. Tap the “Upload web” button and select the zip file from the USB drive. Your custom application will become a new home web app. Rules for creating web applications: must start with index.html; after unzipping, index.html should be in the root directory, not in any subfolder.

When enabled, app icons appear in a vertical scroll on the left side of the Start screen. Tapping an icon opens a browser window. These apps behave like browser tabs; if you close the window, the progress remains active in the background until you log out or restart the device.

### Utilizing Portrait Orientation

MTR series video recorders feature a versatile Portrait Orientation mode designed to optimize clinical workspaces and enhance procedural efficiency. By rotating the user interface 90 or 270 degrees, the display transforms into a vertical workstation, offering several key advantages:

- Dual View Functionality: This is a primary benefit where the screen is logically split. The top half displays the live camera feed in its native aspect ratio, while the bottom half provides access to the user interface, Archive browser, or external applications.
- Dual Camera Operation: You can display a secondary camera's live feed below the primary camera, enabling independent image capture and video recording for both sources simultaneously.
- Live Study with Archive Review: This allows you to review previous recordings as a reference during a live procedure. For example, you can have a looped playback of blood flow captured by a fluorescent camera on the bottom half while performing live surgery under visible light on the top half.
- Optimized for Medical Carts: Portrait orientation is ideal for space-constrained environments, allowing for a slimmer equipment profile on medical carts or integrated towers where horizontal desk space is limited.
- External App Integration: This mode is particularly powerful when combined with our External Apps feature. You can run third-party web applications—such as surgical light controls, video matrix switchers, or hospital-specific web portals—on the bottom half of the screen. This allows you to manage the operating room environment from a single vertical display without losing sight of the live video feed.
  To switch one of our MTR devices to portrait mode, navigate to the INFORMATION screen, tap Display settings, and select a screen rotation of 90° or 270°.

### DICOM package

DICOM package, enabled via the AKDICOM activation key, is designed to integrate MTR recorder seamlessly into the hospital’s imaging network. Key Features include:

- PACS Connectivity: Once activated, MTR can automatically or manually send captured images and videos directly to your Picture Archiving and Communication System (PACS) for long-term storage and review.
- Modality Worklist (MWL): This feature allows the recorder to retrieve patient schedules and procedure details directly from the hospital information system.
- Data Traceability: Every DICOM file generated includes essential metadata, such as the unique DeviceID, ensuring full traceability of the recorder used for each study.
- Offline Support: If the network is temporarily unavailable, MTR can temporarily store patient worklists and queue captures for upload once the connection is restored.
- HL7 Integration: The package also supports an HL7 message listener (port 2575) that can bridge hospital messages to the Modality Worklist, enabling a fully automated workflow.
  It is possible to evaluate DICOM features before purchasing the activation key. MTR includes a demo worklist and trial capabilities that let you test the workflow and network compatibility in the actual environment.

To begin using these features, enter the AKDICOM activation key in the system settings. Once the key is applied, you will need to configure your PACS server and Modality Worklist (MWL) server settings (such as AE Title, IP address, and Port) to establish communication with your hospital network.

Once the DICOM feature is activated with the AKDICOM key, it is a permanent license that never expires, ensuring continued integration for the life of the device.

### 3.11 System and Security

MTR recorder is designed with a robust security architecture and comprehensive system management features to ensure data integrity and compliance within medical environments.

#### 3.11.1 User Access Control (RBAC)

MTR recorder implements Role-Based Access Control (RBAC) to protect local recordings and network access.

- No Default Passwords: For maximum security, our products do not ship with a default password. Upon the first power-on or after a factory reset, the system requires the administrator to create a unique, secure password before any configuration can proceed.

- Roles:
  Roles:
  
  - Admin: Full access to all device features, including Advanced Settings (Network, Storage Rules, User Accounts, Audit Trail). No access is granted to the operating system.
  - User: Standard access to record, review, and document studies. Access to Advanced Settings is blocked.
  - Guest: Limited to reviewing the Archive and viewing live streams; no recording or system modification rights.

- Authentication Methods:
  Authentication Methods:
  
  - Local Accounts: Up to 20 local accounts can be managed directly on the device.
  - LDAP/LDAPS: Centralized authentication via Active Directory. It supports Offline Authentication (temporary caching credentials) to allow logins when the MTR recorder is on a mobile trolley disconnected from the network.

- "Break the Glass" Emergency Login: In urgent situations, an emergency study can be started without a login. This mode is restricted to recording only; the Archive and Settings remain protected.

#### 3.11.2 Password and Session Management

- Password Policies: Administrators can enforce password strength requirements and set renewal periods (from 1 week to 6 months).
- Inactivity Timeout: To prevent unauthorized access to an unattended device, the system can be set to automatically enter a password-protected screensaver after 1 to 60 minutes of inactivity.

#### 3.11.3 OS Protection and Malware Prevention

The MTR recorder uses a proprietary hardened operating system designed for maximum security:

- Kiosk Mode: The MTR recorder operates in a dedicated, full-screen kiosk environment. This ensures that the user is restricted to the medical recording interface, with no access to the underlying operating system desktop, system settings, or third-party applications.
- Direct Boot: The device is configured to boot directly into the MTR application, ensuring the system is ready for clinical use immediately upon power-on.
- No-Execute (noexec) Storage: To protect against external threats, MTR recorder mounts all connected external storage—including USB flash drives and NAS—with a noexec attribute. This ensures that even if a connected drive contains malware, viruses, or unauthorized scripts, the system is physically incapable of executing them.
- Closed System: There is no direct access to the OS, no "IT administrator" shell, and no ability to install third-party software.
- Read-Only Partitions: System partitions are read-only. The device boots fresh in "factory mode" every time, retaining only user-defined settings.
- Boot Security: The system uses an encrypted bootloader signed with a proprietary key, rejecting any unauthorized or unsigned firmware.
- Audit Trail: The MTR recorder maintains a log of the last 5,000 critical events and user actions for regulatory compliance.

#### 3.11.4 Network Security

- Services Off by Default: To minimize the attack surface and ensure a secure "out-of-the-box" experience, all network services (such as Remote Access, DICOM, and HL7) are turned off by default. They must be explicitly enabled and configured by an administrator.
- Remote Access: When enabled, it requires a unique password.
- NTP (Network Time Protocol): Automatically synchronizes the clock with hospital time servers. Accurate time-stamping is critical for security and medical records.

#### 3.11.5 Firmware Update Procedure

To ensure your MTR recorder remains secure and up to date, MediCapture regularly provides firmware updates on the website https://medicapture.com/portal/firmware/.

- Once the new version is available, download the update file and copy it to the root of the USB drive.
- Insert the USB drive into any available USB port on the MTR recorder.
- Go to Settings ➤ Advanced ➤ System ➤ Update & Default. Select Update firmware. Select the update file. The file will be copied to the device.
- Remove the USB drive and confirm the update action.
- The device will restart.
- The system will automatically detect the file, validate its digital signature to ensure it is an authentic, untampered update from MediCapture, and install it.
- Completion: Once the update is applied, the MTR recorder will reboot automatically. You can verify the new version number in the INFORMATION screen.

#### 3.11.6 Automatic Video Repair Function

MTR device features an Automatic Video Repair Function, patented by MediCapture® (US patent 11,750,784 B2).

- Functionality: The system automatically detects and repairs corrupted MP4 video files. This occurs both when the device is powered on (scanning internal storage) and when a USB drive containing a damaged file is inserted.
- User Notification: The device provides a pop-up message to inform the user of the repair progress and success, ensuring the video is ready for playback.
- Corruption Causes: accidental removal of USB media while the write indicator is active, sudden power loss, or turning the device off during an active recording session.
  This feature is a core part of our commitment to data reliability in critical medical environments, ensuring that important procedural footage is preserved even in the event of technical or operational interruptions.

### Remote Operation and Control

The MTR offers flexible options for remotely managing recorders to suit different clinical and technical needs.

- It is possible to control the device directly from an Android tablet using our dedicated MVR Remote App, which lets you manage recordings, take snapshots, and review the study archive.
- For advanced system integration, MTR supports remote control via a comprehensive API over either a LAN (HTTP) or RS232 serial connection, enabling automated workflows for starting studies, capturing media, and managing PACS communication. Contact MediCapture for API documentation.
- Additionally, IT administrators can utilize the remote web configuration interface through a standard browser to securely manage device settings, network parameters, and system status from any workstation on the network.
- All remote services are disabled by default for security reasons. When necessary, enable and assign passwords for the remote access.

### Structure of Settings:

Settings: Video/Audio, System, Archive, Advanced.

Video/Audio

- Video Input
  Video Input
  
  - Selecting and renaming Video Input 1 and Video Input 2.
  - Selecting the resolution of the USB cameras
  - aiScope model selection
  - Stamp function in pictures and videos: Off/On, stamp position, patient info to display in the stamp: None, Personal. ID, All.
  - Picture in Picture: Off/On, position, size: 10%, 15%, 20%, 25%.
  - Split view
  - Parallel recording.

- Recording Quality
  Recording Quality
  
  - Quality: Normal, Super.
  - Codec selection: H.264, HEVC.

- Recording Options
  Recording Options
  
  - Video Time Limit: Off, 1 min, 2 min, 3 min, 5 min, 10 min.
  - Time Lapse Speed: Off, 4x, 12x, 60x, 300x, 900x, 3600x.
  - Pause Function: Off/On.
  - On-Screen Tally Light (OTL): Off/On; adjust size by tapping on OTL when it is shown.
  - Hold to record: Off/On.
  - Auto record: Off/On.

- Photo Settings
  Photo Settings
  
  - Image Format: JPEG, PNG.
  - Noise reduction: Off/On, demo mode.
  - Freeze on capture: Off/On.
  - Snapshot preview: Off/On, position, freeze seconds: 1-10 seconds.

- Audio Input settings
  Audio Input settings
  
  - Volume of system sounds: 0-100%.
  - Record audio: Off/On.
  - Audio monitor: sound level indicator.
  - Audio sources: wired microphone, line in, USB microphone, HDMI audio.
    System

- Study Info
  Study Info
  
  - Patient Info selection: Off, Human, Veterinarian
  - Auto start of Study: Off/On.
  - Worklist search and worklist server setup.

- Device Info
  Device Info
  
  - Institution name
  
  - Department name
  
  - Location
  
  - Device title
  
  - Logo (branding of the recordings)
    Logo (branding of the recordings)
    
    - View, replace, delete.
    - Show logo: Off/On, position, size: 5-40%.

- Printer

- Display
  Display
  
  - Brightness.
  - Pointer Speed (speed of the external pointing device, like a mouse).
  - Display rotation: 0°, 90°, 180°, 270°.
  - Display size: 50-120%.

- Date and Time
  Date and Time
  
  - Time selector.
  - Date selector.
  - Time zone.
  - Date format: YYYY-MM-DD, DD/MM/YYYY, MM/DD/YYYY.

- Language
  Language
  
  - Language of the user interface (except the Settings, which are in English only): English, German, French, Italian, Spanish, Polish, Dutch, Czech, Swedish, Danish, Finnish, Slovak, Norwegian, Russian, Turkish, Brazilian Portuguese, Japanese, Korean, Thai, Chinese Traditional, Chinese Simplified, Arabic.
    Archive

- Storage
  Storage
  
  - Resolution limit: set separately for each Storage type (Internal, USB, Network): 2160p, 1080p, 720p(30), Only images, Off.

- Export
  Export
  
  - Disabled.
  - Export to PACS: PACS server setup, secondary PACS.
  - Export to NAS: NAS server setup.
  - Auto Send: Off/On.
  - Auto Delete: (after Send): Off/On.

- Report Settings
  Report Settings
  
  - Preview
  - Header image selection (hospital logo).
  - Image at the end of the report (signature, stamp).
  - Footer text.
  - Notes text.
  - Page layout.
  - Page size.
  - Auto reporting: Disable, Print, PDF.
    Advanced

- Connections
  Connections
  
  - Network
    Network
    
    - IP setup: DHCP (Auto) / Static IP selection: IP address, Mask, Gateway, DNS.
    - NTP Server – Network Time Protocol: IP address:port; Test button.
  
  - Network Storage
    Network Storage
    
    - Server Properties: server IP address, folder name, user name, password, label, and domain.
    - Personal mode: When user accounts are enabled and the user is logged in, use this user's name and password to access the Network Storage.
    - Video resolution limit: 2160p, 1080p, 720p, Only Images. These admin limits override the user limit.
    - Find a server.
    - Test.
  
  - Remote Access
    Remote Access
    
    - Remote access: Off/On.
    
    - Use https: Off=HTTP, On=HTTPS.
    
    - Password (for remote access).
    
    - Local storage. Enable local storage on a remote device (MVR Remote App).
    
    - Remote app download QR code.
    
    - WEB streaming. Enable streaming via network and Audio option.
      WEB streaming. Enable streaming via network and Audio option.
      
      - Streaming: Off/On.
      - Always allow (allow watchers to connect without confirmation from operator: Off/On.
      - Enable audio (allow watchers to hear audio from the device): Off/On
    
    - API access. Password for the non-blocking API access. Allows simultaneous local use and remote API control.
  
  - External Apps
    External Apps
    
    - Enable External Apps: Off/On.
    
    - Default App selector
    
    - New app: add an external app button (“+”).
    
    - Add/Edit external App
      Add/Edit external App
      
      - Name
      - Description
      - Type: HTTP/HTTPS
      - URL
      - 16:9: Off/On, force this app to display in a 16:9 ratio.
      - Block screen saver: Off/On, screen saver will not be activated when this app is shown.
      - Test, Add, Update.
    
    - List of External Apps with an individual enable button.

- Storage Rules
  Storage Rules
  
  - Disable USB Storage: Off/On.
  - Internal storage cleanup rules: keep 50GB free, keep last 28 days.
  - Auto delete after sending to NAS or PACS.
  - Allow deleting non-empty Studies: Off/On.

- Update & Default
  Update & Default
  
  - Backup settings to USB stick: Save, Restore.
  - Format USB Storage.
  - Format Internal Storage.
  - Reset settings to default.
  - Reset device to factory default.
  - Update firmware.

- User accounts
  User accounts
  
  - User accounts enabled: Off/On.
  
  - Add user: “+”.
  
  - LDAP:
    LDAP:
    
    - Enabled: Off/On
    - LDAP Server IP address, server port, Auth path, Naming context, Admin groups, User groups, Guest groups, Caching time (hours), Use SSL: Off/On.
    - Test server connection
    - Test user authentication.
  
  - List of users; allows Role selection: ADMIN, USER, GUEST.

- Security
  Security
  
  - Renew password (time settings).
  - Inactivity time-out: 1-60 minutes or never.

- Activation keys
  Activation keys
  
  - List of active features
  - Enter new key.

- Audit Trail
  Audit Trail
  
  - List of the last 100 events
  - Filter events.
  - Export audit log to USB.
  - Erase audit log.

## MediCapture Medical Video Recorders Software Features of MVR and MTR series of medical video recorders

### Main Features of MVR and MTR series devices

- Record high-quality medical images and videos in High Definition (HD).
- Optional 4K video recording package AK4K enabling video recording in 4K and including a video signal converter matching the customer's 4K camera signal output type.
- Storage for recordings can be selected from the Internal Storage, USB Storage, and Network Storage (NAS).
- Parallel recording, when two video inputs can be combined into a single Picture-in-Picture composite video or recorded independently.
- Smart workflow including Study management, patient information input, and editing, video recording with simultaneous image capturing, file archive, review of the recordings with the ability to edit and annotate images, create PDF reports, trim videos, copy or delete recordings.
- Manual input of the patient data, procedure description, and surgeon name and notes.
- Automatic Video Repair (AVR), ensuring that videos are not lost if the recorder loses power or when a USB stick is accidentally removed during a recording session.
- USB Storage Disablement feature for health care facilities with the restricted use of removable storage
- User management.
- Remote control over RS232 using a USB-to-RS232 adapter (not included).
- No measurement features, no calibration is required.

### Traceability of the Recordings

All recordings are traceable to the actual device used to acquire these recordings. The best way to trace MVR devices is by using Device ID, which is unique for every MVR device and consists of 8 characters. The Device ID can be found on the supplementary label at the bottom of the MVR device (see attached photo) and in the INFORMATION screen of the user interface. The device ID can be found in files produced by the MVR recorder in the DICOM tag or the EXIF tags when DICOM is not used.

DICOM standard defines specific tags for the information of various types. The Device ID is saved in the DICOM tag (0018,1003), and the device firmware version is saved in the DICOM tag (0018,1020). Important note: In order to contain all the information, DICOM files must be produced by the MVR device. This can be achieved by using the "Send to PACS" or "Copy as DICOM" functions. If customer copies plain JPG and MP4 files and later converts them to DICOM at their side - they will lose device and patient information.

EXIF information of the captured images and video recordings also contains the Device ID and device firmware version. Metadata in images (JPG and PNG) is stored in the so-called EXIF data structure. EXIF data was created for the photography applications to keep the camera model and parameters. EXIF standard does not define DeviceID, so the store MVR model and Device ID are stored in the tag "Model", for the example "EXIF:Model": "MVR Pro 20bd4b50".

Metadata in video files is included as Quicktime MP4 tags. MP4 tags were designed for different purposes, and a model of the producing device was not even defined. We use Composer tag:  QuickTime:Composer": "MVR DeviceID".

It's important to note that the device's Serial Number is only printed on the label and is not traceable in software. However, you can use the Device ID, which is also printed on the supplementary device label, for traceability instead.

### Video Input Signal Settings for MVR and MTR series devices

- Two options for video input signal settings are BT2020 and Extended Color Range
  Two options for video input signal settings are BT2020 and Extended Color Range
  
  - BT2020 and color range options are set per camera
  - Only 4K cameras can output BT2020 color; typically, 4K cameras are connected to HDMI 1
  - Once the BT2020 color gamut is enabled, still images and videos are recorded with the color space set to BT2020
  - Only some viewers support the BT2020 color gamut; however, it will be shown in the default color gamut BT709 when BT2020 is not supported
  - While reviewing by MVR devices themselves, you will not be able to see any difference with the BT2020 option enabled or disabled - it will be displayed in BT709

- Select the color range to "extended" to match a specific camera. When not sure, keep "normal."
  Select the color range to "extended" to match a specific camera. When not sure, keep "normal."
  
  - Technically, the extended range means 0-255, while the normal range is 16-234 for the 8-bits colors

### Network Features of MVR and MTR series devices

- Connection to the wired or wireless network allows more features
  Connection to the wired or wireless network allows more features
  
  - Recording to the Network Storage (NAS) or Send to NAS;
  - Video and audio streaming;
  - Integration with hospital information and imaging systems via optional DICOM upgrade package AKDICOM;
  - Remote control over the network from the web browser, tablet, or smartphone with MVR Remote App or API;
  - The ability to connect wireless BT devices: BT headsets for audio recording, BT HID devices for UI.

### Video Playback Speed Control Feature of MVR and MTR series devices

- Allows selecting video playback speed from 0.1x to 10x.

- Speed steps: 0.1x, 0.2x, 0.3x, 0.4x, 0.5x, 1x, 2x, 3x, 4x, 5x, 6x, 7x, 8x, 9x, 10x.

- Speed control buttons look like "<< " and ">>":
  Speed control buttons look like "<< " and ">>":
  
  - During Pause, these buttons change into "<1" and ">1" for frame-by-frame stepping.

- Touch button functions are duplicated by the keys "-" and "+":
  Touch button functions are duplicated by the keys "-" and "+":
  
  - Short tap reduces/advances video playback speed by one step.
  - Long press adjusts play speed to the slowest/fastest value.

### Video Edit Feature Description of MVR and MTR series devices

- Allows selection of several segments from the original video recording.
- Saves selected segments as a new video with desired parts only.
- NOT available for MVR Lite (MVR400).

#### Quick Manual on Video Edit using MVR and MTR series devices

- Press the "video edit" button (the one with scissors) in the video player
- The video player changes into an editor with additional controls
- The primary tool is an axis with time segments below the seek bar
- Each video segment is drawn in yellow, with start and end thumbs
- The video segment represents the time range on the seek bar, which will be included in a new video file
- Initially, there is one segment covering the entire video duration
- Edit the segments as needed, using the provided controls

#### Editing Controls of MVR and MTR series devices

- Drag the start or end thumb of the video segment to change its time range
  Drag the start or end thumb of the video segment to change its time range
  
  - Merging adjacent segments is possible by dragging their ends

- Click the segment to select it, then click the delete button to delete it

- Click a segment to select it, then click the cut button to split it into two parts
  Click a segment to select it, then click the cut button to split it into two parts
  
  - Two modes: if the seek bar is positioned in the segment, the cut is done at seek bar position; otherwise, the segment is cut at its center

- To create a new segment, click on the empty space right below the seek bar (not occupied by another segment) and move/touch to the left or right; a new segment will be created

- Fine-tune selected segment thumb's position using the blue previous/next buttons on the left and right side of the seek bar

#### Notes on Editing using MVR and MTR series devices

- Segment start/end times can be positioned only on keyframes
  Segment start/end times can be positioned only on keyframes
  
  - Keyframe: a special type of picture frame stored in a video file, occurring when a drastic change of video picture happens, or periodically approximately every 5 seconds
  - Granularity of selectable segment start/end times is about 5 seconds
  - Each tag in the video, created by capturing the still image, also contains a keyframe so that the video cut can be positioned precisely at the tag

- Zooming is impossible in the video editor, and the saved video is in its original resolution

- The edit area (below seek bar) contains information about the selected segment and the total time of all segments (= time of final video clip)

- The play button behaves differently in the video editor - it previews the final video
  The play button behaves differently in the video editor - it previews the final video
  
  - Seek bar still shows the original video timespan but with defined segments, and seeking in preview works only within the segments
  - Fast skip forward/backward using blue buttons as usual
  - Press the Pause button to stop the preview and return to the editor

- Saving edited video:
  Saving edited video:
  
  - Button on the top right part of the screen allows you to save the final video
  - The video is saved in the same folder as the original video, with appended incremented counters
  - A new video file is created each time you use the Save button
  - The save button indicates unsaved changes with a yellow asterisk
  - If you try to exit the video editor with unsaved changes, a dialog will prompt you to save the changes (or just quit)
  - Cut positions are preserved in the resulting video as tags and visible in the player

### Merge Selected Video Files into a Single Video using MVR and MTR series devices

- From the Review screen: select several videos and click the Edit button

- Files appear in the editor as one continuous video with green tags showing the start of each video

- Portions can be cropped out as during regular video editing

- Preview of the resulting video is available

- The result may be saved as one continuous video file

- Limitations:
  Limitations:
  
  - Result file cannot exceed 4GB
  - All videos should be recorded with the same settings (codec, resolution, bitrate, audio, etc.)
    Description of Features for MVR/MTR recorders

## External Apps

Applicable device models: MVR435, MVR436, MVR450, MVR460, MTR133, MTR156.

Available since firmware version FW 250603.

Category: New feature.

Workflow stages: Start screen, Settings..

Purpose: Enables control of the external smart devices on the local network via a built-in web browser, such as a video switch matrix, intelligent camera controller, surgical light controller, etc.

This feature, External Apps, is intended to control video sources, such as smart camera controllers, video switches, and routers, over the web interface, or provide web help or guidance for the device operation.

### Usage

An external app is a browser window with a preset URL. In other words, an external app is a shortcut to a specific website or web application.

When enabled, the vertical scroll of the external apps is available on the left side of the Start screen. Tap on the app icon to open a browser window.

It is possible to navigate through the connected website or web app in the same way as using a regular web browser. External apps behave like tabs in a regular browser. Closing the browser window by tapping the “X” button in the top left corner of the screen will keep the browsing progress in the background, allowing you to continue from the same point after reopening the same external app. The background activity of the external apps will remain active until the user logs out or the device restarts.

The browser window starts with the upper navigation bar hidden. Scroll the video down to reveal the navigation bar.

To refresh the current web page content, tap the “Reload” icon in the screen header on the right side, next to the app icon. To browse back, tap the “<” button in the right corner of the screen header.

To set up and customize the list of external apps, open the “External apps” setup page in “Settings > Advanced Settings > Connections”, then tap on the “Enabled” slider.

Tap the plus sign “+” in the screen header to add a new app or tap the existing app to edit its parameters. Select the type from HTTP or HTTPS, enter the URL, such as “www.medicapture.com”, or the IP address and port for external smart devices on the local network, like “192.168.2.13:3333”.

The “Test” button will open the built-in browser with the specified URL.

Tap the “Update” button to save changes.

Tap the “Remove” button to delete the currently selected app.

The app's icon is automatically fetched from the website. If the icon cannot be found, the default “Globe” icon is used. The icon is obtained by searching for the “favicon.ico” file link on the landing page or in the root page.

Each external app can be enabled or disabled individually by tapping its “Enabled” slider.

The sequence in which external apps are listed can be changed by tapping on the “^” button to move the current entry upwards or tapping on the “v” button to move it downwards.

One app can be selected as the default home app, and it will start automatically once the device starts and the user logs in. Select the default app from the drop-down list at the bottom of the External Apps settings screen.

In Portrait orientation, an External App can run under the live camera view at the bottom half of the screen.

## Support for multiple USB cameras

Applicable device models: MVR435, MVR436, MVR450, MVR460, MTR133, MTR156.

Available since firmware version FW 250603.

Category: New usability feature.

Workflow stages: Live Study.

Purpose: Enable simultaneous use of two USB cameras..

### Usage

Up to six USB cameras can be connected simultaneously, enumerated as “USB camera”, “USB camera 2”, “USB camera 3”, and so on.

All connected USB cameras will appear in the list of available inputs on the “VIDEO INPUT SETTINGS” screen. Select the camera first, and later select the desired resolution.

Video settings, such as resolution and Area of Interest, will be automatically stored for each camera individually.

Adding new cameras, changing the USB port, or adding a hub will alter the enumeration of cameras. Connect all USB cameras before powering on the device and keep them connected at all times, as it may become very confusing when USB cameras are plugged in and unplugged live. If the physical connection has been changed, reboot the device and then make the proper selections and settings.

When two USB cameras are intended for simultaneous use (PIP, Split, Dual View, Parallel recording), one camera should be connected to the USB-C port, while the other should be connected to the USB-A port of the device. When both cameras are connected to USB-A ports or via the same USB hub, simultaneous use is possible only for lower resolutions, typically 720p30 and below, due to USB bandwidth limitations, especially when the cameras are USB 2.0.

When USB cameras are intended to be used separately (Live Study recording with a single video source), there is no limitation on using USB ports or hubs.

## Custom logo stamp

Applicable device models: MVR435, MVR436, MVR450, MVR460, MTR133, MTR156.

Available since firmware version FW 250415.

Category: New branding feature.

Workflow stages: Study.

Purpose: Enable branding of the recordings and the live view with the hospital, system, or personal logo.

The branding logo stamp will be shown during the Live Study, recorded in videos, and captured images when enabled.

Logo settings are available at the bottom of the “PATIENT INFO SETTINGS” screen.

Copy the custom logo image in the JPG or PNG format to the USB flash stick and plug it into the USB connector on the device. Tap the “Pick” button and select the desired file from the list.

To replace the logo, tap the “View” button, and then select “Replace” or “Delete” from the pop-up menu. Select the desired logo file from the list of image files on the USB flash stick.

Tap the “Show logo” slider to enable logo overlay.

Select the logo position relative to the Area Of Interest (AOI): top-left, top-right, bottom-left, or bottom-right. The logo size can be adjusted using a “Size” slider, which ranges from 5% to 40% relative to the AOI vertical size, in 5% increments. Set the logo size and position so that it does not overlap the date stamp.

## Dual View in Portrait Screen Orientation

Applicable device models: MVR435, MVR436, MVR450, MTR133, MTR156.

Available since firmware version FW 250326.

Category: New usability feature.

Workflow stages: Study, Archive, Settings.

Purpose: Enable comparison of the two cameras, live (real-time) camera view with a previous recording, and comparison of two recordings. Application examples: review recordings “Before” and “After” looped playback of the recordings from the fluorescence camera or ICG (IndoCyanine Green) video as a reference to the live surgery footage.

There are recorders on the market that allow for the simultaneous recording and review of two video channels. Typically, the standard landscape layout is used, featuring two small windows - one for each camera's live preview or playback. Our solution maximizes the usage of the screen area by taking advantage of a portrait orientation.

Dual View is compatible with all new device models; however, some models may not be suitable for this feature. For example, the MVR460 is unsuitable for portrait orientation, and its built-in 7-inch touchscreen is too tiny for dual-view interaction. The suitable models for the application requiring Dual View are MTR156 and MVR450 or MVR436 with MTS156 monitor. MTR133 can be used when there are restrictions on the device size.

### Usage

Change screen orientation to Portrait: In the Settings screen, navigate to “Settings - System - Display” and set Display rotation to 90 or 270 degrees. An external monitor, MTR156 or another model, should be mounted in portrait orientation. Dual View will be enabled automatically, and more options will be displayed at the bottom of the screen. Typically, the screen is split vertically in half between two views, but the top view occupies 75% of the screen area when no selection is made for the bottom view. The size ratio is automatically controlled and cannot be adjusted by the user. It is possible to interact with both views simultaneously using the touchscreen, and the two views operate independently from each other, in principle.

During the Live Study, several options are available for display at the bottom of the screen, under the live footage of the current camera: another camera or an Archive. The screenshot below on the right shows an example of a comparison between live footage from a microscope camera and recorded footage from the fluorescence camera, which was captured a few minutes earlier.

When two cameras are shown live, recordings can be made independently for both cameras unless Parallel Recording is enabled. The bottom camera displays fewer controls: a Capture and Record button, and an ”X” sign to close the camera’s live view. Top and bottom cameras can be easily swapped by tapping on the Input select button (marked as “1/2").

The archive screen allows a review of another Study under the current selected Study. The study below can be the same as the one above, or it can be a study recorded at a different time, or a study from a different storage location. For example, a Study on Internal Storage can be compared to a Study on Network Storage. In both views, images and videos can be played, edited, or zoomed independently at the same time. When both videos contain soundtracks, both audio tracks will play simultaneously. All controls and interactions are identical to those in the regular single-view mode.

This allows for comparison between “before” and “after” footage, or footage from different cameras or patients. Portrait screen orientation also allows larger previews of the reports in the portrait layout. Examples are presented in the screenshots below.

## WiFi connectivity using USB adapters

Applicable device models: MVR436, MVR450, MVR460, MTR133, MTR156. Not available for MVR435.

Available since firmware version FW 250326.

Category: Connectivity. Workflow stage: Settings.

Supported USB WiFi adapters: ASUS USB-AC58.

Purpose: Enable wireless connectivity for MVR/MTR devices.

Note: Log in as Administrator, which is required to perform Network Settings.

### Usage

Connect the USB WiFi adapter when the device's power is off. Only one adapter can be used at a time.

The LAN cable must be disconnected; an active wired LAN connection will disable wireless connectivity. Power on the device. On the Settings screen, navigate to Advanced> Connections> Network> Network Settings, then tap More settings. This will show system settings for the Internet.

Hint: Tap and hold the LAN icon on the INFORMATION screen for quick access to the Network Settings.

Tap on the Wi-Fi slider to enable WiFi. The list of available networks will be displayed. If the WiFi enable

slider does not work and turns off automatically, the WiFi adapter is not connected or not supported. Connect

the supported adapter and reboot the device.

Tap the desired network from the list and enter the password to establish a connection. Tap on the Advanced options to set the static IP and other parameters. Ensure the status “Connected” is displayed for the desired network.

Return to the device settings and observe the wireless connection status on the INFORMATION screen. The WiFi icon should appear under the wired LAN status, and the current wireless IP address should be displayed. Tap the WiFi icon to view available WiFi networks, change the connected network, adjust settings, or turn off WiFi. Network settings are saved automatically, and the device will reconnect to WiFi at the next power-on.

## Video Mode Menu

Applicable device models: MVR435, MVR436, MVR450, MVR460, MTR133, MTR156.

Available since firmware version FW 250323.

Category: Usability improvement.

Workflow stage: Live (real-time) Study.

Purpose: The video mode menu offers quick access to video compositing features, including Picture-in-Picture, Split View, and Parallel recording.

### Usage

Tap and hold (over a second) on the Input select button (marked as “1/2") until the video mode menu appears. Select the desired combination of two video inputs, Split View or Picture in Picture, or choose Parallel recording to record both video inputs to separate files. Selecting the Picture in Picture option displays a sub-menu to choose the desired position of the picture-in-picture: top left, top right, bottom left, bottom right, or disabled, as shown in the screenshot example. Selection will be applied immediately, and the current layout of the video inputs will be updated.

## On-Screen Indicator Tally Light (OTL)

Feature: Recording Indicator or On-screen Tally Light (OTL).

Devices: MVR-series and MTR-series.

Available in FW250119.

Category: Usability improvement.

Workflow stage: Live (real-time) Study.

Purpose: Provide a clear visual indicator of active recording.

The objective of adding OTL is to enhance the operator's visibility of the active recording. Currently, we have a video icon indicating active recording, but it is small and cannot be clearly seen from a distance on a small screen. Additionally, MTR devices do not have front LEDs, so users can only rely on the small icon, which is not obvious enough from a distance.

### Usage

OTL is disabled by default. Enable it on the Settings screen Recording Options by tapping the slider On-screen Tally Light.

OTL will appear when the recording is ON (constantly on, no blinking), and it looks like a green rectangle with

the text “REC” in it. OTL will blink once for 1 second during the still image capture (negative blink - the entire

green rectangle off - when recording is ON).

OTL size can be adjusted by tapping on it. A pop-up window titled “Recording Indicator” will offer 11-step sliders for the width and height adjustment of the recording indicator, as shown in the screenshots. Tap on the Close button to complete the OTL size adjustment. OTL size will be automatically saved and applied at the start of the device.

Swiping icon positions will also change the OTL position; OTL is positioned over the Back button. Hiding icons will hide OTL. Screenshot examples demonstrate how OTL size can be adjusted to minimize the obstruction of the live (real-time) camera.

For devices with a small screen, OTL can be adjusted to almost fill the full screen size, allowing for a clear view from a distance. Covering the entire camera footage is beneficial when the primary surgical monitor is available, and the device's small screen serves as a visual indicator for recording. OTL does not cover control buttons.

External Tally Light. The “Scroll Lock” LED of the standard keyboard is used to indicate the recording function. The LED indicator logic is precisely the same as the internal on-screen tally light.

## Area of Interest AOI

Feature: Area of Interest AOI within the video input signal.

Devices: MVR-series and MTR-series.

Available in FW250119.

Category: Usability improvement.

Workflow stage: Live (real-time) Study.

Purpose: AOI enables users to select a rectangular area on the screen to be captured in images and videos, thereby improving workflow efficiency.

The Area of Interest (AOI) feature allows users to select a rectangular area on the Live Study screen, capturing only the selected area in images and videos. This is useful when the active area of the screen does not cover the whole screen, as is often the case with endoscopes.

For endoscopes, the active area is typically a circle located at the center or side of the screen. The other screen area is black or contains some camera settings. Often, the black area is not desired for the recordings or reports. For reporting, the doctor copies all images to a PC, crops them using PC tools, and later uses these images to generate the report. This is not productive, as the crop area is always the same.

### Implementation details

To activate AOI, tap and hold (over a second) on the live (real-time) screen until guiding symbols appear, as shown in the screenshot example. The intuitive guide symbols will be displayed, and the screen area outside the AOI will be slightly dimmed.

Change AOI size by dragging a circle symbol in the top-left or bottom-right corner.

Move the AOI rectangle to a different position by dragging the four-arrow symbol.

Confirm the AOI selection by tapping the “✓”

symbol.

Cancel (deactivate) AOI by tapping the “X” symbol.

A cross mark in the center of the AOI helps to position the AOI accurately across the live video.

All images and videos will capture only the selected AOI.

The AOI coordinates are automatically saved for future use.

The AOI cannot be changed during the recording process.

AOI is different for each of the two input video channels and can be set individually.

AOI is also used during PIP and parallel recording.

Stamps, overlays, and PIP: all are aligned to the AOI.

AOI settings do not affect live Study preview or streaming - Live is showing in the same way as it is now. AOI only affects image and video capture. Visually, the area outside of the AOI is slightly dimmed.

### FAQs

Can the AOI be deactivated if it is no longer needed?

Answer: Yes. Long-press on the Live screen to invoke the guide symbols and tap the “X” symbol to deactivate AOI. In principle, AOI is always active and covers the entire screen by default; when enabled, AOI covers a portion of the screen.

Can the AOI be applied to previously captured images or videos?

Answer: No. AOI is applied only to the recording taken while AOI is active.

Does AOI affect the quality or resolution of the captured images and videos?

Answer: No, the recordings are taken using all the original pixels within the AOI area. However, when the AOI resolution is higher than defined by the Storage Settings, the final recordings will be scaled down to the limits set in the Storage Settings.

How does AOI work with multiple video sources?

Answer: AOI is defined individually for each of the two input video sources.

How to save AOI settings as default for future use?

Answer: AOI settings are automatically saved for future use of the current video source on this device.

How to change the AOI shape (e.g., from rectangle to circle)?

Answer: AOI can be defined only in a rectangular shape.

## Split View SV

Feature: Split View of two cameras side by side.

Devices: MVR-series and MTR-series. Not applicable for MVR, MVR Pro, MVR Lite.

Available in FW 250126.

Category: Usability improvement.

Workflow stage: Live (real-time) Study.

Purpose: SV allows for the simultaneous display and recording of two camera inputs side-by-side for required

procedures.

The Split View feature displays two camera inputs side by side, each scaled to fit half the screen without cropping any content.

This feature is designed for procedures requiring simultaneous use of two video cameras, such as video laryngoscopy-assisted bronchoscopy intubation for managing difficult airways or ultrasound-assisted laparoscopy.

### Implementation details

The Storage Settings determine the SV resolution, and if multiple storages are enabled, the highest resolution setting will be used (see the Storage Settings screen). If a higher or lower SV resolution is desired, change it in the Storage Settings screen. When Storage Settings are set to “Only images”, the default 1920x1080 resolution will be used for the SV.

After the SV resolution is defined, for example, 1920x1080, the relevant AOI (Area of Interest) is first applied to every camera video input. Then it is automatically scaled to fit half the SV screen, for example, 960x1080. Black bands may be added horizontally or vertically when the AIO aspect ratio differs from the half-screen aspect. A vertical separation line in the center of the screen clearly defines the view area of each camera, avoiding possible confusion. The camera separation line is fixed and cannot be adjusted.

The AOI of every input video channel can be adjusted by a long touch to the image (see AOI feature description).

The SV screen is updated when an image frame is received from the camera, which reports the highest frame rate. Thus, the SV framerate equals the fastest framerate from the attached camera sources.

Recordings are saved, as you can see on the screen, at the SV resolution and SV framerate.

Sound can be chosen from any audio source on the Audio Settings screen menu.

Cameras can be swapped from left to right using the on-screen input select button.

When a camera has no signal, the relative SV area is black.

The SV feature cannot be used simultaneously with the PIP (Picture-in-Picture) or Parallel Recording features.

SV is intended for use with two cameras. Half the screen will be black when SV is activated with a single video source.

The SV can be activated from the Settings screen Video Input Settings by tapping the Split View slider.

### FAQs

Does SV support a vertical layout (cameras arranged vertically instead of side-by-side)?

Answer: No. For the vertical uncropped layout of two cameras, change the screen orientation to portrait and use

the Dual View feature.

Can the size of each camera's view be adjusted individually in SV (e.g., make one camera's view larger than the

other)?

Answer: No. When you need a smaller image, use the PIP feature.

What happens when the resolutions of the two cameras are different? How does SV handle this?

Answer: Yes, the resolutions and framerates of the two cameras can be different. Every camera input is automatically scaled to fit half the SV screen.

Can each camera's video feed be saved separately in SV mode?

Answer: No. Use the Parallel Recording feature to save each camera's video feed separately.

Can SV be used with more than two cameras?

Answer: Only two active video input channels can be selected, so only two cameras can be shown on the SV

screen. However, some MVR/MTR devices allow several video sources for each input channel.

Is it possible to get rid of the black bands?

Answer: Adjust each camera's AOI Area of Interest to fit half the screen without black bands.

## On-Screen Keyboard

A new on-screen keyboard (Gboard) is Available in FW 250126 to enable support of the Asian languages and

more.

Tap the icon in the top-left corner to show the keyboard control menu.

It is possible to adjust the keyboard's style, size, and position, and make it float.

Tap the Settings icon to bring up the keyboard settings screen.

Add the desired input language by tapping the “Add keyboard”. Use a search tool to search for the language among hundreds of options.

The on-screen keyboard layout can be changed to another language by tapping the Globe key.

## Shortcut keys

Applicable models: MVR435, MVR436, MVR450, MVR460, MTR133, MTR156.
Shortcut Keys for System Integrators to remotely control MVR and MTR series devices from the Network, RS232, and USB keyboard. MVR/MTR shortcut keys definitions for different modes of operation are below:

#### Start Screen shortcut Keys (added 250527)

- 0: set screen rotation to 0 degrees (landscape);
- 9: set screen rotation to 90 degrees (portrait);
- 3: set screen rotation to 270 degrees (portrait);
- 6: set screen rotation to 180 degrees (landscape);
- F3, n: Start Study;
- i: Information screen;
- s: Settings.

#### Live Mode shortcut Keys (reviewed 251118)

- F1/F4: capture still.
- F2/F5: start/stop recording.
- Enter: Pause on/off.
- Long F2: Pause on/off.
- PageUp or PageDn: information screen.
- Esc: End of Study confirmation.
- e: Stop recording and End of Study without confirmation.
- F3: End of Study.
- Left/Right arrows: UI buttons position change/hide.
- Home: Video input change.
- F6: stop recording or no action.
- F7: start recording or no action.
- F9: capture an image from the secondary video input.
- F10: record start/stop of the secondary video input.
- '1': change the input to HDMI 1 or no action.
- '2': change the input to HDMI 2 or no action.
- 'c', F12: to switch camera input from 1 to 2 or from 2 to 1.
- 'r' to review the last captured image or play the last captured video directly without the Review screen with thumbnails.
- Ctrl+H: change the color range for the current input: full/limited.
- 's': Split view;
- 'p': PIP (Picture In Picture) enable, default Top left or previously selected;
- '=': enable/disable parallel recording
- 't': show other camera (valid only for portrait layouts).

#### Video Review, Image Editor, Report Preview Modes shortcut Keys

- PageUp/PageDn keys to zoom in/out.
- ASDW keys to pan.

#### Shortcut Keys for the Video Playback

- Space key: Pause/Play mode.
- "< ": move the play position to the previous video tag.
- ">": move the play position to the next video tag.
- "-", "_": Play mode: decrease video playback speed; Pause mode: move to the previous frame.
- "+", "=": Play mode: increase video playback speed; Pause mode: move to the next frame.
- Press and hold key '1' for slow play 0.1x, and press and hold key '2' for fast play 5x (slow/fast playback while the key is pressed).

#### Universal Keys (added on 250603)

Universal keys work system-wide and are particularly useful for external apps.

- Volume control: Ctrl+’>’, Ctrl+’<’; Ctrl+PgUp, Ctrl+PgDn; Alt+’+’, Alt+’-’.
- Back: Ctrl+ESC, Ctrl+’b’, Ctrl+NUMPAD_1.
- Back: gesture: quick swipe from the left or right edge of the screen (added on 250903).
- Home (back to the MVR app, which is the HOME app): Ctrl+’h’, Ctrl+’~’, Ctrl+NUMPAD_7.

## ARCHIVING feature of MVR and MTR series devices

### Internal Storage / USB Storage / External Network Storage

#### General storage rules & and advice for MVR and MTR series devices

- Internal Storage is the fastest and most reliable destination for recordings; however, it serves as a buffer or temporary Storage only.
- The internal storage needs to be activated for DICOM export and sending studies to PACS.
- Data should be copied from the Internal Storage to USB Storage, or Sent to PACS or NAS; there is an Internal Storage Backup feature to copy the entire Internal Storage to external USB drive.
- Internal Storage has auto-cleaning rules, user should setup rules and manage data, user is solely responsible of the data loss or leak.
- Size of the Internal Storage: MVR Pro (MVR409) & MVR (MVR420): 128 GB, upgradable up to 512 GB or 1 TB; 1 TB for MVR435 upgradable to 2 TB; None for MVR Lite (MVR400).
- USB storage is portable and an excellent way to save studies for presentations or for handing out data to the patient. It can also be used to copy or back up recordings from Internal Storage.
- USB flash sticks, SSDs, HDDs, or card readers can be connected as USB storage devices.
- MVR recorders support USB Storage formatted as exFAT, FAT32, or NTFS.
- Due to the large capacities of external USB hard drives, it may take approximately 20-60 seconds to recognize the device. Please be patient and wait until the external hard drive has been recognized. The external hard drive is recognized when the USB icon appears on the screen.

#### Archive selection for MVR and MTR series devices

Storage locations can be selected for direct (real-time) recording of your studies:

- Internal Storage
- USB Storage
- Network Storage (NAS)
  The maximum video recording resolution can be specified separately for each Storage device; the choices are 2160p, 1080p, and 720p. To record for archiving purposes, select 720p, which will also reduce the recording framerate to 30 or 25 frames per second. Selecting "Only images" will turn off video recording for this Storage. MVR recorder offers the flexibility to select one or two Storages simultaneously. When two Storages are chosen, captured images are stored at both locations, and videos are recorded at both locations. For instance, you can select 'Only images' for the Internal Storage and 720p for the Network Storage. This setting ensures that images are stored in both Internal and Network Storages, while the video is recorded only to the Network Storage in the archive resolution. This setup is ideal for capturing images for further reporting and sending them to PACS, while keeping videos in the network archive for insurance or other purposes.

Note: The maximum video recording resolution limit may only reduce the resolution of the input video but will never increase it. For example, when 2160p is selected, and the video input is 1080p, the recording will be performed at the original input resolution, which is 1080p.

Note to model MVR Lite: Internal storage is unavailable for MVR400 (MVR Lite).

#### Video Recording Notes for MVR and MTR series devices

Reliability of the recording using MVR and MTR series devices

The stability of the video recording depends on the writing speed of the media storage. Storage must provide writing speed faster than the current recording bitrate; otherwise, recording video will not be possible, and the recording process will stop abruptly. Testing the writing speed of the new unknown Storage before using it for video recording is recommended. External USB Storage is user-dependant and can vary in brand, size, technology, format, existing file system error, cables and connectors issues, etc. The most reliable method is to record to the Internal Storage. Recording directly to the Network Storage may be affected by the actual network load and server load. Recording over a smaller local network to local NAS within a department might be acceptable. Recording over large hospital networks to distant servers without the knowledge and control of the actual bandwidth and load may not be reliable. Another tip to improve reliability is to avoid parallel recording to different storage media. The most reliable method is to record to Internal Storage. However, consider that any internal memory will be full one day. The later export/copy or Backup to another storage will be necessary. Summary: For reliable recording, choose reliable memory. An internal memory is more reliable than any other memory. Recommended workflow for reliable recording:

- Set recording to a single storage, preferably Internal Storage.
- After some experimentation, set the lowest acceptable video resolution and recording quality. (Users tend to choose the maximum of everything, resulting in huge unmanageable amounts of data, video fragmentation to shorter clips, bandwidth, and storage capacity issues, leading to lower usability and frustration. Intelligent recording resolution and quality selection can significantly improve reliability and customer satisfaction.)
- Perform Copy to USB, Send to NAS or Send to PACS, if necessary, after finishing the Study.
- Keep external USB Storage plugged only when recording directly to the USB Storage. In other cases, plug USB Storage only when a Copy or Backup is required and unplug it when the process is completed. Keeping USB Storage connected without reason may create usability confusion and increase device heat due to the extra energy consumption.
  Testing the writing speed of a Storage on an MVR and MTR medical video recorder

Writing Speed Test is a helpful feature to test the quality of storage media (USB sticks and USB SSD) and network storage.  (Note: Speed test is unavailable when an MVR is under tablet Remote control.) Writing Speed Test function is available on the Information screen by tapping the corresponding storage media icon.A pop-up appears showing Storage details and allowing testing of the write speed of this storage. MVR will run benchmarking that simulates realistic video recording scenarios on an MVR device. Results in green color indicate writing speed suitable for 4K video recording. The typical recording speed required is under 4 MB/s (at 32 Mbps quality settings) with a maximum of 8 MB/s (Super, 64 Mbps, H264, 4K30). Lower resolutions, as well as the HEVC codec, require lower writing speed. The results of the writing speed may be displayed in green (good) or orange (too low). It is not recommended to use Storage when the benchmark result is not green. Note: The reading speed is typically faster than the writing speed and significantly faster for USB flash storage. MVR does not test reading speed but tests writing speed. MVR writing speed test results to the included SanDisk 64GB flash stick are 18-30 MB/s for FAT32/NTFS/ExFAT and are sufficient for video recording. If the writing speed for a USB flash drive or Network Storage is too low - record to the Internal Storage first and copy to USB or Send to NAS afterward. Internal Storage of the MVR medical video recorder is designed to provide sufficient speed to record video in any scenario.

Selecting external USB Storage for MVR and MTR series devices

USB flash stick is included with every MVR device, which provides a write speed sufficient for video recording. It is possible to use other USB Storage devices available from the market: USB flash drive sticks, USB HDDs (Hard Disk Drives), USB SSDs (Solid State Drives), and USB card readers. The typical writing speed of a USB flash is around 13 MB/s, ranging from 8 to 20 MB/s. Larger-size flash may offer faster writing speeds. USB 2.0 is slower in data transfer; however, modern USB 2.0 sticks may have a 10 MB/s writing speed and may serve well for video recording. USB 3.0, 3.1, 3.2, Type-A, and Type-C versions may have different data transfer speeds, and higher versions may deliver higher read speeds. However, the writing speed heavily depends on the underlying flash technology. Typically, all USB flash drives of different USB 3.x versions will have similar writing speeds. When connecting a USB HDD, allow sufficient time to spin up, typically under 1 minute, before it is detected and becomes available for recording.

MVR medical video recorders support the following storage formats for external USB Storage: FAT32, NTFS, and ExFAT. Writing speed depends on the file system as well. FAT32 is the most compatible, followed by ExFAT and NTFS, which are the slowest.

USB Storage may be used for direct recording, copying, and backing up internal Storage. While the USB Flash drive writing speed may be sufficient to perform recording, it may be slow to perform a Copy or Backup of the Internal Storage due to the large amount of data. For Backup, an external USB SSD drive is recommended. USB HDD is also an option for Backup, but the writing speed is slower compared to SSD. USB flash cannot provide higher writing speed due to the flash memory block's long erase time and the operation's sequential nature. In other words, USB flash spends most of its time waiting to be erased during the writing process. The new SSD technology performs many operations in parallel to overcome this problem. There are better options than USB flash for the Backup of the Internal Storage. Backup may require a large amount of data to be transferred (up to 1 TB). Writing this data will require USB Storage to work at the maximum performance for a long time. Maximum performance results in maximum heating. USB flash sticks are small in physical size and do not dissipate heat efficiently, causing the rising temperature of the internal circuits and slowing down the writing process. The longer it takes - the slower it runs. In contrast, SSD drives are larger and typically equipped with additional heat sinks that transfer heat from the inside to the aluminum enclosure. Summary: USB HDD and SSD drives will perform Backup 10-15 times faster than USB flash and are more suitable for data Copying and Backup. For the fastest Backup, use a USB SSD formatted to ExFAT.

How to select a "good quality" USB flash drive? The quality level of the USB flash drive may be defined using parameters such as speed, lifetime, data reliability, and physical size.

- Speed. Typical USB flash sticks can deliver up to 10-30 MB/s or writing speed and 40-130 MB/s or reading speed. USB SSD can deliver 200-500 MB/s or write and read, beating traditional flash 10-20 times in speed.
- Lifetime and data reliability. USB flash drives utilize flash memory with limited write cycles. Frequent rewrites will significantly shorten their lifespan. The number of write cycles, or endurance, varies based on the type of NAND flash memory cell, with single-level cell (SLC) NAND flash supporting up to 100,000 write cycles, multi-level cell (MLC) flash sustaining up to 10,000 write cycles, triple-level cell (TLC) flash having as low as 300 write cycles, and quadruple-level cell (QLC) NAND likely supporting a maximum of 1,000 write cycles. Low-cost flash drives and SSDs use the cheapest TLC technology. Traditional USB flash drives do not manage write frequency to the same flash cell, causing the beginning of the drive to be used more often. SSDs, in contrast, do manage write frequency to the same flash cells and attempt to spread rewrite data as evenly as possible to extend the overall lifespan of the drive. This process is achieved through a combination of techniques known as wear leveling.
- Physical size. USB thumb drives are significantly smaller than typical USB SSD drives.
- "Good quality" modern USB drives could contain SSD technology within the small size and use MLC flash.

#### Folder names for MVR and MTR series devices

Folders are named chronologically after CASE numbers CASE0001, CASE0002, etc. If you want the folder to be named using Study date, time, and patient ID, enable the option "Stamp folder names." Since the MVR435 model, the folder name is always time-stamped and contains DeviceID; personal patient data in the folder name is optional and can be enabled in the Settings menu. It is recommended that patient data be avoided in folder names to reduce the possibility of personal data leakage.

### Internal Storage of MVR and MTR series devices: Rules for automatic cleaning

Rules for deleting the internal storage can be set to One of two options for automatic cleaning of the internal storage can be selected.

- Keeping around 20% of free space, but not more than 50 GB, ensures minimum storage space for the subsequent study.
- Keeping the last 7 days should be selected if the internal storage is only a safety backup. MVR435 model offers 28 days instead of 7. Cleaning rules are checked at the Start of the Study to ensure sufficient space for the new Study. Rules are not checked during the active Study. Keep both cleaning options unchecked (not selected) to keep all recordings and delete them manually.

### Disabling (locking) the USB storage for MVR and MTR series devices

USB storage can be completely disabled/locked if portable or removable media is prohibited in your clinical environment. If the USB memory has been deactivated here, it no longer appears in the archive settings for storage selection.

### Internal Storage Backup Feature Description for MVR and MTR series devices

- Internal Storage Backup feature is available in the Archive screen and it copies all Studies from MVR Internal Storage to external USB flash stick (or hard disk or SSD).
- Note: Internal Storage Backup feature does not backup device settings and Activation Keys; device settings backup is available on the "UPDATE / DEFAULT" screen of the Advanced settings.
- A button for the Internal Storage Backup is located at the bottom-left part of the screen, which is shown only when conditions for backup are satisfied: external USB Storage is present.
- Internal Storage Backup feature will check the available space on USB drive before start copy.
- Internal Storage Backup is incremental. It copies only new or changed files and skips previously copied files.
- It does not delete any other files on USB storage; only Study folders (CASExxxx) are created, and files are copied into folders.
- Users can repeatedly do backups on the same USB storage.
- Internal Storage Backup feature does not delete anything; delete data manually or format Internal Storage when backup is complete.
- When file error is encountered during the backup of the Internal Storage, a pop up dialogue will show the error description; tap to "Skip" button to continue Backup process; only corrupted files will be skipped, all good files will be copied from the Internal Storage to USB Storage.

### Creating a shared folder on your Network Server (NAS) to use as Network Storage for MVR and MTR recorder

- Create a shared folder per your NAS Server instructions.
- Ensure the MVR user has sufficient privileges to read and write to the shared folder.
- Take special care if this is a Wi-Fi user connecting via WPA2-Enterprise. They may need additional setup.
- Note the User Name, Password, and Shared Folder name (Example: User name: mm, Password: 123412341234, Shared Folder Name: Shared.) You will need this information to connect the MVR to the Network Server Shared Folder.

### Settings for Network Storage on MVR and MTR series devices

After you have created the shared folder on your Network Server, you can match the storage settings and test the connection.

Note: Please make sure that Network Storage is enabled in the Archive Settings.

Directly type the IP address of your server or tap on Find Server. Available servers with shared folders in your LAN environment get listed:

- Tap on your server to select it.
  Note: If you do not see the expected server, verify that the subnet where the shared folder is located is accessible by the subnet where the MVR is located.

The Server IP-Address will be inserted automatically.

- Type the properties of your Server and Shared folder for storage:
- User Name = Name of the logged-in user on this server
- Password = Password you are using to start this computer with the entered User Name
- Folder Name = Name of the shared folder
- Label = Server Name - Optional
- Domain = Optional
- Personal mode: Off/On. When user accounts are enabled, and user is logged in, use this user's name and password for accessing the Network Storage.
  You can set a video resolution limit for network storage and select “Only images.” This limitation will take influence general Archive Storage Settings.

Tap on Test to check the settings. When your settings are correct and displayed as OK: Tap on Save to store your settings.

### Send to NAS Feature Description of MVR and MTR series devices

Background: Hospital networks may limit network bandwidth per device to prevent situations where a few devices may occupy the entire bandwidth. Also, the network may not be available at the time of surgery. The solution is the "Send to NAS" feature.

Setup "Send to NAS" options on Archive Settings / Export screen:

- Enable Export to NAS: 'Export to PACS/NAS' set to 'NAS'. When enabled, files saved to Internal Storage can be Sent to NAS. Note: Sending to PACS feature will be disabled. It is impossible to export studies from the Internal Storage to a shared folder (NAS) and PACS simultaneously.

- The optional 'Auto Send' feature will automatically send all Study files to NAS upon completing of a Study (End of Study).

- The optional 'Auto Delete' feature will automatically remove files from Internal Storage once they have been successfully Sent to NAS.

- An orange error message will be displayed at the top of the screen if there are incorrect settings.
  Details of the "Send to NAS" feature:

- Network Storage should be configured but turned OFF for the recording to enable the Send to NAS feature.

- Send to NAS performs a copy of a folder or files in the background from the Internal Storage to the Network Storage.

- Background copy is performed at a lower priority, can be interrupted by New Study or by power off, and will resume automatically.

- Auto Send to NAS will send all Study files as soon as Study ends.

- When the Auto Delete feature is enabled, the study folder will be deleted as soon as all Study content is sent to NAS.

- Sending the same CASE folder again will merge files in the existing folder.

- Sending the same files will overwrite existing ones.

- Sending a few files will create a new folder with the same CASE folder name.

- In the Export settings screen, select Export to NAS to enable this feature.

### Sharing the Internal Storage of MVR and MTR series device over network

This feature enables SAMBA server on MVR device and allows access to the Internal Storage from remote PC. Sharing the Internal Storage is not available for MVR400 (MVR Lite) and MVR435. From the Settings / Advanced/ Storage Rules screen: Tap on Share Internal Storage to enable it; enter password. Address to connect to the internal storage from remote PC will be displayed. Restart MVR device by power off/on after changes been made. From the remote PC point file explorer to the MVR access point, ex: "\\192.168.2.125\storage"; enter credentials: user name: "root" and password for Sharing Internal Storage. Internal Storage of MVR device will appear as folder in PC file explorer.

### How to delete recordings?

Recording can be deleted in the Review screen: select one or several recordings by tapping the right-top corner of the thumbnail and the Delete button. There is also a button to select or unselect ALL recordings. In the Archive screen, the Study folder can be deleted only when it is empty. This prevents the accidental deletion of many recordings at once. When it is necessary to delete a folder, delete all recordings first inside this folder, and then, after returning to the Archive screen, the Detele button will appear to delete the Study folder. There is no feature to delete all the recordings; however, in the Advanced Settings, available to the Administrator only, there is an option to format Internal Storage or USB Storage. The format will delete all the recordings within the selected storage. However, be careful not to lose the important recordings. Ensure all necessary recordings are properly archived—copied, backed up, sent to NAS, sent to PACS, or printed.

## Automation Reporting Feature

The Automation Reporting feature is available on all MediCapture MVR and MTR device models. The recommended firmware version is FW 250924 or newer.

### 1. Report Description

#### Report Structure

- Report Header Image (Present only on the first page).
- Institution Name and Location.
- Device Name, Model, Device ID, and Firmware Version of the device used to create the report.
- Patient Last and First name.
- Patient ID Number.
- Patient Gender.
- Patient Birth Date.
- Performing Physician.
- Study/Series Description.
- Case Folder Name (unique name constructed of the time stamp and Device ID).
- Report Creation Date.
- Current/Total Number of Report Pages.
- Image File Name.
- Image Captured Date.
- Image Notes. Created in Image Review.
- Image to Report. Annotation was done in Image Review.
- Report Notes. Ending notes. Written using Markdown.
- Institution Stamp or Physician Signature.
- Footer Text (present at the bottom of every page).
  The header table (items 2-12) will be displayed on every page to ensure traceability and prevent pages from being mixed up.

### 2. Creating a Report

To generate a new report, follow these steps:

- Go to the Archive and find the case folder you wish to use.

- Open the folder and select the images you want to include in the report. You can choose any number of images before or after entering the Report screen. You must select at least one image to create a report.

- Press the "Report" button.

- Adjust the general report settings as needed.

- Click "Save" to save the report as a PDF in the same folder, or click "Print" to send it directly to a connected printer.
  Click "Save" to save the report as a PDF in the same folder, or click "Print" to send it directly to a connected printer.
  
  - Note: To exit the print menu, either swipe left on the screen or choose "Cancel Print" and then press the "<" arrow button.

- Alternatively, in Archive mode, tap on the Report button to create a report that includes all images in the selected study folder.

### 3. Report Customization

You can customize the appearance of your reports using a variety of settings.

#### General Settings

These settings are adjusted after you enter the "Report" screen and apply to the current report you are creating.

- Page Layout: Choose the page orientation and the number of images per page.
  Page Layout: Choose the page orientation and the number of images per page.
  
  - Portrait: 1, 2, 3, 6 (2 x 3), or 8 (2 x 4) images per page.
  - Landscape: 1, 4 (2 x 2), or 9 (3 x 3) images per page.

- Page Size: Select a standardized size for your report and printing (e.g., ISO A4, Letter, ISO A3, ISO A5, ISO A6, or 100 x 148 mm (Hagaki).

- Mode: Choose one of three modes:
  Mode: Choose one of three modes:
  
  - Default: Standard report with all information.
  - Anonymize: Excludes all patient information.
  - Only images: The report contains only images with no accompanying text.

- Notes: Add or adjust existing notes in Markdown format. These notes will appear at the end of the report after the images (item 17).

#### Report Settings and Presets

The Report settings allow you to create a preset, so your preferred settings are applied to every future report. To access these settings, navigate to Settings > Archive > Report Settings, or from the "Report" screen, click the Report settings button in the top right.

- Report preview: View a simulated version of a report before it's finalized. Patient info excluded.
- Header image (1): Upload an image in JPG or PNG format from the root folder of the USB storage to be used as a header on the first page of the report. The recommended image resolution is around 2048 x 256, or an approximate aspect ratio of 8:1 to 10:1. The image will be scaled to fit the page width.
- Image at the end of the report (18): Upload an image from the root folder of USB storage to appear after the notes (e.g., a doctor's signature or hospital stamp). The recommended image resolution is around 2048 x 256, or an approximate aspect ratio of 8:1 to 10:1. The image will be scaled to fit the page width.
- Footer text (19): Write text with Markdown to be placed at the bottom left of each page.
- Notes text (17): Create a default Markdown note that will automatically appear at the end of every report. This note will be used as a template and can be edited for individual reports by tapping Notes.
- Page Layout and Page Size: These settings function the same as the general settings, but apply as a default for all future reports.
- Auto reporting: When enabled, a report will be created automatically after each study. You can choose to automatically save it as a PDF in the case folder or open the print directory. This feature is disabled by default.

### 4. Notes

- To set up the institution name, Department name, Location, and Device title, navigate to Settings > System > Patient info.
- Following your medical institution's document formatting guidelines, you might need to format your document in Markdown. Here's a quick cheat sheet for common Markdown formatting.
  
  ## UPDATE / DEFAULT screen

Location: Settings -> Advanced -> Update & Default "UPDATE / DEFAULT" screen offers a menu with the following features:

- Update firmware;
- Backup settings;
- Restore settings;
- Format USB Storage;
- Format Internal Storage;
- Reset settings to default;
- Reset device to factory default. To access the "UPDATE / DEFAULT" screen, you need to have Administrator privileges.

### Factory Reset Guide for MVR and MTR series devices

#### General Information about Factory Reset of MVR and MTR series devices

Performing a factory default reset resets all user and system settings to default. Factory Reset helps resolve system errors, before upgrading from an old Firmware version. It can also be done before transferring the device to another department or user to clear old settings, user accounts, and other configurations.

Information and recordings on the Internal Storage of the MVR device remain preserved during the Factory Reset. When you need to clean the Internal Storage from the recordings, perform "Format Internal Storage" from the "UPDATE / DEFAULT" screen menu.

#### Lost Passwords

A deep factory reset is necessary when the Administrator password is lost, which locks the "Advanced Settings" section. MediCapture does not have access to user passwords, nor are there default passwords available. We are unable to assist customers in recovering passwords or user accounts. If only one User Account password is lost and the Administrator has locked the Advanced Settings with their password, a full factory reset is not required. The Administrator can log in to the MVR using their own password without requiring a User Name. From there, they can delete User Accounts, create new User Accounts, or disable the User Account function.

#### Reset device to factory default procedure for MVR and MTR series devices

- From the "UPDATE / DEFAULT" screen menu select "Reset device to factory default".
- Confirmation dialogue will pop up. "Are you sure? You may want to backup settings first". If desired, tap the "Backup settings" button to save settings (including Activation Keys) to the USB Storage, because Reset device to factory default procedure will erase all settings, including Activation Keys.
- After Reset contirmation, device will automatically restart, floating circles will be displayed during the reset procedure, and device will restart again to a normal working mode. The process may take 3-5 minutes to complete.
- Once back to working mode, you may restore saved settings from the USB Storage.
- It is recommended to restart device after restoring settings.
  Notes on restore saved settings: There are 2 ways to restore settings: REPLACE and MERGE. REPLACE uses the entire backup - use this to restore this particular device settings. MERGE is used when you save many typical settings, like servers, hospital info, user accounts, etc and want to use the same settings to multiple other devices, to make the entire department settings consistent. So, you save settings on one completely configured device, and when you apply this backup to other devices, use MERGE - it will use all the settings except of the "device private" stuff, like activation keys and fixed IP address.

#### Deep Factory Reset Procedure for MVR (MVR420), MVR Pro (MVR409) and MVR Lite (MVR400) devices

Deep Factory Reset can be performed when settings menu is not available due to the lost passwords and other unexpected condition.

- Turn MVR device with the main switch on the back panel.

- Press and hold the Video Recording button on the front (middle button).

- Hold down the button on the front and turn on MVR device with the main switch on the back panel.

- Hold the button until the front rings stop blinking (after approx. 15 seconds).

- MVR Maintenance screen will be shown.
  Navigation on the MVR Maintenance screen:

- Use the same Video Recording button to navigate the cursor line to: Reset to Factory Defaults

- Press the Patient button to confirm.

- Use the Video Recording button again to navigate the cursor line to: Yes

- Press the Patient button to confirm and activate the reset.
  MVR device is re-booting with factory default settings (time approx. 50 seconds).

### How to upgrade/update an MVR and MTR Recorder

Upgrading the MVR and MTR Recorder to new firmware is a quick and easy procedure, taking only a few minutes. You'll need a USB stick and the new firmware file. Your settings and activated keys will remain unchanged.

The terms "update" and "upgrade" are interchangeable. Some newer firmware versions may include additional features, making them an "upgrade" by providing extra functionality to the MVR device.

#### Getting the latest MVR firmware for MVR and MTR series devices

Get the latest MVR firmware, with free improvements and new features, from your sales representative or directly from MediCapture. Request it from the https://medicapture.com/support/ website or contact your regional MediCapture office. Firmware is delivered as a digital download, in a single file of approximately 900MB in size.

The latest MVR firmware version is 231225.

#### Check the actual firmware version of MVR and MTR series device

• Switch on your MVR device. • Once the boot sequence has been completed, access the INFORMATION page by using the internal touchscreen, monitor or a connected USB mouse. Tap on the icon. You can see the actual firmware version, e.g., APP=230220. • If the latest MediCapture Firmware Update Report recommends updating this firmware version, please continue with steps 2 or 3.

#### Upgrade the firmware of MVR and MTR series device using USB flash drive stick

• Create an “Upgrade Flash Drive.” We recommend using an empty USB stick. • Download the upgrade file from the MediCapture customer's portal or from the link, provided by your sales representative. • Download the latest firmware and copy it to the USB Flash Drive. The MVR or MVR Pro update file is MVR409-yymmdd.upd where “yymmdd” indicates the firmware version. For MVR Lite, the update file is called MVR405-yymmdd.upd. MVR435 update file names as MVR435-yymmdd.upd. Files with wrong name or name structure will be rejected. • Insert the USB Flash Drive into the front panel. • Access the INFORMATION screen again and tap on the icon for SETTINGS. • Go to Settings/Advanced/Update & Default. • Tap the “Update” button in the section Update firmware and follow the instructions. • Please re-confirm that you are using the correct firmware version when it is displayed. During the upgrade, the MVR requires USB removal. Follow on-screen instructions. After upgrade, that may take 3-5 minutes, MVR reboots automatically. Wait for startup screen, then wait 2 minutes. Turn recorder off and on using back panel switch. Once device is in the normal working mode - new firmware is now ready for use.

- Access the INFORMATION screen once more to check the new firmware version has been installed.

- Check your system settings for Time zone, Date, and Time. Settings/System/Date and Time.

- Check if your (optional) activation keys are unlocked. Settings/Advanced/Activation key.
  When error happened during update:

- Do not worry, your data is safe and MVR device will stay with the current firmware.

- Make sure that firmware update file is copied to USB stick without errors; download firmware update file again; format USB flash drive or use another USB flash to ensure firmware file is not corrupted.

#### Upgrade firmware of MVR series device from remote PC using MVR Remote Configuration

Open a web browser on your PC or portable device and type in the device address, shown on MVR Remote Access Settings, example: http://192.168.1.233:3333/config and enter password.

Check your actual installed firmware version by going to ►Information ►System Information.

Start update/upgrade process from ► System ► Upgrade Firmware tab; select firmware file and confirm update. Sending the firmware file to your MVR may take a few minutes. Once the upgrade screen on your device changes back to the login screen, the remote update procedure of the recorder has started. Wait 5 minutes, and log in again to verify that the new firmware version has been installed.

## Network Settings for MVR and MTR series devices

### Wired LAN Settings / Network Settings for MVR and MTR series devices

#### General preparations

- Connect the network cable (RJ45) to the LAN connector on the back.
- For MVR Lite, a USB-LAN adapter is required.

#### General Network Settings

- Go to the Network SETTINGS page.
- Network settings are automatically assigned when MVR is set to Auto IP settings. It is recommended to apply these settings permanently.
- Change to Manual IP setup and tap on Set.
- Enter manual IP settings if needed and confirm by tapping on Set.
- Control IP settings on the Information screen.

### Wi-Fi for MVR series devices

#### General Preparations

- Connect the supplied Wi-Fi antennas to the rear connectors "WIFI" and "WiFi/BT".
- Turn on your Wi-Fi access point (Wi-Fi Router) and ensure you know the password.

#### Activating Wi-Fi

- Go to the Wi-Fi SETTINGS page.
- Enable Wi-Fi and wait the list of the access points to be populated.
- If your Wi-Fi access point is not listed, tap on the search icon.
- Once your access point is listed, tap on it.
- Type the correct password, paying attention to uppercase and lowercase letters. After successful connection, the Wi-Fi IP address of your MVR device will be displayed. Password will be saved automatically, WiFi will reconnect automatically after the next power on.

#### WPA2-Enterprises / Setting-up secured Wi-Fi CERTIFICATES on MVR series devices

- WPA2-Enterprise is more secure than WPA2-Personal and provides personalized login and personalized encryption.

- To log in, the user must use their identity and password.

- Additionally, the IT Administrator may create optional security certificates. These certificates should be installed on the MVR device later.
  Preparations and equipment to be used to install security certificates

- Equipment to be used: External USB keyboard, USB stick (empty).

- Upgrade to the latest firmware version before beginning.

- Obtain the Wi-Fi MAC address: open the Information page, Tap on the MVR device icon to see details about MAC addresses.
  Creating the certificates for encryption

- Follow the requirements of your local authentication server.

- MVR supports security standard WPA2, which fully implements the IEEE802.11i security standard with CCMP/AES encryption. Certificates need to be created by the I.T. Administration, following the requirements of the on-sight external authentication server (Remote Authentication Dial-In User Service = RADIUS).

- Accepted file formats: .pem for the "CA certificate" and .p12 for the "User certificate."
  Installing the WiFi certificates on MVR series devices

- Copy the certificates onto an empty USB stick and connect it to the front USB port of MVR.

- Goto Settings / Connections / WiFi screen and make sure WiFi is connected. Set MVR in Test mode by pressing Ctrl + W using the external USB keyboard.

- Tap on ADVANCED (in right upper corner):, then tap on "Install certificates". The file browser opens. Select your USB stick and search for the folder with certificates for installation.

- Select the CA certificate first and name it.

- Select and install the User certificate, typing and naming the password.

- After the certificates have been installed, connect to your Wi-Fi Enterprise network. Tap on ESC on your USB keyboard to return to the WLAN screen. Select your network from the list of the available networks.

- Follow the procedure obtained from your IT Administrator to connect. Example:
  Follow the procedure obtained from your IT Administrator to connect. Example:
  
  - Choose the EAP method. It depends on the requested settings of your Authentication Server, (In this example “TLS”).
  - Scroll down (“ ↓“ key). After selecting EAP method, Phase 2 authentication.
  - Select a certificate from the list of the installed certificates, if required.
  - Type your identity. The identity is your User Name for the user which was created on your local authentication server (Windows 2012 server or other software used to create the certificate).
  - Tap on CONNECT. Your secured Wi-Fi connection gets established.

- Following information need to be provided to the user: User Account. User Name and Password; Connection instructions. Your personal instructions, after you have successfully tested the connection of MVR / MVR Pro to your secured Wi-Fi.

#### Connecting MVR series device to a hidden SSID

To connect to a hidden SSID, you will need to connect a USB keyboard to the MVR. From the WIFI SETTINGS screen, as shown in your image, press CTRL + W on the keyboard. You will now see the Android WLAN Screen. Tap on Add Network and enter your SSID details. Press escape on the keyboard several times to escape out of the Android menus back to the MVR Pro screens. The new SSID settings will be retained when you power off and on the unit.

## MVR and MTR Time and Date Settings and Clock Keeping

Ensure the correct date, time, and time zone are set. These settings can be done manually. However, the good practice is connecting to the local NTP server to keep time settings updated. We suggest checking the correct date and time before Start of a Study and include this in the checklist to prepare for the surgical operation.

### Manual Setup of the Date, Time and Time Zone on MVR and MTR series devices

To set up Date and Time manually, tap on the Calendar icon in the top right corner of the Start screen. Calendar icon will be shown when Date or Time is suspected to be incorrect. Alternatively, the Date and Time setup screen can be reached from Settings/System/Date and Time. Ensure you entered the correct Year, Date, Time, and Time Zone, and tap the Set button to confirm. Users can select the Date format from 3 options on the Date and Time setup screen: YYYY-MM-DD, DD/MM/YYYY, or MM/DD/YYYY. The selected date format will be used in the Start screen, Time Stamp, Archive screen, Report, and Patient data edit. The Date and Time setup screen will be displayed automatically when time loss is detected upon power on the MVR device and on the attempt to start the Study with an incorrect Date and Time. MVR device can maintain the clock running without external power for the fully charged time-keeping battery for around a week. Keep the MVR device powered for at least 8 hours to ensure full charge of the time-keeping battery. When the MVR device is not used regularly and powered on for short periods, like 1-2 hours a day, users may often experience date and time loss after power on the MVR device.

### NTP – Set Network Time Protocol for MVR and MTR series devices

The best way to maintain the correct date and time is to connect the MVR recorder to your internal network (LAN or WiFi). NTP, or Network Time Protocol, is a protocol used for synchronizing the clocks of computers on a network to a standard time reference. NTP allows for accurate time-keeping across different devices and systems, which is essential for various applications, including the time and date of the imaging Study.

To use NTP, MVR device must be configured to connect to an NTP server, which is a device that broadcasts accurate time signals over the network. There are many public NTP servers available on the internet that can be used for free, or an organization may choose to set up its own internal NTP server over a local network.

MVR will pick up an existing local NTP server automatically in most cases. It is possible to set an IP address and port of NTP in Settings/Advanced/Connections/Network/NTP server, for example: 192.168.2.10:123. If there is existing access to the Internet, external NTP can be specified by name, for example, "pool.ntp.org." Tap the Test button to ensure the NTP function works properly - the current date and time from the NTP server should appear green at the top of the screen. Confirm your settings with the Set button.

When in doubt - contact the IT specialist or network administrator about the availability of the NTP server and its address and port.

### USB Time Dongle for Date and Time Keeping on MVR series devices

USB Time Dongle is intended for MVR400, MVR409, MVR420 devices for the timekeeping when devices are used rarely and NTP server is not available.

Order number: DODT001 – Dongle Date Time Note: Firmware FW220602 (or higher) required on the MVR Recorder.

USB Time Dongle Operating Principles

- Provided to customers affected by time loss free of charge
- Plug the USB Time Dongle into the MVR device's rear USB port directly, avoiding USB hubs or splitters
- Check the date, time and time zone are all correct
- The manual time setting sets the time to the USB Time Dongle and the internal clock
- If the MVR device uses a network NTP time server, automatic time updates from NTP will propagate to the USB Time Dongle
- When after powering on, the MVR device detects internal time lost, it will automatically restore time from the USB Time Dongle
- If after power on, the internal time is different from the Dongle time and both have valid values, the time and date from the USB Time Dongle are used and set to the internal clock because the USB Time Dongle has better time accuracy by the hardware design

### I am experiencing frequent loss of date and time on the MVR device.

- Keep the MVR409, MVR420 device running for at least 8 hours daily to allow the clock to run for the following week without external power.
- Connect to Network and setup the NTP server - MVR device will synchronize with the NTP server at every power on.
- When the above conditions cannot be met - contact MediCapture to obtain USB Time Dongle.

## AK4K Feature Activation Key Specifications for MVR series devices

### Product Information

- Product name: AK4K
- Product type: Digital code for feature activation
- Product description: Activation key for 4K video recording for MediCapture MVR series and MTR series medical video recorders.
- Product grade: None
- Medical device classification: None

### Compatibility

- Compatible MediCapture medical video recording devices: MVR Pro (MVR409), MVR (MVR420), MVR Lite (MVR400), MVR435, MVR436, MVR450, MVR460, MTR133, MTR156.
- The activation key is specific to the particular MVR device identified by the Device ID and will not work with other devices.
- To be compatible with MVR Pro (MVR409), MVR (MVR420), MVR Lite (MVR400), your camera equipment should provide a signal on HDMI in 2160p30. Other models accept 2160p60 video signal over HDMI or DP (Display Port).
- If your camera equipment outputs 4x 3G-SDI in Quad-Split (Square Division) or 2-Sample Interleave format 2SI, MediCapture's additional item MVC Pro HDMI to SDI will convert your SDI-signals to HDMI.
- If your camera equipment outputs 12G SDI video signal, models MVR450 and MVR460 can accept it directly, other models require additional SDI to HDMI converter. Recommended models from the https://www.blackmagicdesign.com/ are: Teranex Mini SDI to HDMI 12G for models MVR Pro (MVR409), MVR (MVR420), MVR Lite (MVR400); Micro Converter SDI to HDMI 12G for other models.
- Some MVR/MTR model variant may come with the AK4K pre-activated. You can find the AK4K code at the labels on the device, IFU (Instructions for Use) and device package box.

### Usage

- Installation: not required.
- Activation: In advanced device settings Activation Keys menu, enter digital code to activate 4K recording features. The word 'Unlocked' will be displayed next to '4K recording' in case of success. Feature work automatically after activation.
- Available after AK4K activation: Ability to select 2160 lines video recording resolution in the Storage Settings screen.

### Advantages

- Advantages of upgrading: Gain the ability to record video at the highest UHD resolution
- Advantages for reliability: Can be re-activated any time without extra charge

### Video Recording Resolution

- Without AK4K activation: Limited to maximum resolution 1920x1200
- With AK4K activated: 4096x2160 and 3840x2160p

### Resolution of Captured Images

- Always the same as the input resolution, with and without AK4K activated.

### Certification and Compliance Standards

- Medical equipment safety: Not applicable
- Electromagnetic compatibility EMC: Not applicable
- Other certification and compliance standards: Not applicable

### Ordering and Pricing

- Ordering code: AK4K
- Required information: MVR device Serial Number and Device ID which is shown on Information screen.
- Package content: 8-digit hex code number
- AK4K price: Contact MediCapture

### Troubleshooting

Some procedures, like Reset to Factory Defaults, will erase Activation Keys. It is recommended to keep record of your purchased keys or add a sticker to a device listing Activation Keys.

If Activation Key is lost - contact MediCapture representative to help recover it free of charge; you will need to provide Device ID and purchase information.

## Cleaning and Disinfection

### Disinfection instructions:

- Before disinfection, the device must be cleaned to remove debris. Debris can be removed with a dry, clean cloth.
- Disinfectant/sterilant: U.S. Environmental Protection Agency (EPA) approved disinfectant/sterilant or U.S. Food and Drug Administration (FDA) approved disinfectants may be used.

### Manufacturer recommended disinfectants:

- Ethyl Alcohol, 70%.
- Becton Dickinson BD Alcohol Swabs – 70% Alcohol Preps.
- Pour approximately 5ml of ethyl alcohol on a sterile cotton swab.
- Swipe the surface area of the device, being careful not to come into contact with any electrical connections on the back faceplate or the USB ports on the front faceplate.
  IMPORTANT! Make sure that no humidity enters the device. Do not use any cleaning agents, scouring agents, or solvents on this device.
