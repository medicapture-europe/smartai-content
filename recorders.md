# MediCapture MVR/MTR Medical Video Recorders

*by MediCapture Inc.*

## Overview

MVR-series of MediCapture medical video recorders consists of models **MVR400, MVR409, MVR420, MVR435, MVR436, MVR450, MVR460**. MTR-series of MediCapture medical touch-screen video recorders consists of models **MTR133, MTR156**.

The MVR/MTR-series devices are intended to record video and images from various medical imaging systems, like endoscopes, microscopes, ultrasound systems, and other medical and dental cameras over HDMI, DP (Display Port), DVI, SDI, or USB UVC interfaces. Features include live preview, live streaming, video recording, image capturing, editing of the recordings, creating and printing customized reports, sending recordings and reports to PACS over the DICOM interface, sending to NAS, and obtaining the MWL DICOM worklist. (Note: actual video input interfaces differ between models — see details below.)

MSP-series of MediCapture Smart Control Panels includes models MSP156, MSP156W and MSP245W. Intended use: Serve as a secondary user interface (touchscreen) for the remote monitoring and operation of compatible external medical devices that provide a web-based user interface (HTTP/HTTPS) via a local network (LAN).
MSP156 shares the same physical properties as MTR156, and MSP245(W) shares the same physical properties as MTR245, except of the software functionality: no access to the Internal Storage, no recording/Study/patient_Info/worklist, no review/archive/report/PACS/DICOM features. Typical usage: run external web apps to control external devices. 

## Operation Workflow

Typical workflow of MVR/MTR device operation:

1. Start the device.
2. Start a new Study by entering Patient Information, procedure description, and physician name.
3. During the Active Study: capture images, record videos, and review recordings.
4. Finish the Study, confirm the automatic export of recordings, and print the auto-generated report.
5. Archive recordings: edit and annotate images and videos, generate and print reports, and send recordings to NAS or PACS.
6. Change device Settings when necessary.
7. Power off the device.

### Start Device

The typical start-up procedure is to supply power to the device — the device boots within 45 seconds, after which a new patient folder can be created. The front LED ring(s) enclosing the button(s) flash, and the MediCapture logo is displayed during the boot sequence. The device is expected to remain powered on (constant operation), allowing recordings to be taken instantaneously at any time. After booting, the Home screen is displayed, offering three options: **Start, Archive, and Information**. When User Accounts are enabled, correct credentials must be entered to get access to the device.

### Start New Study

Tap the **Start** button to start a new Study. The Study starts with entering patient information, procedure description, and physician name. A new folder with a unique name is created on the enabled Storage, and all recordings for the current Study will be placed in this folder. Ensure the correct date, time, and time zone are set. Check the correct date and time before the Start of a Study and include this in the checklist to prepare for the surgical operation.

### During the Active Study

**Preview and Select Video Source.** A live image from an external camera is displayed during the active Study and is overlaid with control icons. The icons' position can be re-arranged to a preferred location by swiping with one finger left or right, or hidden by swiping again in the same direction. If more than one camera is connected, the image source can be toggled by tapping the Source icon. Two video sources can be combined in PIP (Picture-In-Picture) or Split View style, enabling simultaneous recording.

**Capturing Images.** Tap the Photo icon to capture the image. The light ring on the front button goes out briefly to indicate image capture. A confirmation sound plays at the current audio output. The sequential number of the current recording is displayed next to the icon. When Image Freeze is enabled, the captured image is shown in a window for a few seconds and minimized to a thumbnail afterwards. Tap the thumbnail to Review current recordings. To trigger image capture remotely, a standard footswitch or any "normally open" switch can be connected to the REMOTE port on the device's rear panel.

**Recording Videos.** Start video recording by tapping the Video icon. A confirmation sound plays; the icon flashes while recording is in progress, and the front-button light ring flashes the same way. The current recording time and sequential recording number are shown next to the icon. Tap again to stop recording (confirmation sound plays). To trigger recording remotely, a second footswitch/normally-open switch can be connected to the REMOTE port via the provided Y-split cable. Images can be captured without interruption during video recording — a Tag is created in the video at the moment of capture, and Tags are also created when the recording is paused, making these events easy to find during Review. Video recording can be paused and resumed multiple times to eliminate unwanted parts (the pause function must be enabled in Video Settings). By default, video is recorded without sound; sound recording and audio source can be enabled in Audio Settings. Date/time text overlay can be enabled over the video signal and is recorded into the video file; patient information can also be added to the overlay, but this is not recommended for privacy reasons. Recordings can be saved to one or two of three storage types: USB, Internal, or Network. Icons of enabled Storages are displayed during the active Study, with a number indicating estimated recording time until Storage is full. Recording automatically stops when there is no free space left. Long recordings are automatically divided into files of 4GB each to keep a manageable file size — this is seamless, and continuous-play media players show no gaps.

**Observing Storage Status.** The current Storage for recordings is represented by one of three distinctive icons for USB, Internal, or Network Storage. Free Storage capacity is displayed under the icon as remaining recording time or storage capacity; toggle the display type by tapping the icon. Remaining recording time is calculated from the selected recording quality/resolution — check it right after Study start to ensure enough free space for the entire Study.

**Web Streaming of the Study.** Streaming allows external viewers to watch live studies with high quality and low latency using a standard web browser. When enabled via the Remote Access screen, the MVR operator maintains complete control — allowing viewers to join, viewing the list of connected viewers, and disconnecting any viewer at any time. (See [Networking](#networking) below for full streaming setup details.)

### Checklist for the Active Study

Before the Study Starts: ensure the correct date, time, and time zone are set. Right after the Study Starts:

* Check the live video source quality.
* Capture and review testing images.
* Record and review a short testing video.
* Ensure the correct Storage is selected for the recordings and that the remaining recording time is sufficient for the entire Study.

### Finish the Study

Tap the Back icon to finish the current Study. A confirmation dialogue offers options to return to the Study or Review recordings before finishing. The Review feature provides an opportunity to ensure all necessary events were captured and to edit, annotate, or delete recordings before automatic export and reporting. Finishing may trigger automatic export of recordings and printing of the auto-generated report. The Archive function allows adding more recordings to a Study after it has been closed — navigate to the Study folder, open it, and tap **Append**.

### Available Features in Archive

The Archive provides extensive post-study capabilities. Users can change the active storage, search studies by patient name or ID, browse and select multiple studies, and back up from Internal Storage to USB. Key functions include editing patient information, generating reports, and deleting empty studies. Within Study Review mode, users can scroll through recordings, select items for report generation, copy, delete, or send to NAS/PACS. The **Append** feature adds new content to closed studies.

Image editing supports annotation, textual notes, zoom/pan, cropping (AOI), and saving edited versions with preserved originals. Video editing provides zoomed playback and panning, adjustable speed, frame-by-frame review, snapshots from video, and trimming/splitting/merging with separate file storage.

Report editing enables layout customization, anonymization modes, branding with institutional logos, and finalization through PDF saving or printing.

### External Web Application

This feature lets users control external smart devices on the local network via the recorder's built-in browser — supporting video switches, camera controllers, and surgical light controllers. Apps appear as a vertical scroll on the Start screen's left side. Custom web applications can be configured by uploading zipped files containing an `index.html` file in the root directory. (Compare with **External Apps** under Advanced Features below, which is the URL-bookmark style browser shortcut feature.)

### Utilizing Portrait Orientation

MTR-series recorders (and compatible MVR models with a portrait-mountable monitor) feature versatile Portrait Orientation (90° or 270° rotation), offering Dual View functionality where the screen is logically split: the top half displays the live camera feed while the bottom half provides UI access or archive browsing. This enables dual-camera operation, live study with archive review, optimization for mobile carts, and external-app integration without losing sight of the live video. See **Dual View in Portrait Screen Orientation** under Advanced Features for full detail.

## Settings Menu Structure

Reference tree of the device Settings menus, for orientation when following setup instructions elsewhere in this document:

**Video/Audio**

* **Video Input:** select/rename Video Input 1 and Video Input 2; select resolution of USB cameras; aiScope model selection; Stamp function in pictures/videos (Off/On, stamp position, patient info to display in stamp: None/Personal ID/All); Picture in Picture (Off/On, position, size: 10%/15%/20%/25%); Split view; Parallel recording.
* **Recording Quality:** Quality (Normal, Super); Codec selection (H.264, HEVC). HEVC (High Efficiency Video Coding) provides the same quality at roughly half the file size of H.264 and is generally recommended, especially for 4K recordings; H.264 offers wider compatibility with older video players but larger file sizes.
* **Recording Options:** Video Time Limit (Off, 1/2/3/5/10 min — recording stops after the limit); Time Lapse Speed (Off, 4x, 12x, 60x, 300x, 900x, 3600x); Pause Function (enable Pause button/function during recording); On-Screen Tally Light; Hold to record; Auto record (Off/On).
* **Photo Settings:** Image Format (JPEG, PNG); Noise reduction (Off/On, demo mode); Freeze on capture (Off/On); Snapshot preview (Off/On, position, freeze seconds: 1–10 seconds).
* **Audio Input Settings:** Volume of system sounds (0–100%); Record audio (Off/On); Audio monitor (sound level indicator); Audio sources (wired microphone, line in, USB microphone, HDMI audio).

**System**

* **Study Info:** Patient Info selection (Off, Human, Veterinarian); Auto start of Study (Off/On); Worklist search and Worklist server setup.
* **Device Info:** Institution name; Department name; Location; Device title; Logo/branding (view, replace, delete; Show logo Off/On, position, size 5–40%).
* **Printer**
* **Display:** Brightness; Pointer Speed (external pointing device); Display rotation (0°, 90°, 180°, 270°); Display size (50–120%).
* **Date and Time:** Time selector; Date selector; Time zone; Date format (YYYY-MM-DD, DD/MM/YYYY, MM/DD/YYYY).
* **Language:** User-interface language (Settings menus remain in English only) — English, German, French, Italian, Spanish, Polish, Dutch, Czech, Swedish, Danish, Finnish, Slovak, Norwegian, Russian, Turkish, Brazilian Portuguese, Japanese, Korean, Thai, Chinese Traditional, Chinese Simplified, Arabic.

**Archive**

* **Storage:** Resolution limit set separately for each Storage type (Internal, USB, Network): 2160p, 1080p, 720p(30), Only images, Off.
* **Export:** Disabled; Export to PACS (PACS server setup, secondary PACS); Export to NAS (NAS server setup); Auto Send (Off/On); Auto Delete after Send (Off/On).
* **Report Settings:** Preview; Header image selection (hospital logo); Image at end of report (signature/stamp); Footer text; Notes text; Page layout; Page size; Auto reporting (Disable, Print, PDF).

**Advanced**

* **Connections > Network:** IP setup — DHCP (Auto) or Static (IP address, Mask, Gateway, DNS); NTP server (IP address:port, Test button).
* **Connections > Network Storage:** Server properties (IP address, folder name, user name, password, label, domain); Personal mode (use logged-in user's credentials); Video resolution limit (2160p/1080p/720p/Only Images — admin limits override user limit); Find a server; Test.
* **Connections > Remote Access:** Remote access (Off/On); Use HTTPS (Off=HTTP, On=HTTPS); Password; Local storage (enable local storage on MVR Remote App device); Remote App download QR code; Web streaming (Streaming Off/On; Always allow — connect without operator confirmation; Enable audio); API access (password for non-blocking API access, allows simultaneous local use and remote API control).
* **Connections > External Apps:** Enable External Apps (Off/On); Default App selector; Add new app ("+"); Add/Edit app fields (Name, Description, Type HTTP/HTTPS, URL, 16:9 forced ratio Off/On, Block screen saver Off/On, Test, Add, Update); list of apps with individual enable toggle.
* **Storage Rules:** Disable USB Storage (Off/On); Internal storage cleanup rules (keep 50GB free, keep last 28 days); Auto delete after sending to NAS or PACS; Allow deleting non-empty Studies (Off/On).
* **Update & Default:** Backup settings to USB stick (Save/Restore); Format USB Storage; Format Internal Storage; Reset settings to default; Reset device to factory default; Update firmware.
* **User Accounts:** User accounts enabled (Off/On); Add user ("+"); LDAP settings (Enabled, Server, Port, Auth path, Naming context, Admin/User/Guest groups, Caching time, Use SSL, Test server, Test user); list of users with Role selection (ADMIN, USER, GUEST).
* **Security:** Renew password (time settings); Inactivity timeout (1–60 minutes or never).
* **Activation Keys:** List of active features; Enter new key.
* **Audit Trail:** List of recent events; Filter events; Export audit log to USB; Erase audit log.

## Software Features

### Main Features

* Record high-quality medical images and videos in High Definition (HD).
* Optional 4K video recording package **AK4K**, enabling video recording in 4K, including a video-signal converter matching the customer's 4K camera signal output type.
* Storage for recordings can be selected from Internal Storage, USB Storage, and Network Storage (NAS).
* Parallel recording: two video inputs can be combined into a single Picture-in-Picture composite video or recorded independently.
* Smart workflow including Study management, patient-information input and editing, video recording with simultaneous image capturing, file archive, review of recordings with the ability to edit/annotate images, create PDF reports, trim videos, copy or delete recordings.
* Manual input of patient data, procedure description, and surgeon name and notes.
* Automatic Video Repair (AVR), ensuring videos are not lost if the recorder loses power or a USB stick is accidentally removed during a recording session.
* USB Storage Disablement feature for health-care facilities with restricted use of removable storage.
* User management.
* Remote control over RS232 using a USB-to-RS232 adapter (not included).
* No measurement features; no calibration is required.

### Traceability of the Recordings

All recordings are traceable to the actual device used to acquire them. The best way to trace MVR devices is by using the **Device ID**, unique for every MVR device and consisting of 8 hex characters. The Device ID can be found on the supplementary label at the bottom of the device and in the INFORMATION screen of the user interface. The device ID also appears in files produced by the MVR recorder in the DICOM tag or the EXIF tags when DICOM is not used.

DICOM standard defines specific tags for various types of information. The Device ID is saved in DICOM tag **(0018,1003)**, and the device firmware version is saved in DICOM tag **(0018,1020)**. Important: to contain all information, DICOM files must be produced by the MVR device itself, using "Send to PACS" or "Copy as DICOM." If plain JPG/MP4 files are copied and later converted to DICOM externally, device and patient information will be lost.

EXIF information of captured images and video recordings also contains the Device ID and firmware version. Metadata in images (JPG/PNG) is stored in the EXIF data structure; since the EXIF standard does not define a DeviceID field, the MVR model and Device ID are stored in the "Model" tag, e.g. `"EXIF:Model": "MVR Pro 20bd4b50"`.

Metadata in video files is included as QuickTime MP4 tags — the "Composer" tag is used: `"QuickTime:Composer": "MVR DeviceID"`.

The device's Serial Number is only printed on the label and is not traceable in software. Use the Device ID (also printed on the supplementary label) for traceability instead.

### Video Input Signal Settings

Two options for video input signal settings: **BT2020** and **Extended Color Range**.

* BT2020 and color range options are set per camera.
* Only 4K cameras can output BT2020 color; typically 4K cameras are connected to HDMI 1.
* Once the BT2020 color gamut is enabled, still images and videos are recorded with color space set to BT2020.
* Only some viewers support the BT2020 color gamut; it will display in default BT709 gamut when BT2020 is not supported.
* While reviewing on the MVR device itself, there is no visible difference with BT2020 enabled or disabled — it is displayed in BT709.
* Select the color range "extended" to match a specific camera; when unsure, keep "normal."
* Technically, extended range means 0–255, while normal range is 16–234 for 8-bit colors.

### Network Features

Connection to a wired or wireless network enables:

* Recording to Network Storage (NAS) or Send to NAS.
* Video and audio streaming.
* Integration with hospital information and imaging systems via the optional DICOM upgrade package **AKDICOM**.
* Remote control over the network from a web browser, tablet, or smartphone with the MVR Remote App or API.
* The ability to connect wireless BT devices: BT headsets for audio recording, BT HID devices for the UI.

### Video Playback Speed Control

* Selectable video playback speed: 0.1x to 10x.
* Speed steps: 0.1x, 0.2x, 0.3x, 0.4x, 0.5x, 1x, 2x, 3x, 4x, 5x, 6x, 7x, 8x, 9x, 10x.
* Speed control buttons look like "<<" and ">>"; during Pause, these change to "<1" and ">1" for frame-by-frame stepping.
* Touch button functions are duplicated by the "-" and "+" keys: short tap reduces/advances speed by one step; long press jumps to the slowest/fastest value.

### Video Edit Feature

Allows selecting several segments from the original video recording and saving them as a new video containing only the desired parts. **Not available for MVR Lite (MVR400).**

**Quick manual:**

1. Press the "video edit" button (scissors icon) in the video player. The player changes into an editor with additional controls.
2. The primary tool is an axis with time segments below the seek bar. Each segment is drawn in yellow with start/end thumbs, representing the time range that will be included in the new video file. Initially, one segment covers the entire video duration.
3. Edit the segments as needed using the provided controls.

**Editing controls:**

* Drag the start or end thumb of a segment to change its time range.
* Merging adjacent segments is possible by dragging their ends together.
* Click a segment to select it, then click the delete button to delete it.
* Click a segment to select it, then click the cut button to split it into two parts. Two modes: if the seek bar is positioned in the segment, the cut is done at the seek bar position; otherwise the segment is cut at its center.
* To create a new segment, click empty space below the seek bar (not occupied by another segment) and move/touch left or right — a new segment is created.
* Fine-tune a selected segment thumb's position using the blue previous/next buttons on either side of the seek bar.

**Notes on editing:**

* Segment start/end times can be positioned only on keyframes (a special frame type occurring at drastic picture changes or roughly every 5 seconds), so granularity of selectable start/end times is about 5 seconds.
* Each tag in the video (created by image capture) also contains a keyframe, so a cut can be positioned precisely at the tag.
* Zooming is not possible in the video editor; the saved video keeps its original resolution.
* The edit area (below the seek bar) shows information about the selected segment and the total time of all segments (= final clip length).
* The play button previews the final video; the seek bar still shows the original timespan but with defined segments, and seeking in preview works only within segments. Fast skip forward/backward uses the blue buttons as usual; press Pause to stop preview and return to the editor.
* **Saving:** the button in the top-right saves the final video into the same folder as the original, with an appended incremented counter. A new file is created every time Save is used. The save button shows a yellow asterisk to indicate unsaved changes; exiting with unsaved changes prompts a save dialog. Cut positions are preserved in the resulting video as tags, visible in the player.

### Merge Selected Video Files into a Single Video

From the Review screen: select several videos and click the Edit button. The files appear in the editor as one continuous video with green tags marking the start of each source video. Portions can be cropped out as during regular video editing, a preview of the result is available, and the result can be saved as one continuous video file.

**Limitations:** the result file cannot exceed 4GB; all source videos should be recorded with the same settings (codec, resolution, bitrate, audio, etc.).

## Advanced Features (Firmware-Specific)

### External Apps

**Applicable models:** MVR435, MVR436, MVR450, MVR460, MTR133, MTR156. **Available since:** FW 250603. **Category:** New feature. **Workflow stages:** Start screen, Settings.

**Purpose:** Enables control of external smart devices on the local network via a built-in web browser, such as a video-switch matrix, intelligent camera controller, surgical light controller, etc. This feature is intended to control video sources — smart camera controllers, video switches, routers — over the web interface, or to provide web help/guidance for device operation.

**Usage.** An external app is a browser window with a preset URL — essentially a shortcut to a specific website or web application. When enabled, a vertical scroll of external apps is available on the left side of the Start screen; tap an app icon to open a browser window. Navigation works like a regular web browser; external apps behave like browser tabs. Closing the window with the "X" in the top-left keeps browsing progress in the background — reopening the same app resumes from the same point. Background activity remains active until the user logs out or the device restarts.

The browser window starts with the upper navigation bar hidden — scroll down to reveal it. Tap "Reload" in the header (right side, next to the app icon) to refresh the page; tap "<" in the right corner to browse back.

To set up and customize the app list: **Settings > Advanced Settings > Connections > External apps**, then tap the "Enabled" slider. Tap "+" in the header to add a new app, or tap an existing app to edit it. Select type HTTP or HTTPS, then enter the URL (e.g. `www.medicapture.com`) or an IP address/port for a local smart device (e.g. `192.168.2.13:3333`). "Test" opens the built-in browser with the specified URL; "Update" saves changes; "Remove" deletes the currently selected app.

The app icon is auto-fetched from the website by searching for a `favicon.ico` link on the landing/root page; if none is found, a default "Globe" icon is used. Each app can be enabled/disabled individually via its "Enabled" slider. The list order can be changed with "^"/"v" buttons to move an entry up or down. One app can be selected as the default home app, launched automatically once the device starts and the user logs in (selectable from the drop-down at the bottom of the External Apps settings screen). In Portrait orientation, an External App can run under the live camera view in the bottom half of the screen.

### Support for Multiple USB Cameras

**Applicable models:** MVR435, MVR436, MVR450, MVR460, MTR133, MTR156. **Available since:** FW 250603. **Category:** New usability feature. **Workflow stages:** Live Study.

**Purpose:** Enable simultaneous use of two USB cameras.

**Usage.** Up to six USB cameras can be connected simultaneously, enumerated as "USB camera", "USB camera 2", "USB camera 3", and so on. All connected USB cameras appear in the list of available inputs on the "VIDEO INPUT SETTINGS" screen — select the camera first, then the desired resolution. Video settings (resolution, Area of Interest) are stored automatically per camera.

Adding new cameras, changing USB ports, or adding a hub alters camera enumeration. Connect all USB cameras before powering on the device and keep them connected at all times — plugging/unplugging live can be confusing. If the physical connection changes, reboot the device and re-check selections/settings.

When two USB cameras are used simultaneously (PIP, Split, Dual View, Parallel recording), connect one camera to the USB-C port and the other to a USB-A port. If both cameras are on USB-A ports or the same hub, simultaneous use is possible only at lower resolutions, typically 720p30 and below, due to USB bandwidth limits (especially with USB 2.0 cameras). When USB cameras are used separately (single-source Live Study recording), there is no port/hub limitation.

### Custom Logo Stamp

**Applicable models:** MVR435, MVR436, MVR450, MVR460, MTR133, MTR156. **Available since:** FW 250415. **Category:** New branding feature. **Workflow stages:** Study.

**Purpose:** Enable branding of recordings and the live view with a hospital, system, or personal logo. The logo stamp shows during Live Study and is recorded in videos and captured images when enabled.

**Usage.** Logo settings are at the bottom of the "PATIENT INFO SETTINGS" screen. Copy the custom logo image (JPG or PNG) to a USB flash stick and plug it into the device's USB connector; tap "Pick" and select the file. To replace the logo, tap "View", then select "Replace" or "Delete" from the pop-up menu and choose the desired file. Tap "Show logo" to enable the overlay. Select the logo position relative to the Area Of Interest (AOI): top-left, top-right, bottom-left, or bottom-right. Logo size is adjustable via a "Size" slider from 5% to 40% of AOI vertical size, in 5% increments; set size/position so it does not overlap the date stamp.

### Dual View in Portrait Screen Orientation

**Applicable models:** MVR435, MVR436, MVR450, MTR133, MTR156. **Available since:** FW 250326. **Category:** New usability feature. **Workflow stages:** Study, Archive, Settings.

**Purpose:** Enable comparison of two cameras — live (real-time) camera view alongside a previous recording, or comparison of two recordings. Example applications: reviewing "Before"/"After" footage, or looped playback of a fluorescence/ICG (IndoCyanine Green) video as a reference alongside live surgery footage.

Some recorders on the market support simultaneous recording/review of two video channels using the standard landscape layout with two small preview windows. MediCapture's solution instead maximizes screen usage by taking advantage of portrait orientation. Dual View is compatible with all new device models, though some are more suitable than others — the MVR460's built-in 7-inch touchscreen is too small for effective dual-view interaction and unsuited to portrait mounting. Suitable setups are MTR156 and MVR450 or MVR436 with an MTS156 monitor; MTR133 can be used where device size is restricted.

**Usage.** Change screen orientation to Portrait: **Settings > System > Display**, set Display rotation to 90 or 270 degrees. An external monitor (MTR156 or another model) should be mounted in portrait orientation. Dual View is enabled automatically, with more options shown at the bottom of the screen. Typically the screen splits vertically in half between two views, but the top view occupies 75% of the screen area when no selection is made for the bottom view; the size ratio is automatic and not user-adjustable. Both views can be interacted with simultaneously via touchscreen and operate independently in principle.

During the Live Study, several options can be shown at the bottom of the screen under the live footage: another camera, or an Archive. For example, live footage from a microscope camera can be compared to recorded footage from a fluorescence camera captured minutes earlier. When two cameras are shown live, recordings can be made independently for both unless Parallel Recording is enabled. The bottom camera shows fewer controls: a Capture and Record button and an "X" to close its live view. Top and bottom cameras can be swapped by tapping the Input select button (marked "1/2").

The archive screen allows review of another Study under the currently selected Study — the same Study, a Study recorded at a different time, or from a different storage location (e.g. Internal Storage compared to Network Storage). In both views, images and videos can be played, edited, or zoomed independently at the same time; when both videos have soundtracks, both play simultaneously. All controls/interactions match the regular single-view mode. This allows comparison between "before"/"after" footage or footage from different cameras/patients. Portrait orientation also allows larger report previews in portrait layout.

### WiFi Connectivity Using USB Adapters

**Applicable models:** MVR436, MVR450, MVR460, MTR133, MTR156. **Not available for MVR435.** **Available since:** FW 250326. **Category:** Connectivity. **Workflow stage:** Settings.

**Supported USB WiFi adapters:** ASUS USB-AC58.

**Purpose:** Enable wireless connectivity for MVR/MTR devices. **Note:** log in as Administrator, which is required to perform Network Settings.

**Usage.** Connect the USB WiFi adapter while the device is powered off. Only one adapter can be used at a time. The LAN cable must be disconnected — an active wired LAN connection disables wireless connectivity. Power on the device; navigate to **Settings > Advanced > Connections > Network > Network Settings**, then tap "More settings" to reach the system Internet settings. (Hint: tap and hold the LAN icon on the INFORMATION screen for quick access to Network Settings.)

Tap the Wi-Fi slider to enable WiFi; the list of available networks appears. If the enable slider turns itself back off, the WiFi adapter is not connected or not supported — connect the supported adapter and reboot. Tap the desired network and enter the password to connect; tap "Advanced options" to set a static IP and other parameters. Confirm the status shows "Connected."

Return to device settings and check the wireless connection status on the INFORMATION screen — the WiFi icon appears under the wired LAN status with the current wireless IP address. Tap the WiFi icon to view available networks, change the connected network, adjust settings, or turn WiFi off. Network settings are saved automatically, and the device reconnects to WiFi at next power-on.

### Video Mode Menu

**Applicable models:** MVR435, MVR436, MVR450, MVR460, MTR133, MTR156. **Available since:** FW 250323. **Category:** Usability improvement. **Workflow stage:** Live (real-time) Study.

**Purpose:** Quick access to video-compositing features — Picture-in-Picture, Split View, and Parallel recording.

**Usage.** Tap and hold (over a second) the Input select button (marked "1/2") until the video mode menu appears. Select the desired combination of two video inputs — Split View or Picture in Picture — or choose Parallel recording to record both inputs to separate files. Selecting Picture in Picture opens a sub-menu for its position: top left, top right, bottom left, bottom right, or disabled. Selection applies immediately and the current video layout updates.

### On-Screen Indicator Tally Light (OTL)

**Devices:** MVR-series and MTR-series. **Available since:** FW250119. **Category:** Usability improvement. **Workflow stage:** Live (real-time) Study.

**Purpose:** Provide a clear visual indicator of active recording. The video icon indicating active recording is small and hard to see from a distance on a small screen, and MTR devices have no front LEDs, so users otherwise rely on that small icon alone.

**Usage.** OTL is disabled by default; enable it on the Settings screen, Recording Options, by tapping the "On-screen Tally Light" slider. OTL appears when recording is ON (constantly on, no blinking) as a green rectangle with the text "REC". It blinks once for 1 second during still-image capture (a negative blink — the whole green rectangle turns off briefly — while recording is ON).

OTL size can be adjusted by tapping on it: a "Recording Indicator" pop-up offers 11-step sliders for width and height. Tap Close to complete adjustment; size is saved automatically and applied at device start. Swiping icon positions also changes OTL's position (it is positioned over the Back button); hiding icons hides OTL. On small-screen devices, OTL can be adjusted to nearly fill the screen for clear visibility from a distance — useful when a primary surgical monitor is available and the device's small screen serves purely as a recording indicator. OTL does not cover control buttons.

**External Tally Light:** the "Scroll Lock" LED of a standard keyboard is used to indicate the recording function, with the same logic as the on-screen tally light.

### Area of Interest (AOI)

**Devices:** MVR-series and MTR-series. **Available since:** FW250119. **Category:** Usability improvement. **Workflow stage:** Live (real-time) Study.

**Purpose:** AOI lets users select a rectangular area of the screen to be captured in images and videos, improving workflow efficiency. This is especially useful for endoscopes, whose active image area is typically a circle at the center or side of the screen, with black or camera-setting content elsewhere that is usually undesired in recordings/reports. Without AOI, a doctor would otherwise copy images to a PC and crop them manually using PC tools each time — unproductive when the crop area is always the same.

**Implementation details.** To activate, tap and hold (over a second) on the live screen until guiding symbols appear; the area outside the AOI dims slightly.

* Change AOI size by dragging a circle symbol in the top-left or bottom-right corner.
* Move the AOI rectangle by dragging the four-arrow symbol.
* Confirm the selection by tapping "✓"; cancel (deactivate) by tapping "X".
* A cross mark in the AOI center helps position it accurately.
* All images and videos capture only the selected AOI; coordinates are saved automatically for future use.
* The AOI cannot be changed during the recording process.
* AOI is set independently for each of the two input video channels, and is also used during PIP and parallel recording.
* Stamps, overlays, and PIP are all aligned to the AOI.
* AOI settings do not affect the live Study preview or streaming (Live shows as before) — AOI only affects image/video capture; visually, the area outside AOI is slightly dimmed.

**FAQs**

* **Can AOI be deactivated if no longer needed?** Yes — long-press the Live screen to invoke the guide symbols and tap "X" to deactivate. AOI is always technically active and covers the full screen by default; when "enabled," it covers only a portion.
* **Can AOI be applied to previously captured images or videos?** No — AOI applies only to recordings taken while it is active.
* **Does AOI affect quality or resolution of captured images/videos?** No — recordings use all original pixels within the AOI area. However, if AOI resolution exceeds the Storage Settings limit, final recordings are scaled down to that limit.
* **How does AOI work with multiple video sources?** AOI is defined individually for each of the two input video sources.
* **How to save AOI settings as default for future use?** AOI settings are saved automatically for future use of the current video source on this device.
* **How to change the AOI shape (e.g. rectangle to circle)?** AOI can be defined only as a rectangle.

### Split View (SV)

**Devices:** MVR-series and MTR-series. **Not applicable for MVR, MVR Pro, MVR Lite.** **Available since:** FW 250126. **Category:** Usability improvement. **Workflow stage:** Live (real-time) Study.

**Purpose:** SV allows simultaneous display and recording of two camera inputs side by side for procedures requiring simultaneous use of two video cameras, such as video-laryngoscopy-assisted bronchoscopy intubation for difficult airways, or ultrasound-assisted laparoscopy. Each camera input is scaled to fit half the screen without cropping any content.

**Implementation details.** Storage Settings determine SV resolution; if multiple storages are enabled, the highest resolution setting is used. When Storage Settings are set to "Only images," the default 1920x1080 resolution is used for SV. After the SV resolution is determined (e.g. 1920x1080), the relevant AOI is applied to every camera input first, then automatically scaled to fit half the SV screen (e.g. 960x1080). Black bands may be added horizontally or vertically when the AOI aspect ratio differs from the half-screen aspect. A fixed, non-adjustable vertical separation line in the center defines each camera's view area. The AOI of each input channel can be adjusted with a long touch on the image (see AOI feature above).

The SV screen updates at the frame rate of whichever camera reports the highest frame rate — SV framerate equals the fastest attached camera's framerate. Recordings are saved at the SV resolution and framerate as shown on screen. Sound can be chosen from any audio source in Audio Settings. Cameras can be swapped left/right using the on-screen input-select button. When a camera has no signal, its SV area is black.

SV cannot be used simultaneously with PIP (Picture-in-Picture) or Parallel Recording. SV is intended for two cameras — half the screen is black if activated with only one video source. SV is activated from **Settings > Video Input Settings** by tapping the Split View slider.

**FAQs**

* **Does SV support a vertical layout (cameras stacked instead of side-by-side)?** No — for an uncropped vertical layout of two cameras, change screen orientation to portrait and use the Dual View feature.
* **Can each camera's view size be adjusted individually in SV?** No — use PIP when a smaller image is needed.
* **What happens when the two cameras' resolutions differ?** Yes, resolutions and framerates can differ between the two cameras — each is automatically scaled to fit half the SV screen.
* **Can each camera's feed be saved separately in SV mode?** No — use Parallel Recording to save each camera's feed separately.
* **Can SV be used with more than two cameras?** Only two active video input channels can be selected for SV, though some MVR/MTR devices allow several video sources per input channel.
* **Is it possible to get rid of the black bands?** Adjust each camera's AOI to fit half the screen without black bands.

### On-Screen Keyboard

A new on-screen keyboard (Gboard) is available since FW 250126, enabling support for Asian languages and more. Tap the icon in the top-left corner to show the keyboard control menu — the keyboard's style, size, and position can be adjusted, and it can be made to float. Tap the Settings icon to bring up the keyboard settings screen. Add an input language by tapping "Add keyboard" and use the search tool to find it among hundreds of options. The on-screen keyboard layout can be changed to another language by tapping the Globe key.

### Snapshot Preview and Freeze on Capture

Configured under **Video/Audio > Photo Settings**.

* **Snapshot preview:** the captured image is shown for a few seconds (adjustable from 1 to 10 seconds) in a corner of the main screen (any one of 4 corners can be selected).
* **Freeze on capture:** freezes the live image after taking a snapshot; does not affect video recording. Press Capture again to unfreeze — the freeze has no time limit and requires a manual second tap to resume the live view.
* **Combined:** enabling both "Freeze on capture" and "Snapshot preview" produces a full-screen freeze, limited by the "freeze seconds" duration (1–10 seconds).

### Auto Study Start and Auto Recording (Black-Box Mode)

Configured under **System > Study Info** (Auto start of Study) and **Video/Audio > Recording Options** (Auto record).

* **Auto start of Study:** automatically initiates a new Study once the device is ready after power-on and a video input signal is available. This requires the Patient Info setting to be "Off" (ensuring automatic recordings contain no identifiable personal data). When a Study is finished manually, it will not restart automatically until the next power-on.
* **Auto record ("black-box" mode):** when enabled, video recording begins automatically as soon as a new Study starts and a video input signal is detected. Auto recording saves directly to Internal Storage in HEVC 720p30 format, at an approximate bitrate of 2 Mbps — roughly 0.9 GB of video per hour. If the camera signal is lost or disconnected, the current auto-recording file is immediately saved and closed; a new file automatically starts once the signal is restored. If a video recording is triggered manually, it overrides these auto-recording defaults and records using the custom quality/storage settings instead. Old recordings are removed automatically according to the Internal Storage auto-cleaning rules (see Storage and Archiving below).
* Combining Auto Study Start with Auto Record enables completely unsupervised, continuous "black-box" style documentation.

### Remote LDAP Authentication

**Applicable models:** MVR435, MVR436, MVR450, MVR460, MTR133, MTR156 and newer. **Introduced since:** FW 250225. Available free of charge as a core security feature for new devices and via firmware update for devices already in the field.

**Description.** LDAPS (Lightweight Directory Access Protocol Secure) is a protocol for accessing and managing directory information within a network — think of it as a phonebook, but for users, computers, and other resources rather than names and numbers. It allows access to the MVR/MTR device using authentication over a central directory such as Active Directory. A central authority can grant access by assigning users to specific groups (e.g. "MVR operator"), including existing group assignments such as "surgeons, nurses." Hospitals increasingly specify LDAPS as a central user-management requirement (potentially becoming mandatory); a typical requirement is Azure AD authentication with 2FA, though a simplified LDAPS flow is accepted for devices without a browser.

MVR implements **Role-Based Access Control (RBAC)** to protect access to data over hospital networks and to local recordings. Three roles are defined:

* **Guest:** limited to accessing the Archive for review only, and the live video stream; no access to the MVR device or its data.
* **User:** access to the MVR device to record, review, and document video content, and to view the live video stream.
* **Admin:** all of the above, plus device settings, user management, and device maintenance.

**LDAP Administrator Workflow.** Before setting up the device, coordinate with the central LDAP administrator to obtain:

* LDAPS server URL or IP address.
* Port number, if different from the default port 636.
* Naming context, e.g. `cn=accounts,dc=demo1,dc=freeipa,dc=org`.
* Several test users, e.g. `mvrAdmin1, mvrAdmin2, mvrUser1, mvrUser2, mvrGuest`.
* An example full DN for user authentication, e.g. `uid=mvrAdmin1,cn=users,cn=accounts,dc=demo1,dc=freeipa,dc=org`.
* Three groups — `mvradmins, mvrusers, mvrguests` — corresponding to roles admin/user/guest (existing groups can be reused), with example full group DN, e.g. `cn=mvradmins,cn=groups,cn=accounts,dc=demo1,dc=freeipa,dc=org`.
* Users added to their respective groups (e.g. mvrAdmin1/mvrAdmin2 → mvradmins; mvrUser1/mvrUser2 → mvrusers; mvrGuest → mvrguests).

**Workflow on the MVR/MTR device.**

1. A user enters credentials (user name and password) on the login screen.
2. The device tries to bind (authenticate) the user to the remote LDAPS server. If binding succeeds, an LDAPS search determines whether the user belongs to a particular group. After all checks pass, the LDAPS connection is closed and the user gains access.
3. Logout is automatic by timeout or by tapping the logout button.

The LDAP(S) implementation does not require a special service account and does not store a bulk copy of LDAP user information — every user is authenticated individually, no other information is read/stored from the LDAP server, and the connection is closed immediately after each login attempt.

**Offline Authentication.** Upon successful LDAPS authentication, the user is added to a local list for offline authentication with a timeout, configurable from 0 to 10,000 hours (default **168 hours**, one week); when the timer expires the user is deleted. Offline authentication is used only when the LDAPS server is unreachable — relevant because MVR/MTR devices are often mounted on mobile surgical towers that move between operating rooms and may be disconnected from the network mid-procedure. When LDAPS is online, authentication and group checks are enforced normally; successful authentication resets the timeout, while failed authentication (rights revoked centrally) deletes the user immediately regardless of timeout. The admin can manually review and delete users from the list at any time, same as local user management.

**MVR Admin Workflow: LDAP Server Setup.** Fields on the LDAP server setup screen:

* **Enabled:** turn on to enable the LDAP server and allow editing other fields.
* **Server:** URL or IP address of the remote LDAP server.
* **Port:** port number; leave blank for default (389, or 636 with SSL).
* **Use SSL:** enables secure LDAPS (recommended).
* **Naming context:** appended to the "Auth path" for user authentication and to group paths for group search; auto-populated after a server Test, editable for extra context. A warning "Authentication is required" appears if the server does not allow anonymous binding — in that case enter Naming context manually.
* **Auth path:** optional extra path when the full authentication path is longer than the Naming context.
* **Admin groups / User groups / Guest groups:** determine user role. groupDN is built from a group path + Naming context. Leave empty to disable a role entirely; use `*` to allow that role for any authenticated user (e.g. any valid credentials → Guest). Group checks run top-down: Admin, User, Guest — a user in multiple groups gets the highest-priority role.
* **Caching time (hours):** how long a logged-in LDAP user can log back in while the device is offline. Default 168 hours (one week); enter 0 to disable offline authentication.
* **Cancel:** returns to the previous screen without saving.
* **Test:** performs an anonymous authentication test using Server/Port/Use SSL; a server that disallows anonymous binding responds "Authentication required" (which still confirms successful reachability).
* **Test user:** performs user authentication and group checks.
* **Save:** must be tapped to persist all changes.

Recommended setup flow: input Server/Port/Use SSL and tap Test; edit Naming context, input optional Auth path, and tap Test user; input group paths and Test user again for each role; finally tap Save.

**Test examples.** User Accounts must be enabled first (Settings > Advanced > User Accounts) with at least one Admin user created and verified by logging in immediately after creation. Then, from User Accounts, tap the "LDAP" button in the top-right corner and turn on "Enabled".

*Public test server 1 — `ldap.forumsys.com`* (basic, persistent, read-only test server): Server `ldap.forumsys.com`, Port default (empty), Use SSL: no. Tap Test to verify connectivity. Naming context auto-populates as `dc=example,dc=com`. Test user credentials `tesla/password` (tick "Show password" to verify input); with `*` in Guest groups, the result is "User: tesla. Role: GUEST". Three test groups exist: `ou=scientists` (einstein, galileo, tesla, newton), `ou=mathematicians` (euclid, riemann, euler, gauss, test), `ou=chemists` (curie, boyle, nobel, pasteur) — the password for all users is "password"; user "nogroup" belongs to no group. Setting User groups to `ou=scientists` and testing `tesla/password` again yields "Role: USER". Setting Admin groups to `ou=chemists` and testing `nobel` yields "Role: ADMIN".

*Public test server 2 — `ipa.demo1.freeipa.org`* (works with SSL on or off; not persistent — resets daily at 05:00 UTC): after Test, Naming context auto-populates as `dc=demo1,dc=freeipa,dc=org`; edit it to `cn=accounts,dc=demo1,dc=freeipa,dc=org`. Example full DN: `uid=admin,cn=users,cn=accounts,dc=demo1,dc=freeipa,dc=org` (built from user `uid=admin` + Auth path `cn=users` + Naming context). Example group DN: `cn=employees,cn=groups,cn=accounts,dc=demo1,dc=freeipa,dc=org`. Set Auth path to `cn=users`. Test users: `manager, helpdesk, employee, admin`, all with password `Secret123` (user names are not case-sensitive; passwords are). Testing `ManageR/Secret123` returns "User: ManageR; Role: GUEST"; testing the wrong-case password `ManageR/secret123` fails with "Error: invalid credentials". Setting Admin groups to `cn=admins,cn=groups` and User groups to `cn=employees,cn=groups` (group membership is checked against LDAP attributes `member`, `uniqueMember`, and `memberUid`): testing `admin` → "Role: ADMIN"; `manager` → "Role: USER"; `helpdesk` → "Role: GUEST". Remember to tap Save.

**User Login.** When user accounts are enabled, the device starts on the login screen; incorrect credentials show "LDAP: invalid credentials". After successful LDAP authentication, the user name is shown in the top-left corner with a "(LDAP)" note indicating LDAP-based authentication, and a role icon (Admin/User/Guest) beside it.

**Users Management.** Guest users have limited access; regular Users have no access to Advanced settings. Log in as Admin to manage users under "User accounts". LDAP-authenticated users are cached locally for offline authentication and auto-deleted once the last login exceeds the Caching time; any user can also be deleted manually (tap the entry > Delete > confirm). Enabling/using LDAP does not affect existing local accounts — one local Admin account should always exist to recover from LDAP misconfiguration. Local user accounts are capped at 20; the number of temporarily cached LDAP users is not limited.

**FAQs**

* **Can local and LDAP users log in simultaneously? What if a user exists both locally and in LDAP?** Credentials are checked against the local database first, then against the LDAP server if not found locally.
* **If the LDAP server is unreachable and a cached user's timeout hasn't expired, can they still access the device?** Yes.
* **How does the device handle revoked permissions during offline mode?** There is no way to check for revoked permissions while offline. Once online again, if the revoked user attempts to log in, the LDAP server's rejection immediately removes them from the local user list.
* **If a user's group membership changes on the LDAP server, is manual intervention required?** No — the user is authenticated to the new role per current group membership automatically. If the group *name* itself changed, the group name must be edited manually on the LDAP server setup screen.
* **Can custom roles be created beyond Admin/User/Guest, or can LDAP groups be mapped to custom permissions?** No new roles or custom permissions are available, but an existing LDAP group (e.g. "ou=surgeons") can be mapped to the standard User role.
* **How do I regain access if LDAP is misconfigured and the local Admin account is lost?** Re-create the admin account via Remote Configuration using the remote-access password. If remote access isn't configured or its password is lost, the device must be reset to factory defaults, wiping all settings.
* **Can LDAP configurations be backed up or transferred to another MVR device?** Yes — back up all device settings to a USB drive, or use the Remote Configuration feature over the local network.

**Glossary**

* **LDAPS:** Lightweight Directory Access Protocol Secure — an encrypted version of LDAP using SSL/TLS.
* **Bind:** the LDAP operation to authenticate a client to the directory server.
* **SSL:** Secure Sockets Layer.
* **DN (Distinguished Name):** a unique, hierarchical identifier for an LDAP entry, e.g. `cn=John Doe,ou=Users,dc=example,dc=com`.
* **Base DN:** the root entry from which an LDAP search begins, e.g. `dc=example,dc=com`.
* **DC (Domain Component):** a DN segment representing part of a domain name, e.g. `dc=example,dc=com` = `example.com`.
* **CN (Common Name):** an attribute naming an object in a DN, e.g. `cn=Alice Smith`.
* **OU (Organizational Unit):** a DN container grouping entries by function/department/role, e.g. `ou=Engineering,dc=company,dc=org`.
* **UID:** User Identifier, e.g. `uid=jdoe`.
* **ObjectClass:** defines the type of object an entry represents (person, organizationalUnit, etc.).
* **Attribute:** a property of an LDAP entry, e.g. `mail`, `telephoneNumber`.

## Shortcut Keys

**Applicable models:** MVR435, MVR436, MVR450, MVR460, MTR133, MTR156. Shortcut Keys let System Integrators remotely control MVR and MTR series devices from the Network, RS232, and a USB keyboard.

### Start Screen Shortcut Keys (added 250527)

* `0`: set screen rotation to 0 degrees (landscape).
* `9`: set screen rotation to 90 degrees (portrait).
* `3`: set screen rotation to 270 degrees (portrait).
* `6`: set screen rotation to 180 degrees (landscape).
* `F3`, `n`: Start Study.
* `i`: Information screen.
* `s`: Settings.

### Live Mode Shortcut Keys (reviewed 251118)

* `F1`/`F4`: capture still.
* `F2`/`F5`: start/stop recording.
* `Enter`: Pause on/off.
* Long `F2`: Pause on/off.
* `PageUp`/`PageDn`: information screen.
* `Esc`: End of Study confirmation.
* `e`: Stop recording and End of Study without confirmation.
* `F3`: End of Study.
* Left/Right arrows: UI buttons position change/hide.
* `Home`: Video input change.
* `F6`: stop recording or no action.
* `F7`: start recording or no action.
* `F9`: capture an image from the secondary video input.
* `F10`: record start/stop of the secondary video input.
* `1`: change input to HDMI 1 or no action.
* `2`: change input to HDMI 2 or no action.
* `c`, `F12`: switch camera input from 1→2 or 2→1.
* `r`: review the last captured image, or play the last captured video directly, without the Review screen thumbnails.
* `Ctrl+H`: change color range for the current input (full/limited).
* `s`: Split view.
* `p`: PIP (Picture In Picture) enable — default top-left or previously selected.
* `=`: enable/disable parallel recording.
* `t`: show other camera (valid only for portrait layouts).

### Video Review, Image Editor, Report Preview Modes

* `PageUp`/`PageDn`: zoom in/out.
* `A`/`S`/`D`/`W`: pan.

### Video Playback Shortcut Keys

* `Space`: Pause/Play.
* `<`: move to the previous video tag.
* `>`: move to the next video tag.
* `-`, `_`: Play mode — decrease playback speed; Pause mode — previous frame.
* `+`, `=`: Play mode — increase playback speed; Pause mode — next frame.
* Press and hold `1` for slow play 0.1x; press and hold `2` for fast play 5x (applies only while the key is held).

### Universal Keys (added 250603)

Universal keys work system-wide and are particularly useful for external apps.

* Volume control: `Ctrl+>`, `Ctrl+<`; `Ctrl+PgUp`, `Ctrl+PgDn`; `Alt+'+'`, `Alt+'-'`.
* Back: `Ctrl+ESC`, `Ctrl+b`, `Ctrl+NUMPAD_1`. Also a gesture: quick swipe from the left or right edge of the screen (added 250903).
* Home (back to the MVR app, the HOME app): `Ctrl+h`, `Ctrl+~`, `Ctrl+NUMPAD_7`.

## System and Security

### Role-Based Access Control (RBAC) and User Accounts

MVR implements Role-Based Access Control to protect access to data over hospital networks and to local recordings. Roles: **Admin** (full access to all device features, including Advanced Settings — Network, Storage Rules, User Accounts, Audit Trail; no access to the underlying OS), **User** (standard access to record, review, and document; Advanced Settings blocked), **Guest** (limited to reviewing the Archive and viewing live streams — no recording or system-modification rights).

Once User Accounts are enabled, correct User Names/passwords are required to operate the device. MediCapture has no access to user account information and there is no "master password" — losing all account information requires a full factory-default reset. As of firmware **FW220602**, User Roles can be assigned; at least one user must have the ADMIN role (the MVR enforces this). When upgrading from previous software, all existing users are migrated to the USER role. All user roles can connect to the device stream via a web browser.

**Setup:** Settings > Advanced > User Accounts > enable User accounts > enter User Name and password. An Administrator manages users (add, delete, rename, change roles) in Advanced Settings.

**Break the Glass** (from FW 210126): when User Accounts are enabled, this emergency feature allows a Study to be started without login, in case a password is lost or unavailable. Tap the icon with a cross at the top-right of the login screen. The Remote App's Emergency button is available ONLY during direct USB tethering. This function is limited strictly to running a Study — archive information and settings cannot be viewed; patient information can be edited afterward via a proper login. This Emergency role is not configurable.

### Password and Session Management

From firmware 210126, a "Security" section in Advanced Settings lets Administrators configure:

* **Renew password:** an optional reminder period after which the user is prompted to change their password (does not force a lockout). Range: 1 week to 6 months. Default: Never.
* **Strength of password:** the UI informs about password strength when entering a new password but does not block a weak password — enforcement is the administrator's responsibility. MediCapture, Inc. is not liable for password misuse by unauthorized parties on the hospital's LAN/Wi-Fi.
* **Inactivity Timeout:** period after which the device enters screen-saver mode (a black screen with a digital clock at a randomly-changing position to prevent burn-in); tap the screen or press any key to wake it, requiring the logged-in user to re-enter their password. Disabled during an active Study. Range: 1–60 minutes. Default: 10 minutes.

### Audit Trail

Serves two purposes: compliance with security regulations, and better diagnostic data for support requests.

* Logs all critical device events and necessary user actions.
* The database keeps the last 5,000 events; older events are deleted automatically.
* Accessed from Advanced Settings, Audit Trail box — to comply with common security regulations, Advanced Settings should be locked under the admin password and access limited to a single admin user.
* Access is limited to the local user (device UI) and a remote admin (web configuration interface); the Remote App does not expose the Audit Trail, though actions performed via the Remote App are still logged.
* Locally, the log can be filtered, viewed, exported to USB, and erased; remotely, it can be exported and erased.
* No patient information is saved in the log.

### OS Protection and Malware Prevention

MVR/MTR devices run a **proprietary iMave operating system**, based on Android with all unnecessary components removed, on **ARM64** CPU architecture (not compatible with x86 PC architecture). The system is closed:

* No possibility for users or IT administrators to gain access to the operating system; there is no "IT administrator" login or system privilege.
* No possibility to install additional software or modify existing software modules that could introduce malware or damage the system.
* No files can be executed on the device by a user or IT administrator (no OS or file-manager access), and the application itself does not execute or allow execution of any file.
* External storage (including USB) is mounted with a **no-execute (noexec)** attribute, preventing execution of any file from removable media — a distinctive Linux OS feature not available on Windows.
* The application runs full-screen with no access to a generic OS desktop; no system hotkeys are accepted (the application processes all key events); no Task-Manager-like system tools exist.
* The application only allows file manipulation within the intended use — no generic file manipulation is available.
* OS and application files live on internal, non-removable eMMC flash storage with proprietary partitioning; system partitions are read-only and cannot have their permissions altered under any privilege. OS and application always boot fresh in "factory mode," retaining only the application's user settings.
* User files (images/videos only) are always kept on a separate storage device from OS/application files — no mixing of system and user files on the same storage.
* There is no BIOS; the OS bootloader is encrypted and signed with a proprietary key. Booting from an external device is impossible, and unauthorized/unsigned firmware is rejected at boot.
* Firmware is a single proprietary-format file, signed with a security key; unauthorized/unsigned firmware is rejected during update. Firmware updates the OS and application together — no separate software-component updates are possible.
* Remote access is disabled by default. Devices have no default user, administrator, or factory passwords; once remote access is enabled, a new password must be assigned, and there is no lost-password recovery procedure.
* Administrator privileges (once User Accounts are enabled) allow operation of Advanced Settings within the application only — no OS-partition/file access, no file-permission changes, and no OS administration rights. From the OS's point of view, the Administrator has only regular "user" rights.

### Network Security

Network services are **off by default** to minimize the attack surface and provide a secure out-of-the-box experience — Remote Access requires a unique password to be assigned when first enabled. NTP synchronizes automatically with hospital time servers for accurate recording timestamps (see Networking below).

### Automatic Video Repair (AVR)

An Automatic Video Repair Function, **patented by MediCapture® (US patent 11,750,784 B2)**, automatically detects and repairs corrupted MP4 files at power-on and when a damaged USB drive is inserted — addressing corruption caused by accidental USB removal, power loss, or unexpected shutdown during recording, so videos are not lost.

## Storage and Archiving

### General Storage Rules and Advice

* **Internal Storage** is the fastest and most reliable destination for recordings, but it is a buffer/temporary Storage only. It must be activated for DICOM export and for sending studies to PACS. Data should be copied from Internal Storage to USB, or Sent to PACS/NAS; an Internal Storage Backup feature can copy the entire Internal Storage to an external USB drive. Internal Storage has auto-cleaning rules — the user must configure rules and manage data and is solely responsible for any data loss or leak. Size: MVR Pro (MVR409) and MVR (MVR420): 128 GB, upgradable up to 512 GB or 1 TB; 1 TB for MVR435, upgradable to 2 TB; none for MVR Lite (MVR400).
* **USB Storage** is portable — good for presentations, handing data to a patient, or copying/backing up Internal Storage. USB flash sticks, SSDs, HDDs, or card readers can all be used. Supported file systems: exFAT, FAT32, NTFS. External USB HDDs may take ~20–60 seconds to be recognized (wait until the USB icon appears).

### Archive Selection

Storage locations selectable for direct (real-time) recording: **Internal Storage, USB Storage, Network Storage (NAS)**. Maximum video recording resolution can be set separately per Storage device: **2160p, 1080p, 720p**, or "Only images" (turns off video recording for that Storage). Selecting 720p also reduces recording framerate to 30 or 25 fps and is recommended for archiving purposes. One or two Storages can be selected simultaneously — e.g. "Only images" for Internal Storage plus 720p for Network Storage stores images at both locations while recording video only to the network archive, useful for keeping images for reporting/PACS while archiving video for insurance purposes elsewhere.

The maximum-resolution limit only reduces input video resolution — it never increases it (e.g. selecting 2160p with a 1080p input records at the original 1080p). **Note:** Internal storage is unavailable for MVR400 (MVR Lite).

### Video Recording Reliability

Recording stability depends on the storage media's writing speed, which must exceed the current recording bitrate — otherwise recording stops abruptly. Test the writing speed of unfamiliar Storage before relying on it. External USB Storage quality varies by brand, size, technology, format, existing file-system errors, and cabling; the most reliable method is recording to **Internal Storage**. Recording directly to Network Storage may be affected by network/server load — recording over a small local departmental NAS is generally acceptable, while recording over large hospital networks to distant servers without visibility into bandwidth/load may not be reliable. Avoid parallel recording to different storage media for best reliability.

**Recommended reliable-recording workflow:**

1. Set recording to a single storage, preferably Internal Storage.
2. After some experimentation, choose the lowest acceptable video resolution/quality (maximum settings tend to produce unmanageable data volumes, fragmentation, and bandwidth/capacity issues).
3. Perform Copy to USB, Send to NAS, or Send to PACS after finishing the Study.
4. Keep external USB Storage plugged in only when recording directly to it, or when performing a Copy/Backup — unplug it otherwise, since leaving it connected without reason can create confusion and increase device heat from extra power draw.

### Storage Speed Testing

The Writing Speed Test (on the Information screen, tap the relevant storage icon) tests USB sticks/SSDs and network storage using realistic video-recording benchmarks (unavailable when the MVR is under tablet Remote control). Results in **green** indicate speed suitable for 4K video recording; the typical requirement is under 4 MB/s (at 32 Mbps quality) with a maximum of 8 MB/s (Super, 64 Mbps, H.264, 4K30) — lower resolutions and HEVC require less. Results appear green (good) or orange (too low); avoid Storage that benchmarks non-green. Reading speed is not tested (it is typically faster than writing, especially for USB flash). The included SanDisk 64GB flash stick tests at 18–30 MB/s for FAT32/NTFS/ExFAT — sufficient for video recording. If a USB drive or Network Storage tests too slow, record to Internal Storage first and copy/send afterward — Internal Storage is designed to provide sufficient speed in any scenario.

### Selecting External USB Storage

A USB flash stick is included with every device and provides sufficient write speed. Other options: USB flash drive sticks, USB HDDs, USB SSDs, and USB card readers. Typical USB flash writing speed is ~13 MB/s (range 8–20 MB/s); larger-capacity flash may write faster. USB 2.0 is generally slower, though modern USB 2.0 sticks can reach 10 MB/s and may still suffice. USB 3.0/3.1/3.2 (Type-A/Type-C) may offer higher read speeds, but write speed depends heavily on the underlying flash technology — different USB 3.x versions tend to write at similar speeds. USB HDDs need up to ~1 minute to spin up before being detected.

Supported external USB file systems: **FAT32, NTFS, ExFAT**. FAT32 is most compatible and fastest in MVR's implementation, followed by ExFAT then NTFS (slowest); flash technology itself limits performance identically across all three below ~70 MB/s. Test results for an MVR Pro writing to a 1TB SSD: **159 MB/s FAT32, 70 MB/s NTFS, 80–100 MB/s ExFAT**.

USB Storage can be used for direct recording, copying, and backing up Internal Storage — but while flash write speed may suffice for recording, it can be slow for large Copy/Backup jobs. An external **USB SSD is recommended for Backup**; USB HDD also works but is slower than SSD. USB flash cannot sustain higher write speeds due to block erase-time limits and sequential-only operation; modern SSDs parallelize operations to overcome this. Backup may involve transferring up to 1 TB, requiring sustained maximum-performance writing — which causes maximum heating. Small USB flash sticks dissipate heat poorly, so internal temperature rises and slows writing further (the longer it takes, the slower it runs); larger SSDs, often with heat sinks, transfer heat to their aluminum enclosure more effectively. **Summary:** USB HDD/SSD perform Backup 10–15x faster than USB flash. For fastest Backup, use a USB SSD formatted ExFAT.

"Good quality" USB flash drives are defined by speed, lifetime/data reliability, and physical size:

* **Speed:** typical USB flash sticks deliver 10–30 MB/s write / 40–130 MB/s read; USB SSDs deliver 200–500 MB/s write and read — 10–20x faster than flash.
* **Lifetime/reliability:** flash memory has limited write cycles (endurance) depending on NAND cell type — SLC up to 100,000 cycles, MLC up to 10,000 cycles, TLC as low as 300 cycles, QLC up to ~1,000 cycles. Low-cost drives typically use TLC. Traditional flash drives do not manage write frequency per cell (so the start of the drive wears faster); SSDs use wear leveling to spread rewrites evenly and extend lifespan.
* **Physical size:** USB thumb drives are significantly smaller than typical USB SSD drives.

"Good quality" modern USB drives may contain SSD technology in a small form factor using MLC flash.

### Folder Naming Rules

**Current rule (Stamp Folder Names: ON):** folders are named using timestamps and device/patient information for proper sorting/identification.

```
Without Patient ID:  YYYYMMDD_HHMMSS_DeviceID
  Example: 20240521_161633_20bd4b50

With Patient ID:     YYYYMMDD_HHMMSS_PatientID_DeviceID
  Example: 20240521_162707_AV35674_20bd4b50
```

`YYYYMMDD_HHMMSS` sorts folders chronologically; the 8-hex-digit DeviceID distinguishes recordings from different devices sharing the same storage location. Always verify the device's date/time before starting a Study. Since the MVR435 model, the folder name is always time-stamped and contains the DeviceID; including personal patient data in the folder name is optional (Settings menu) and is recommended to be avoided to reduce the risk of personal-data leakage.

**Legacy rule (Stamp Folder Names: OFF):** folders are named sequentially `CASE0001, CASE0002, ..., CASE9999`. After CASE9999, naming resets to CASE10000, and although images/videos can still be captured, they cannot be reviewed from the Archive — subsequent studies after CASE9999 overwrite the previous CASE10000 contents. **Recommendation:** use the current (timestamped) naming rule to avoid overwriting and ensure archive functionality.

### File Naming Rules

File name structure: `PSSSS[-FFF].EXT`

* `P` — one-letter prefix for recording type/source: `I` = image, primary channel; `J` = image, secondary channel; `V` = video, primary channel; `W` = video, secondary channel; `R` = imaging report.
* `SSSS` — sequential capture number (0001–9999), reflecting chronological order of all captures/recordings regardless of type.
* `-FFF` — optional fragment number (001–999), used for long recordings split at the 4GB limit, saved edits, or images captured from video during playback.
* `.EXT` — file extension: images `jpg`, `png`, `dcm`; videos `mp4`, `dcm`; reports `pdf`, `dcm`.

The primary and secondary channels can be swapped during recording; recordings are made from the primary channel unless parallel recording is enabled.

**Examples:**

```
Capturing images and video (sequential):
  Capture image             → I0001.jpg
  Start video recording     → V0002.mp4
  Capture image (during rec)→ I0003.jpg
  Capture image (during rec)→ I0004.jpg
  Stop video recording
  Capture another image     → I0005.jpg

Long recording exceeding 4GB — fragments:
  Original: V0001.mp4
  Fragments: V0001-001.mp4, V0001-002.mp4, ...

Parallel recording (primary + secondary channel):
  Start parallel recording
    Primary   → V0001.mp4
    Secondary → W0001.mp4
  Capture images during recording
    Primary image   → I0002.jpg
    Secondary image → J0002.jpg
  Stop recording, switch channels (secondary becomes primary)
  Start new recording
    New primary   → V0003.mp4
    New secondary → W0003.mp4

Appending to a closed Study:
  Existing: I0001.jpg, V0002.mp4, I0003.jpg
  Capture image  → I0004.jpg
  Start recording→ V0005.mp4, then stop

Editing images/videos (fragment numbers preserve originals):
  Edit I0001.jpg           → save as I0001-001.jpg
  Edit that edited image   → save as I0001-002.jpg
  Capture image from V0002.mp4 → saved as I0002-001.jpg
  Save a video clip from original video → V0002-002.mp4

Generating PDF reports (prefix R):
  Generate report → R0004.pdf
  Append + capture image → I0005.jpg
  Generate another report → R0006.pdf
```

**Recording formats:** images JPEG (default)/PNG/DICOM; videos MP4/DICOM; reports PDF/DICOM.

**Archiving and copying.** Copying options: "As PNG/MP4/JPG" (original formats) or "As DICOM (.dcm)" (converts on copy). When copying to USB/NAS multiple times, a timestamp is appended to the folder name to avoid overwriting, e.g. `CASE0001-202405221435`. For USB drives, use NTFS to support long folder names and files >4GB (FAT32 may not). Example — copying as DICOM to USB: folder `CASE0001` with `I0001.jpg, V0002.mp4` becomes `CASE0001/I0001.dcm, V0002.dcm`. Example — copying as PNG/MP4/JPG to NAS with Stamp Folder Names ON: folder `20240522_152927_20bd4b50` with `I0001.png, V0002.mp4` is copied unchanged. **Sending to NAS** transfers the study folder directly without changing file formats — e.g. `CASE0001/I0001.png, V0002.mp4, patient_info.json` (the `patient_info.json` file may not appear in all cases, depending on system settings).

**Important notes:** verify device date/time before starting a Study for correct chronological sorting; use appropriate file systems (e.g. NTFS) on external storage for long names/large files; the Sequential Capture Number range is 0001–9999 (exceeding it may prevent further captures); certain folder-naming or copying methods may affect the ability to review studies on the device.

### Internal Storage Auto-Cleaning

One of two automatic-cleaning rules for Internal Storage can be selected:

* Keep around 20% free space, but not more than 50 GB, to guarantee minimum space for the next Study.
* Keep the last 7 days (MVR435 offers 28 days instead) — appropriate when Internal Storage is only a safety backup.

Cleaning rules are checked at Study Start (to ensure enough space for the new Study) and are not checked during an active Study. Leave both options unchecked to keep all recordings and delete them manually.

### Disabling (Locking) USB Storage

USB storage can be completely disabled/locked where portable/removable media is prohibited. Once deactivated, it no longer appears in the archive storage-selection settings.

### Internal Storage Backup

Available on the Archive screen; copies all Studies from Internal Storage to an external USB flash stick, hard disk, or SSD.

* Does **not** back up device settings or Activation Keys — use the "UPDATE / DEFAULT" screen's settings backup for that.
* The backup button appears at the bottom-left of the screen only when external USB Storage is present.
* Checks available USB space before starting.
* Incremental — copies only new/changed files, skipping previously-copied files; does not delete other files on the USB drive (only creates/updates `CASExxxx` Study folders).
* Repeatable — can be run again on the same USB storage.
* Does not delete anything from Internal Storage — delete manually or format Internal Storage once backup is complete.
* On a file error, a pop-up shows the error description; tap "Skip" to continue — only the corrupted file is skipped, all good files are still copied.

### Network Storage (NAS) Setup

**Creating a shared folder on the NAS:** create the shared folder per your NAS instructions, ensure the MVR user has sufficient read/write privileges, and take extra care for Wi-Fi users on WPA2-Enterprise (may need additional setup). Note the User Name, Password, and Shared Folder name (example: user `mm`, password `123412341234`, shared folder `Shared`).

**Settings for Network Storage:** ensure Network Storage is enabled in Archive Settings. Tap "Find Server" to list available servers with shared folders on the local network, then tap the desired server (its IP address is inserted automatically) — if the expected server isn't listed, verify the shared folder's subnet is accessible from the MVR's subnet. Enter: User Name (login user on the server), Password, Folder Name (shared folder name), Label (optional server name), Domain (optional). A video-resolution limit or "Only images" can be set for network storage, which combines with the general Archive Storage Settings. Tap Test to check settings (should show "OK"), then Save.

### Send to NAS

Background: hospital networks may limit per-device bandwidth, or the network may be unavailable at the time of surgery — the "Send to NAS" feature addresses this.

**Setup (Archive Settings / Export screen):**

* **Enable Export to NAS:** set 'Export to PACS/NAS' to 'NAS'. Files saved to Internal Storage can then be Sent to NAS. Note: this disables the "Send to PACS" feature — a Study cannot be exported to both a NAS shared folder and PACS simultaneously.
* **Auto Send** (optional): automatically sends all Study files to NAS when a Study finishes.
* **Auto Delete** (optional): automatically removes files from Internal Storage once successfully sent to NAS.
* An orange error message appears at the top of the screen for incorrect settings.

**Details:** Network Storage must be configured but turned OFF for recording to enable Send to NAS. The copy runs in the background from Internal Storage to Network Storage at lower priority, can be interrupted by a New Study or power-off, and resumes automatically. Auto Send fires as soon as a Study ends; with Auto Delete enabled, the Study folder is deleted once fully sent. Sending the same CASE folder again merges files into the existing folder; sending the same files overwrites them; sending a subset of files creates a new folder with the same CASE folder name.

### Sharing the Internal Storage over the Network (SMB)

Enables a SAMBA server on the MVR device for remote-PC access to Internal Storage. **Not available for MVR400 (MVR Lite) or MVR435.** From **Settings > Advanced > Storage Rules**: tap "Share Internal Storage" to enable, and set a password — the connection address is then displayed. Restart the device (power off/on) after making changes. From a remote PC, point the file explorer at the MVR access point, e.g. `\\192.168.2.125\storage`, and enter credentials: user name `root`, password as set for Sharing Internal Storage. Internal Storage then appears as a folder in the PC's file explorer.

### Deleting Recordings

In the Review screen, select one or several recordings (tap the top-right corner of the thumbnail) and use the Delete button; a Select/Unselect ALL button is also available. In the Archive screen, a Study folder can be deleted only when it is empty — this prevents accidental bulk deletion; delete all recordings inside the folder first, then the folder's Delete button appears. There is no "delete all recordings" feature; however, Administrator-only Advanced Settings offer Format Internal Storage / Format USB Storage, which deletes all recordings on the selected storage — ensure everything important is archived (copied, backed up, sent to NAS/PACS, or printed) first.

## Networking

### Wired LAN Settings

Connect the network cable (RJ45) to the LAN connector on the back (MVR Lite requires a USB-LAN adapter). On the Network Settings page, network settings are auto-assigned when the device is set to Auto IP (recommended to keep permanent). Switch to Manual IP and tap Set to enter settings manually; confirm on the Information screen.

### Wi-Fi

Connect the supplied Wi-Fi antennas to the rear "WIFI" and "WiFi/BT" connectors, and turn on the Wi-Fi access point. On the Wi-Fi Settings page, enable Wi-Fi and wait for the access-point list to populate (tap the search icon if not listed); tap the desired network and enter the password carefully (case-sensitive). After connecting, the Wi-Fi IP address is displayed; the password is saved and Wi-Fi reconnects automatically at next power-on.

**WPA2-Enterprise / Certificates.** WPA2-Enterprise is more secure than WPA2-Personal, providing personalized login and encryption via user identity/password; the IT administrator may also create optional security certificates to install on the device. Equipment needed: external USB keyboard, empty USB stick; upgrade to the latest firmware first. Obtain the Wi-Fi MAC address from the Information page (tap the device icon). MVR supports WPA2 (IEEE802.11i, CCMP/AES encryption); certificates are created by the IT administrator per the on-site RADIUS authentication server's requirements. Accepted formats: `.pem` for the CA certificate, `.p12` for the User certificate.

**Installing certificates:** copy certificates to an empty USB stick and connect to the front USB port. Go to **Settings > Connections > WiFi**, confirm Wi-Fi is connected, and press `Ctrl+W` on an external USB keyboard to enter Test mode. Tap "ADVANCED" (top-right) then "Install certificates" to open the file browser, select the USB stick, and locate the certificate folder. Select and name the CA certificate first, then select/install the User certificate with its password. After installation, tap `ESC` to return to the WLAN screen and select the Enterprise network. Follow the IT administrator's procedure — e.g. choose the EAP method (e.g. "TLS"), scroll to Phase 2 authentication, select an installed certificate if required, type the identity (the user name created on the local authentication server), and tap CONNECT.

**Hidden SSID.** Connect a USB keyboard, go to the WIFI SETTINGS screen, and press `Ctrl+W` to reach the Android WLAN screen. Tap "Add Network" and enter the SSID details, then press Escape repeatedly to return to the MVR screens. The new SSID settings persist across power cycles.

### Remote Access and Remote Configuration

The device can be controlled remotely from a PC browser ("MVR Remote Configuration") by IT administrators, from a tablet/smartphone via the MVR Remote App, or from remote IT systems via the API. Remote Access is **disabled by default** — enable it at **Settings > Connections > Remote Access**, toggle the slider, and set a password. Once enabled, the device is reachable at its IP address on port **3333** (full URL shown on screen). For MVR Lite (MVR400), remote access requires the Connect Package (USB-LAN adapter + Network activation key).

**MVR Remote Configuration** lets IT administrators browse all settings and manage files on all storages (watch, delete, download) via a web browser, and update firmware remotely. Activate at **Settings > Advanced > Connections > Remote Access**, enable, set a password, note the IP address, then return to the Home screen (the device must be idle/at the Home screen for remote access — not during an open Study or Archive browsing). Connect a PC/portable device to the same LAN/Wi-Fi and open a browser to e.g. `http://192.168.1.233:3333/config`, entering the password. While under Remote Configuration, the device cannot be operated locally and shows a corresponding message; log out of Remote Configuration to resume normal local operation.

**Troubleshooting — login stops working after a firmware upgrade:** likely cause is the device set to Auto-IP, so its address changed after the upgrade. Check the new address at **Settings > Advanced > Remote Access**, or switch to Manual IP at **Settings > Advanced > Connections > Network** by entering the fixed IP address from your IT administrator and tapping Set.

### Video Streaming

Video streaming enables external viewers to watch live studies with low latency, using **FMP4 (Fragmented MP4) over TCP/IP** — accessible on most JavaScript-enabled browsers with no extra infrastructure. Advantages of FMP4/TCP over typical UDP streaming: no special network equipment needed; enhanced reliability via TCP's connection-oriented error correction/retransmission (vs. UDP's packet loss/artifacts); better firewall/NAT compatibility for clients behind firewalls; better scalability through CDNs/cloud services. If audio is enabled with a connected microphone, audio playback is also available. Streaming is intended for education, training, and consultation — **not for diagnostic use**. Activation requires a password-protected user account and active confirmation from the MVR operator, who can terminate the stream at any time.

**Streaming features:** resolution **1280x720p30**; browser viewing options include full-screen, picture-in-picture overlay, and snapshot (browser-dependent, via right-click); maximum **8 simultaneous stream clients**; lower task priority than other MVR functions, with automatic quality reduction if needed.

**Requirements:** MVR firmware **220116** or later; streaming activation via PC/laptop over the network, or Android mobile devices via Wi-Fi; recommended browsers Chrome, Edge, Firefox (potential compatibility issues on Apple iPhone/MacBook).

**Administrator setup:** connect the MVR and streaming device to the same network; check Network settings (Settings > Advanced > Connections > Network) or Wi-Fi settings; enable User Accounts, create user accounts, and remember the credentials (no master password exists); optionally protect Advanced Settings with an admin password; assign user roles (GUEST recommended for stream viewers); activate Streaming at Settings > Advanced > Connections > Remote Access (enable Remote access and Streaming); note the displayed address (e.g. `http://192.168.2.108:3333`) and share it with clients; optionally enable "Always allow" for trusted environments and enable audio if a microphone is connected; optionally disable "Stamp function in pictures and videos" to protect patient anonymity (Settings > Video/Audio > Video Input).

**User instructions:** start a Study with live camera video on the recorder; open a browser on the remote device to the IP address with a `/stream` suffix (e.g. `http://192.168.2.108:3333/stream`); request to join by entering User Account credentials; wait for the operator's acceptance; adjust settings (full-screen, audio) and terminate when finished (a new stream requires a new login). MVR operators can view the list of connected viewers and selectively disconnect any of them during the live stream.

## Reporting

### Automation Reporting Feature

Available on all MediCapture MVR and MTR device models; recommended firmware **FW 250924** or newer.

**Report structure** (header table items 2–12 repeat on every page to prevent pages being mixed up):

1. Report Header Image (first page only).
2. Institution Name and Location.
3. Device Name, Model, Device ID, and Firmware Version of the device used to create the report.
4. Patient Last and First name.
5. Patient ID Number.
6. Patient Gender.
7. Patient Birth Date.
8. Performing Physician.
9. Study/Series Description.
10. Case Folder Name (unique name from time stamp + Device ID).
11. Report Creation Date.
12. Current/Total Number of Report Pages.
13. Image File Name.
14. Image Captured Date.
15. Image Notes (created in Image Review).
16. Image to Report annotation (done in Image Review).
17. Report Notes — ending notes, written in Markdown.
18. Institution Stamp or Physician Signature.
19. Footer Text (present on every page).

**Creating a report:** open the Archive and the desired case folder; select the images to include (any number, before or after entering the Report screen — at least one image is required); tap "Report"; adjust general settings; tap "Save" to save as PDF in the same folder, or "Print" to send directly to a connected printer (to exit the print menu, swipe left or choose "Cancel Print" then the "<" button). Alternatively, in Archive mode, tap Report to create a report including all images in the selected study folder.

**General report settings** (applied to the report currently being created):

* **Page Layout:** Portrait — 1, 2, 3, 6 (2x3), or 8 (2x4) images per page; Landscape — 1, 4 (2x2), or 9 (3x3) images per page.
* **Page Size:** ISO A4, Letter, ISO A3, ISO A5, ISO A6, or 100x148mm (Hagaki).
* **Mode:** Default (standard, all information), Anonymize (excludes patient information), Only images (images only, no accompanying text).
* **Notes:** add/adjust notes in Markdown, appearing at the end of the report after images.

**Report settings and presets** (Settings > Archive > Report Settings, or the Report-settings button on the Report screen):

* **Report preview:** simulated report preview with patient info excluded.
* **Header image:** JPG/PNG from the USB root folder, used as the first-page header; recommended ~2048x256 (~8:1–10:1 aspect ratio), scaled to page width.
* **Image at end of report:** similarly-sized image (e.g. doctor's signature or hospital stamp) shown after the notes.
* **Footer text:** Markdown text placed at the bottom-left of every page.
* **Notes text:** default Markdown note automatically appended to every report, editable per-report via Notes.
* **Page Layout / Page Size:** same options as general settings, applied as future defaults.
* **Auto reporting:** when enabled, a report is generated automatically after each Study (saved as PDF in the case folder, or opened for printing); disabled by default.

To set the institution name, department name, location, and device title: **Settings > System > Patient info**.

### Accession Number Auto-Encoding

Specification for automatic encoding of a unique, time-sortable, 12-character alphanumeric code.

* **Output format:** 12-character string.
* **Character set:** A–Z, 0–9 (Base36).
* **Uniqueness source:** combination of a timestamp and a unique device identifier.

**Data structure** — derived from a 62-bit unsigned integer:

```
bit_fields:
  - bits: 61..32
    component: Timestamp
    description: Seconds elapsed since the custom epoch.
    bit_length: 30
  - bits: 31..0
    component: Device ID
    description: The full 8-character hexadecimal device ID.
    bit_length: 32

Visual layout:
[ t t t t t t t t t t t t t t t t t t t t t t t t t t t t t t | d d d d d d d d d d d d d d d d d d d d d d d d d d d d d d d d ]
(t = timestamp bit, d = device ID bit)
```

**Component definitions:**

* **Timestamp:** unit seconds; epoch start 2025-01-01 00:00:00 UTC (Unix timestamp 1735689600); calculation `floor(current_unix_timestamp_seconds) - 1735689600`; lifespan ~34 years from epoch start.
* **Device ID:** source is the unique 8-character hex string (e.g. `1A2B3C4D`); represented as its full 32-bit integer value.

**Encoding procedure:**

1. Calculate the 30-bit timestamp value (current UTC seconds minus 1735689600).
2. Convert the 8-character hex Device ID to its 32-bit integer equivalent.
3. Combine: `combined_value = (timestamp_value << 32) | device_id_value`.
4. Encode `combined_value` to Base36 (uppercase).
5. Pad with leading zeros to exactly 12 characters.

**Example:**

```
Time: 2025-06-25 02:27:00 UTC (Unix: 1750895220)
Device ID: AABBCCDD

Timestamp Value: 1750895220 - 1735689600 = 15205620
Device ID Value: 0xAABBCCDD = 2864434397
Combine: (15205620 << 32) | 2864434397 = 65301827059633373
Encode: (65301827059633373).toString(36).toUpperCase() = "1J3J4A25V5D"
Pad: "01J3J4A25V5D"

Final Code: 01J3J4A25V5D
```

## Firmware Update and Factory Reset

### UPDATE / DEFAULT Screen

**Location:** Settings > Advanced > Update & Default. Requires Administrator privileges. Offers: Update firmware; Backup settings; Restore settings; Format USB Storage; Format Internal Storage; Reset settings to default; Reset device to factory default.

### Getting and Checking Firmware

Get the latest firmware, with free improvements and new features, from your sales representative, directly from MediCapture, or at [https://medicapture.com/support/](https://medicapture.com/support/) / the [firmware portal](https://medicapture.com/portal/firmware/). Firmware is delivered as a single digital-download file of approximately 900MB.

**Check the current firmware version:** power on the device, wait for boot to complete, open the INFORMATION page, and tap the icon — the version is shown, e.g. `APP=230220`.

### Upgrade via USB Flash Drive

1. Prepare an "Upgrade Flash Drive" (recommended: an empty USB stick).
2. Download the update file from the MediCapture customer portal or the link from your sales representative, and copy it to the USB Flash Drive. File naming: MVR/MVR Pro use `MVR409-yymmdd.upd`; MVR Lite uses `MVR405-yymmdd.upd`; MVR435 uses `MVR435-yymmdd.upd` (files with an incorrect name/structure are rejected).
3. Insert the USB Flash Drive into the front panel.
4. Open the INFORMATION screen, tap the SETTINGS icon, then go to **Settings > Advanced > Update & Default**.
5. Tap "Update" in the Update firmware section and follow on-screen instructions, confirming the firmware version shown.
6. During the upgrade, the device requires USB removal per on-screen instructions; the upgrade takes 3–5 minutes and the device reboots automatically. Wait for the startup screen, then wait 2 more minutes, then power the recorder off and on using the rear-panel switch. Once in normal working mode, the new firmware is ready.
7. Re-check the INFORMATION screen for the new version; verify Time zone/Date/Time (Settings > System > Date and Time) and confirm optional activation keys remain unlocked (Settings > Advanced > Activation key).

If an error occurs during update: data is safe and the device remains on the current firmware. Ensure the update file copied to the USB stick without errors — re-download it, and format the USB drive or use another one to rule out a corrupted file.

### Upgrade via Remote Configuration

Open a browser to the device address shown on the MVR Remote Access Settings screen, e.g. `http://192.168.1.233:3333/config`, and enter the password. Check the currently installed firmware version under **Information > System Information**. Start the process from **System > Upgrade Firmware**, select the firmware file, and confirm. Sending the file may take a few minutes; once the upgrade screen reverts to the login screen, the remote update has started. Wait 5 minutes, then log in again to verify the new firmware version.

### Factory Reset

Performing a factory-default reset resets all user/system settings to default — useful for resolving system errors before upgrading from an old firmware version, or before transferring a device to another department/user. Recordings on Internal Storage are preserved during a Factory Reset; use "Format Internal Storage" separately to clear recordings.

**Lost passwords:** a deep factory reset is necessary only when the Administrator password itself is lost (locking Advanced Settings) — MediCapture has no access to user passwords and there is no default/master password, so password recovery is not possible. If only a single User Account password is lost (and the Administrator still has access), a full factory reset is not required — the Administrator can log in with their own password, then delete/create User Accounts or disable the User Account function.

**Reset device to factory default procedure:** from the "UPDATE / DEFAULT" screen, select "Reset device to factory default". A confirmation dialogue appears ("Are you sure? You may want to backup settings first") — optionally tap "Backup settings" to save settings (including Activation Keys) to USB first, since the reset erases all settings including Activation Keys. After confirming, the device restarts automatically (floating circles shown during reset) and restarts again into normal working mode — the process takes 3–5 minutes. Once back in working mode, saved settings can be restored from USB; a restart after restoring settings is recommended.

### Deep Factory Reset (MVR420, MVR409, MVR400)

Used when the Settings menu is unreachable due to lost passwords or another unexpected condition:

1. Turn the device off with the main switch on the back panel.
2. Press and hold the Video Recording button on the front (middle button).
3. While holding it, turn the device on with the main switch.
4. Continue holding until the front rings stop blinking (~15 seconds) — the MVR Maintenance screen appears.
5. Use the Video Recording button to navigate the cursor to "Reset to Factory Defaults", then press the Patient button to confirm.
6. Use the Video Recording button to navigate to "Yes", then press the Patient button to confirm and activate the reset.
7. The device reboots with factory default settings (~50 seconds).

## Activation Keys

### AK4K

**Product name:** AK4K. **Product type:** digital code for feature activation. **Description:** activation key for 4K video recording on MediCapture MVR-series and MTR-series recorders. **Grade / medical device classification:** none.

**Compatibility:** MVR Pro (MVR409), MVR (MVR420), MVR Lite (MVR400), MVR435, MVR436, MVR450, MVR460, MTR133, MTR156. The key is specific to the Device ID of a particular unit and will not work on other devices. To be compatible with MVR409/MVR420/MVR400, the camera must output HDMI 2160p30; other models accept 2160p60 over HDMI or DisplayPort. For 4x 3G-SDI Quad-Split (Square Division) or 2-Sample Interleave (2SI) camera output, MediCapture's **MVC Pro HDMI to SDI** converter converts to HDMI. For 12G-SDI camera output, MVR450/MVR460 accept it directly; other models need an SDI-to-HDMI converter — recommended: Blackmagic Design Teranex Mini SDI to HDMI 12G (for MVR409/MVR420/MVR400) or Micro Converter SDI to HDMI 12G (other models). Some MVR/MTR variants may ship with AK4K pre-activated (the code is found on device/IFU/box labels).

**Usage:** no installation required. Activate via **Advanced device settings > Activation Keys**, entering the digital code — "Unlocked" is displayed next to "4K recording" on success, and the feature works automatically thereafter. Available after activation: selecting 2160-line video recording resolution in Storage Settings.

**Video recording resolution:** without AK4K, limited to max 1920x1200; with AK4K, 4096x2160 and 3840x2160p. Captured-image resolution always matches the input resolution, with or without AK4K.

**Ordering:** ordering code `AK4K`; required info: device Serial Number and Device ID (Information screen); package content: 8-digit hex code; price: contact MediCapture.

**Troubleshooting:** procedures like Reset to Factory Defaults erase Activation Keys — keep a record of purchased keys (e.g. a sticker on the device). If a key is lost, contact a MediCapture representative for free recovery (Device ID and purchase information required).

### AKDICOM

**Product name:** AKDICOM. **Product type:** digital code for feature activation. **Description:** activation key for DICOM worklist import and PACS export. **Compatibility:** MVR-series and MTR-series devices; the key is specific to the Device ID and will not work on other devices. **Ordering code:** `AKDICOM`; required info: device Serial Number and Device ID; package content: 8-digit hex code; price: contact MediCapture.

**Functional description.** Once connected and configured to a worklist server, the MVR/MTR retrieves the worklist for every new patient Study; after selecting the correct worklist item and verifying its data, recording proceeds as usual, and all worklist data is embedded into captured images and recorded videos. Images, videos, and PDF reports can be sent to PACS manually or automatically (accepted formats depend on the PACS server, testable from the PACS server setup screen). DICOM setup/testing screens are available **without activation**, so PACS and Worklist can be configured and tested before purchasing AKDICOM; regular Send-to-PACS and Worklist Search require activation.

**Activation and settings.** Administrator privileges are required. Internal Storage must be enabled (set the desired resolution, or "Only images" if videos should not go to PACS). Confirm network connectivity on the Information screen. On the Patient Info Settings screen, set "Patient Info" from "Off" to "Human" and enter Hospital Name, Department Name, Location, and Device Title (consult hospital IT as needed). Enable Worklist Search if desired and complete Worklist server setup. Enable "Export to PACS" on the Archive Settings/Export screen, and perform PACS Server Setup and Test. Finally, enter the activation code in Advanced Device Settings > Activation Keys — "Unlocked" appears next to "DICOM software" on success.

**DICOM conformance:**

| Parameter                              | Value                          |
| -------------------------------------- | ------------------------------ |
| Implementation Class UID               | 1.2.826.0.1.3680043.9.7572.1.0 |
| Implementation Version Name            | MEDICAPDCM 1.1                 |
| Maximum PDU size                       | 65536 bytes                    |
| Storage SCP outgoing local port number | 3383                           |

**Supported Transfer Syntaxes:**

| Name                                             | UID                     |
| ------------------------------------------------ | ----------------------- |
| JPG — JPEG Baseline                              | 1.2.840.10008.1.2.4.50  |
| H264 — MPEG-4 AVC/H.264 High Profile / Level 4.1 | 1.2.840.10008.1.2.4.102 |
| HEVC — HEVC/H.265 Main Profile / Level 5.1       | 1.2.840.10008.1.2.4.107 |
| IVRLE — Implicit VR Little Endian                | 1.2.840.10008.1.2       |
| EVRLE — Explicit VR Little Endian                | 1.2.840.10008.1.2.1     |

**Supported SOP Classes:**

| SOP Class                                              | UID                              |
| ------------------------------------------------------ | -------------------------------- |
| Verification                                           | 1.2.840.10008.1.1                |
| Secondary Capture Image Storage                        | 1.2.840.10008.5.1.4.1.1.7        |
| Multi-frame True Color Secondary Capture Image Storage | 1.2.840.10008.5.1.4.1.1.7.4      |
| VL Endoscopic Image Storage                            | 1.2.840.10008.5.1.4.1.1.77.1.1   |
| Video Endoscopic Image Storage                         | 1.2.840.10008.5.1.4.1.1.77.1.1.1 |
| VL Photographic Image Storage                          | 1.2.840.10008.5.1.4.1.1.77.1.4   |
| Video Photographic Image Storage                       | 1.2.840.10008.5.1.4.1.1.77.1.4.1 |
| VL Microscopic Image Storage                           | 1.2.840.10008.5.1.4.1.1.77.1.2   |
| Video Microscopic Image Storage                        | 1.2.840.10008.5.1.4.1.1.77.1.2.1 |
| Encapsulated PDF Storage                               | 1.2.840.10008.5.1.4.1.1.104.1    |
| Modality Worklist Information Model - FIND             | 1.2.840.10008.5.1.4.31           |

Images captured in JPEG are sent using the JPG transfer syntax when the server supports it; otherwise they are converted to RGB and sent via EVRLE. Images captured in uncompressed PNG are sent uncompressed via EVRLE. If an image transfer fails, the Storage SCU AE does not auto-retry — the user is notified and can retry manually. Acquired images use the Study Instance UID of the Scheduled Procedure Step when available; if the WL item lacks Study Date/Time (unscheduled Study), these are generated locally along with the Study Instance UID.

Traceability: Device ID is stored in DICOM tag (0018,1003), firmware version in (0018,1020); EXIF metadata in images/videos also carries Device ID and firmware version. The Serial Number is label-only and not software-traceable — use Device ID instead.

**Worklist Server Setup.** Required fields: Server IP, Server Port, Server Title (Called AET), Device Title (Calling AET) — consult hospital IT. **Default Character Set** for incoming worklist results (when the server doesn't specify one): UTF-8 (ISO_IR 192, default), ISO-8859-1 (ISO_IR 100), EUC-KR (Korean), Big5 (Traditional Chinese), or "Do not use" for older servers. The right-side fields are matching keys for the Broad Worklist query (limit results to this device/modality/date): enabling "Match by: Scheduled Device Title" filters to this device only. Modality options: XC (External-camera Photography), ES (Endoscopy), GM (General Microscopy), SC (Secondary Capture) — recommended to match the Export-to-PACS modality; a Worklist search result's Modality overwrites the Study's Modality. Scheduled-date filters: "Today" (today + tomorrow), "Today and newer" (today + next 10 days), "Recent" (past 2 days + next 10 days), "Last week" (today + previous 6 days), "Last month" (today + previous 30 days). For testing, start with all matching keys disabled/"Any".

Tap "Test" to verify connectivity (shows "Success" plus server UID/version — useful for support); tap "Worklist search" to verify "Match by" filters (an "Empty list" means the server works but found no matches — try disabling filters temporarily). Results typically show the first few items plus a remaining count, e.g. "(23)". **Remember to tap Save.**

**Worklist User Guide.** At Study start, a "Worklist search" pop-up appears; tapping "Search" with empty fields searches the full worklist (subject to the AET/time-frame filters set above; results are capped at 200 entries). Results show Accession Number, Patient ID, Name, Scheduled Procedure Date, and Name in a table; typing filters the list live. Five search fields are available: Accession number, Patient name (last), Patient ID, Procedure ID, Scheduled physician — some fields require exact matches (Accession number, Patient ID, Procedure ID) while others support wildcards (Patient name, Scheduled physician, case-sensitive depending on the server, e.g. `Cl_` matches "Cleo", "Claudia", "Clark"). Narrowing the list to under 5 items is recommended to reduce operator mistakes.

Tapping a worklist item opens "Verify Data", showing the full patient information set; obtained fields cannot be edited, but missing essential fields (birth date, Patient ID, Gender, etc.) can be added. Editable exceptions: the scheduled Performing Physician (editable if changed), Referring Physician's name, Anatomic Region information, and the Scheduled procedure step description. **Verify** the Scheduled Procedure Step Status — SCHEDULED/ARRIVED/READY show in blue; STARTED/DEPARTED or any undefined code shows in orange as a warning. Note: the WL item's Modality overwrites the DICOM format settings' Modality — always set the correct Modality as a matching key in Worklist server setup (except for demo/testing); an unsupported Modality is replaced with SC (Secondary Capture) and highlighted in orange as a warning. Verify patient identity, then scroll down and tap Start.

Emergency/unscheduled patients not on the worklist can be entered manually via the "Unscheduled" button in the Worklist search window, using the on-screen keyboard, then tap Start.

**Anatomic Region.** Required for several Visual Light modalities including Endoscopy (ES); available both from Worklist selection and manual entry. Consists of three fields — the anatomic region plus two optional modifier fields — each drawn from fixed DICOM-specified lists (regions per DICOM CID 4040 for Endoscopy; modifiers per DICOM table CID 2). Typing filters the list live (e.g. "C" shows all regions containing "C"; a single match auto-selects). The examined body part is auto-generated from the Anatomic Region and embedded into image/video files; selecting a "Left" or "Right" modifier auto-generates the corresponding Laterality (L/R), also embedded into files.

**DICOM tags/fields in the MWL C-FIND request:** Accession Number (0008,0050); Modality (0008,0060); Referring Physician Name (0008,0090); Study Description (0008,1030); Physicians Of Record (0008,1048); Performing Physician Name (0008,1050); Referenced Study Sequence (0008,1110); Patient Name (0010,0010); Patient ID (0010,0020); Patient Birth Date (0010,0030); Patient Sex (0010,0040); Other Patient IDs (0010,1000); Patient Address (0010,1040); Military Rank (0010,1080); Medical Alerts (0010,2000); Allergies (0010,2110); Additional Patient History (0010,21B0); Pregnancy Status (0010,21C0); Last Menstrual Date (0010,21D0); Study ID (0020,0010); Requesting Physician (0032,1032); Admission ID (0038,0010); Special Needs (0038,0050); Performed Procedure Step ID (0040,0253); Performed Procedure Step Description (0040,0254); Scheduled Protocol Code Sequence (0040,0008); Scheduled Procedure Step Description (0040,0007); Scheduled Procedure Step ID (0040,0009); Requested Procedure ID (0040,1001); Requested Procedure Comments (0040,1400).

**Worklist retrieval from Patient Info Edit screen.** For emergency cases performed before a formal worklist is populated: tap the Worklist search button at the top of the Edit Patient Info screen, select from the list, populate the form, and continue manual editing as needed.

**PACS Server Setup.** On Archive Settings/Export: enable "Export to PACS" ('Export to PACS/NAS' = 'PACS' — this disables Send-to-NAS, since a Study cannot go to both a shared folder and PACS simultaneously); optional Auto Send (on Study finish) and Auto Delete (after successful send). Incorrect settings show an orange error, e.g. "PACS export cannot be enabled: Internal Storage is disabled" or "...Patient Info must be enabled".

On the PACS Server Setup screen: required fields Server IP, Server Port, Server Title (Called AET), Device Title (Calling AET) — consult hospital IT. Video upload can be disabled if the PACS server rejects video files or IT policy forbids it. Specific Character Set defaults to `ISO_IR 192` (covers all national/international characters, recommended default); use `ISO_IR 100` if the PACS only accepts Latin characters. Modality options match the Worklist settings (XC/ES/GM/SC) — recommended to keep consistent. Tap "Test" to confirm connectivity — success shows server UID/version info and a result like `OK (Modality ES formats: JPG, H.264, HEVC, PDF, PNG)`, confirming the connection, accepted modality, and supported DICOM encodings. A test-image upload button is available. **Remember to tap Save.** Once saved, server status appears on the Information screen as "Ready", "No connection", or "Sending".

**PACS setup troubleshooting:** "Error: connect timed out" — wrong IP/port. `OK (No formats supported)` — the specified port isn't designated for file storage; verify the correct port with IT. `Error: Associate rejected; Called AE-title not recognized` — wrong Server title (case-sensitive). `Error: Associate rejected; Calling AE-title not recognized` — wrong/restricted Device Title (case-sensitive).

**Send to PACS user guide.** Two export modes, set by the IT administrator: **Auto Send** — export happens automatically; images/videos can still be edited and reports generated in Review during the session as long as the Study isn't closed; tap "Finish your study" then confirm export by tapping Send — the whole Study is sent, or cancelled to send later manually; a new Study can be started while sending continues; do not power off during export; with Auto Delete, the Study is removed from Internal Storage after successful export. **Manual Export** — open Archive, select a non-exported study, and tap "Send to PACS". Export status icons: no cloud = not yet sent; grey cloud = sending in progress; blue cloud = sent successfully; orange cloud = an error occurred (some/all files not sent). Studies can still be edited after being sent (snapshot from video, magnify, annotate, etc.) — added files stay local until re-sent (page up to the overview and tap Send to PACS again).

**PACS upload error troubleshooting:** "PACS Error: connect timed out" — device was powered off or network was interrupted during send; export may resume automatically once reconnected, or may need to be restarted manually (tap the error message). "PACS upload errors" (network unreachable, broken pipe, socket closed) — tap the orange message for detail; retry once reconnected. "Server doesn't support transfer syntax for HEVC" — contact IT administrator (indicates a PACS setup/test issue). "Out of resources" — PACS server lacks storage/memory; contact IT. "Processing failure" — PACS server error; contact IT. In the error dialogue, "Retry" resends all failed files, "Ignore" clears the error status without resending (failed files can be sent again later manually). "No response" — file uploaded but the PACS server errored, possibly due to large file size; contact IT.

**Reset PACS database:** available in the PACS export screen; clears all cloud-status icons and resets the internal database — useful when switching PACS servers, cleaning/maintaining Internal Storage, or resolving erratic behavior/deadlocks in the PACS database.

**Compatible PACS servers:** in principle, any DICOM-standard-compliant PACS server. Known tested server: **AGFA Impax**.

**Offline DICOM Operation.** Feature: offline Worklist and offline Send to PACS. Background: surgical towers are often mobile across operating rooms, and network access may not be available during surgery. MVR supports full offline operation with WiFi flexibility, providing Worklist and DICOM functionality while disconnected — once reconnected (e.g. when the tower rests in a corridor with power/network cables attached), MVR automatically resumes sending files to PACS and updates the Worklist without operator interaction.

*Principles of operation:* after power-on, MVR attempts to obtain and retain the Worklist for possible offline use, using the default filter, refreshed every hour. If Worklist Search is used at Study Start, a fresh Worklist is fetched if online; otherwise search uses the offline copy. After Finish Study, if Send to PACS/NAS is used (auto or manual), the dialogue does not block on "waiting for network" — files are silently scheduled and sent once network is available.

*Worklist security (informative):* the Worklist is encrypted and saved to internal device storage (not shared or accessible by traditional means); the saved copy is auto-deleted at device start once older than 24 hours; every device encrypts differently; the administrator can disable the offline Worklist feature via the web configuration tool.

## MVR Remote App

**Description:** MVR Remote App is MediCapture's Android application (smartphone or tablet) providing remote (wired or wireless) control and monitoring of MVR/MTR recorders. **Compatibility:** Android 6.0 and newer. **Availability:** Google Play Store. **Price:** free.

* **Remote operation:** the tablet becomes a full, ergonomic remote control.
* **Remote MVR manager:** browse and review all patient files, annotate, zoom, report, and print — manage the complete archive of the recorder.
* **IT remote access:** access the device through the hospital facility network for remote maintenance, setup, or upgrades.

**Compatible hardware:** MVR, MVR Pro, MVR Lite, MVR 4K. MVR Lite requires the additional **Connect Upgrade Package** for network connectivity.

### Using a Tablet as an External Touchscreen Monitor (USB cable)

Available on all MVR-series types: MVR Lite (MVR400), MVR (MVR420), MVR Pro (MVR409). Connecting via USB cable charges the tablet continuously while the MVR is powered; no User Account or Remote Access activation is required — the tablet remains permanently connected, ready for viewing/operation/charging.

**Operating:** turn on the recorder and tablet, open the MVR Remote App; if the Login field is greyed out, tap USB tethering (and ensure USB tethering is enabled on the tablet), close Settings, select the connected device, and tap LOG IN — the tablet now shows the full MVR UI. **Exiting:** go to the MVR home screen and LOG OUT. **Standby:** it's recommended to leave both devices on (low energy use, tablet stays charged); to power down fully, turn off both units rather than leaving them in standby.

### Using a Tablet as a Handheld Remote Control (wireless)

Available for MVR (MVR420) and MVR Pro (MVR409) with networking. MVR Lite requires the Connect Package (network activation key + USB-to-Network adapter) connected to a Wi-Fi router via LAN.

**Preparations:** Remote Access must be activated (Advanced Settings > Connections); User Accounts with individual passwords must be enabled (at least one account). On the tablet: either connect its Wi-Fi to the same router as the MVR, or turn on a Wi-Fi hotspot on the tablet and connect the MVR to it (keep the tablet from powering off completely, or the connection may drop).

**Operating:** turn on the MVR (ensure it shows the Home screen) and the tablet, open the MVR Remote App, select the device, log in with either the general Remote Access password or a User Account name/password. The tablet then shows the full MVR UI. Note: in user-account mode, the MVR automatically stops the application after 10 minutes if no recording session has started, to prevent unauthorized access. **Exiting:** Home screen, then LOG OUT. **Standby:** leave both devices on to keep the Wi-Fi connection active; charge the tablet whenever not in use.

### Downloading Data to the Tablet

Copying data to the tablet stores sensitive data locally on it — the operator is responsible for handling it per local data-security regulations; the administrator must enable "Local storage" in MVR settings first. **Copying studies** (MVR420/MVR409 only): in Archive, select the source storage, tap Copy, choose the tablet as the destination, tap Continue, and wait for the Success message.

**MVR Local Archive:** after closing the Remote App, open the separate "MVR Local Archive" app to view/edit data stored on the tablet the same way as on the recorder itself, including local patient-data editing.

**Installation and updates:** ensure the recorder has the latest firmware. Install/update the MVR Remote App from Google Play if internet access is available on the tablet; otherwise contact MediCapture for a download link, copy the `.apk` to a USB stick (a USB-A to USB-C adapter may be needed), and install/update it by browsing to the file on the tablet.

## After-Market Support and Integration

MediCapture provides traceable firmware upgrades to address issues and add usability/features. The upgrade process is easy, reliable, and field-performable by the user; to maintain integrity, all software parts are updated to a new version at once. MediCapture releases non-mandatory enhancements roughly every six months, free of charge for the entire product lifetime. MediCapture owns all parts of the software/firmware — OS, applications, DICOM, and other communication modules — so once a device or feature is sold there are no recurring fees, license expirations, or other time-limited conditions.

MediCapture video recorders are designed to be part of a larger medical imaging system: beyond video recording and image capturing, they add network connectivity, user management, patient information, file management, editing, annotation, reporting, printing, streaming, DICOM, and tablet-based remote control to an existing imaging setup.

# 


