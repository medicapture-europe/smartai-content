# MediCapture MVR and MTR Recorders: Features

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
