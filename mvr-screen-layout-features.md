# Screen Layout and View Features of MVR and MTR series devices

Dual View, Video Mode Menu, On-Screen Indicator Tally Light (OTL), Area of Interest (AOI) and Split View.

## Dual View and Portrait Screen Orientation

Applicable device models: MVR435, MVR436, MVR450, MTR133, MTR156.

Available since firmware version FW 250326.

Category: New usability feature.

Workflow stages: Study, Archive, Settings.

Purpose: Enable comparison of the two cameras, live (real-time) camera view with a previous recording, and comparison of two recordings. Application examples: review recordings “Before” and “After” looped playback of the recordings from the fluorescence camera or ICG (IndoCyanine Green) video as a reference to the live surgery footage.

There are recorders on the market that allow for the simultaneous recording and review of two video channels. Typically, the standard landscape layout is used, featuring two small windows - one for each camera's live preview or playback. Our solution maximizes the usage of the screen area by taking advantage of a portrait orientation.

Dual View is compatible with all new device models; however, some models may not be suitable for this feature. For example, the MVR460 is unsuitable for portrait orientation, and its built-in 7-inch touchscreen is too tiny for dual-view interaction. The suitable models for the application requiring Dual View are MTR156 and MVR450 or MVR436 with MTS156 monitor. MTR133 can be used when there are restrictions on the device size.

### Usage

Change screen orientation to Portrait: In the Settings screen, navigate to “Settings - System - Display” and set Display rotation to 90 or 270 degrees. On MTR devices the same setting is reachable from the INFORMATION screen: tap Display settings and select a screen rotation of 90° or 270°. An external monitor, MTR156 or another model, should be mounted in portrait orientation. Dual View will be enabled automatically, and more options will be displayed at the bottom of the screen. Typically, the screen is split vertically in half between two views, but the top view occupies 75% of the screen area when no selection is made for the bottom view. The size ratio is automatically controlled and cannot be adjusted by the user. It is possible to interact with both views simultaneously using the touchscreen, and the two views operate independently from each other, in principle.

During the Live Study, several options are available for display at the bottom of the screen, under the live footage of the current camera: another camera or an Archive. The screenshot below on the right shows an example of a comparison between live footage from a microscope camera and recorded footage from the fluorescence camera, which was captured a few minutes earlier.

When two cameras are shown live, recordings can be made independently for both cameras unless Parallel Recording is enabled. The bottom camera displays fewer controls: a Capture and Record button, and an ”X” sign to close the camera’s live view. Top and bottom cameras can be easily swapped by tapping on the Input select button (marked as “1/2").

The archive screen allows a review of another Study under the current selected Study. The study below can be the same as the one above, or it can be a study recorded at a different time, or a study from a different storage location. For example, a Study on Internal Storage can be compared to a Study on Network Storage. In both views, images and videos can be played, edited, or zoomed independently at the same time. When both videos contain soundtracks, both audio tracks will play simultaneously. All controls and interactions are identical to those in the regular single-view mode.

This allows for comparison between “before” and “after” footage, or footage from different cameras or patients. Portrait screen orientation also allows larger previews of the reports in the portrait layout. Examples are presented in the screenshots below.

### Advantages of Portrait Orientation

By rotating the user interface 90 or 270 degrees, the display transforms into a vertical workstation, offering several key advantages:

- Dual View Functionality: The screen is logically split. The top half displays the live camera feed in its native aspect ratio, while the bottom half provides access to the user interface, Archive browser, or external applications.
- Dual Camera Operation: You can display a secondary camera's live feed below the primary camera, enabling independent image capture and video recording for both sources simultaneously.
- Live Study with Archive Review: This allows you to review previous recordings as a reference during a live procedure. For example, you can have a looped playback of blood flow captured by a fluorescent camera on the bottom half while performing live surgery under visible light on the top half.
- Optimized for Medical Carts: Portrait orientation is ideal for space-constrained environments, allowing for a slimmer equipment profile on medical carts or integrated towers where horizontal desk space is limited.
- External App Integration: This mode is particularly powerful when combined with our External Apps feature. You can run third-party web applications—such as surgical light controls, video matrix switchers, or hospital-specific web portals—on the bottom half of the screen. This allows you to manage the operating room environment from a single vertical display without losing sight of the live video feed.

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
