# **External Web Applications**

## **Overview**

The External Apps feature for MVR/MTR recorders and MSP smart panels allows users to access and control smart devices on the local network or launch web tools directly through the recorder's built-in web browser. An external app acts as a shortcut (URL) pointing to either an **external website / web application** or an **internally hosted web application**.

## **Target Devices & Medical Use Cases**

Designed for medical environments, this feature provides direct control over local network devices and surgical utilities, including:

* Video switch matrices  
* Intelligent camera controllers  
* Surgical light controllers  
* Web-based help portals and guidance systems  
* Custom medical utilities and AI visualization tools

### **Empowering Custom Medical Workflows**

While off-the-shelf software cannot address every specialized surgical or hospital requirement, MediCapture empowers users, healthcare facilities, and integration partners to quickly create tailored web applications for their exact clinical needs. Leveraging modern AI coding agents, custom web apps and control interfaces can be developed in as little as 15 minutes—from initial specification to first test deployment on a Class I medical device.

## **Navigation & Configuration**

**Navigation Path:** Settings ➤ Advanced Settings ➤ Connections ➤ External apps

To activate the feature, toggle the **Enabled** slider on the settings screen.

### **Adding Applications**

* **Internally Hosted Web App (+ button):** Tap the **\+** icon to add a new internally hosted app by uploading its .zip package.  
* **External Web App (Link button):** Tap the **Link** icon to add an external web app or website by providing its URL (HTTP or HTTPS address and port).

### **App Metadata & Auto-Discovery**

When creating or editing an app:

* **Custom Name & Description:** Can be specified for each entry.  
* **Favicon:** Discovered and assigned automatically by the system.

## **Per-App Advanced Settings**

Each application includes configurable options:

* **Block Screensaver:** Prevents the device screensaver from activating while the application is active.  
* **Run in Live Study (Camera Preview Overlay):** Allows the app to run directly over the live camera preview during a Study. Useful for:  
  * Custom live video annotations  
  * aiScope inference result visualizations  
  * Real-time telemetry or graphic overlays  
  * *Note:* When enabled, the web app icon is also displayed on the Start card during an active Study.  
* **Fix 16:9 Canvas:** Enforces a fixed 16:9 aspect ratio canvas when the app is displayed in the Upper or Lower split-screen view. When a web app runs in portrait mode within an enforced 16:9 canvas, the space beneath the 16:9 area displays External App cards to quickly launch another application.  
* **Default Home App:** Up to two applications can be designated as default home apps to launch automatically upon startup and user login—one assigned to the upper screen half and another assigned to the lower screen half.

## **Custom Web App Packaging & Upload Rules**

For internally hosted web applications:

1. Package the web application files into a .zip archive.  
2. Ensure the main entry point is named index.html and is located in the **root directory** of the zip archive (not inside any subfolder).  
3. Copy the .zip file to a USB drive and connect it to the recorder device.  
4. Select the app on the settings screen, tap **Upload web**, and select the .zip file from the USB drive.

### **Pre-loaded and Internally Hosted Web Apps**

* **URL Endpoints & Port Allocation:**  
  * Pre-loaded internal apps run locally at http://localhost:3335/1, http://localhost:3335/2, up to slot 99\.  
  * User-uploaded apps are served at http://localhost:3335/100 and above.  
* **Persistence & Updates:** Pre-loaded internal apps **cannot be deleted**, but their content can be updated at any time by re-uploading a new .zip archive.

## **List Management**

* **Rearranging Apps:** Tap the arrow buttons to reorder how app shortcuts appear on the Start screen.  
* **Edit & Delete:** Any custom app can be edited or deleted. (Pre-loaded apps are locked against deletion).

## **User Interface & System Behavior**

### **Navigation & Window Behavior**

* **Start Screen Shortcuts:** App icons appear in a horizontal bar of app cards on the Start screen and in the lower screen half. Tapping an app card launches the app in the respective upper or lower screen half.  
* **Background Execution:** Web apps behave like tabs in a regular browser. Closing the browser window by tapping the **"X"** button in the top-left corner of the header keeps the browsing progress running in the background, allowing you to resume from the exact same point when reopening the app. Background activity remains active until the user logs out or restarts the device.

### **Header Controls & Floating Action Button (FAB)**

* **Header Visibility:** When opened, the browser window initially hides the header navigation bar. Tap the **Floating Action Button (FAB)** to reveal the navigation bar.  
* **FAB Dragging & Positioning:** The FAB can be dragged to a less obstructive location on screen or docked along the upper edge of the view to minimize its footprint. In 16:9 mode, the FAB can also stick directly beneath the view window.  
* **Navigation & Audio Controls:**  
  * **Reload:** Tap the **Reload** icon on the right side of the screen header (next to the app icon) to refresh current web page content.  
  * **Back:** Tap the **\<** button in the right corner of the header to navigate back to the previous page.  
  * **Sound Controls:** The header automatically provides audio controls when the active web app uses sound.

## **Designing Web Apps for MVR/MTR/MSP Devices**

When developing custom web applications for MVR, MTR, or MSP devices, follow these core development rules and leverage built-in integration capabilities:

### **Core Rules**

* **Standard Web Architecture:** Build the application as a standard website or web application using standard HTML, CSS, and JavaScript.  
* **No External Dependencies:** Ensure all scripts, stylesheets, fonts, and media assets are contained locally within the uploaded package and referenced relatively. Do not rely on external CDN links or online libraries, as local network setups may lack internet access.

### **Integration Possibilities for Web App Designers**

* **Device Awareness & Licensing (window.MvrOverlay):** Custom web apps can detect whether they are running inside an MVR device, read hardware model and firmware information, and check active feature licenses (e.g., AI Scope, PACS/DICOM, 4K).  
* **Live Study & Recording State Feeds (SSE):** Real-time Server-Sent Event (SSE) streams (/study/events) push live recording state changes (start, pause, resume, stop), snapshot triggers, and camera signal updates directly to the web app without polling.  
* **Real-Time Vision-AI Data Stream:** The /ai/events feed delivers continuous live inference results directly from the built-in aiScope vision AI inference engine to the web app for displaying live graphic overlays or diagnostic indicators.  
* **Custom Medical Timeline Logging:** Web apps can write custom events, markers, and notes into the active medical study's timeline (timeline.ndjson) using native bridge methods (injectTimelineEvent).  
* **Interactive Touch Gesture Control:** When running as a transparent overlay over active camera views, web apps can use native gesture reporting (reportInteractive()) to intercept touch inputs while letting underlying native controls remain accessible.

# MVR web-app JavaScript bridge (`window.MvrOverlay`)

When an external web app is opened inside the MVR device (either in the normal
side-by-side pane or as the transparent **"Run over active Study"** overlay),
MVR injects a JavaScript bridge object into the page as `window.MvrOverlay`.

This lets a web page:

- **detect that it is running inside an MVR device** (rather than in an ordinary
  desktop/mobile browser), and
- read basic, non-sensitive **device identity** (device ID, hardware model, app
  and firmware version), and
- check whether a **paid feature** is activated on the device, and
- read the current active **study path**, and
- read the current **recording status**, and
- (overlay mode only) opt a touch gesture out of native click-through.

The bridge is attached to every external web app configured on the device, over
both `LOCAL` and `HTTP(S)` schemes. On any other browser the object simply does
not exist.

> Availability note: the bridge is a native
> [`@JavascriptInterface`](https://developer.android.com/reference/android/webkit/JavascriptInterface)
> object. All methods are synchronous and return primitive values (strings /
> numbers / booleans / null). Only methods annotated for JavaScript are
> callable; nothing else on the object is accessible.

---

## Detecting the MVR device

Feature-detect the bridge before using it. Its presence is itself the signal
that the page runs inside MVR:

```js
const onMvr = !!(window.MvrOverlay && window.MvrOverlay.getDeviceId);

if (onMvr) {
    // running inside an MVR device
} else {
    // running on an external PC / plain browser
}
```

---

## Device identity

### `window.MvrOverlay.getDeviceInfo() → string (JSON)`

Returns all device identity fields as a JSON string. Parse it with
`JSON.parse`. The `firmware` key is omitted when the firmware version is not
available on the device.

```js
const info = JSON.parse(window.MvrOverlay.getDeviceInfo());
// {
//   "deviceId":   "A1B2C3D4",   // device serial / ID (hex string)
//   "model":      "MVR-PRO",    // hardware model name (upper case)
//   "appVersion": 260704,       // app version code, integer (see note below)
//   "firmware":   "1.2.3"       // firmware version string (key omitted if unknown)
// }
```

The `deviceId` is the same value shown on the device **INFORMATION** screen
(field **ID**) and printed on the unit's label, so it is safe to display or log
in the web app.

### Individual getters

The same values are also available one at a time:

| Method | Returns | Notes |
| --- | --- | --- |
| `getDeviceId()` | `string` | Device serial / ID, hex string. Same as INFORMATION-screen **ID**. |
| `getModelName()` | `string` | Hardware model name, upper case. Same as INFORMATION-screen **HW**. |
| `getAppVersion()` | `number` | App version code, integer. See note below. |
| `getFirmwareVersion()` | `string \| null` | Firmware version, or `null` if unavailable. |

```js
const id    = window.MvrOverlay.getDeviceId();
const model = window.MvrOverlay.getModelName();
const app   = window.MvrOverlay.getAppVersion();       // e.g. 260704
const fw    = window.MvrOverlay.getFirmwareVersion();  // may be null
```

> **App version format.** The value is derived from the build date. It is the
> lower 6 digits of a `yyyyMMdd` build stamp (i.e. `yyMMdd`) — for a build made
> on 2026-07-04 the value is `260704`. Larger numbers indicate newer builds, so
> a numeric comparison is a reliable "newer than" check within the same century.

---

## Paid features

### `window.MvrOverlay.hasFeature(id) → boolean`

Returns `true` when the paid feature `id` is activated on this device. Feature
IDs are stable strings:

| Feature ID | Feature |
| --- | --- |
| `mvr_pro_4k` | 4K recording |
| `mvr_pro_pacs` | DICOM / PACS |
| `mvr_435_activation` | MVR unlock (the `435` in the name is historical) |
| `mvx_441_activation` | MVX441 |
| `mvr_aiscope` | AI Scope |

```js
if (window.MvrOverlay?.hasFeature?.('mvr_aiscope')) {
    // AI-Scope UI
}
```

Notes:

- Only the on/off state is exposed. The activation keys themselves are **not**
  readable from a web app.
- An unknown feature ID returns `false`.

---

## Active study

### `window.MvrOverlay.getCurrentStudyPath() -> string | null`

Returns the current active study folder path, or `null` when there is no active
study.

```js
const studyPath = window.MvrOverlay?.getCurrentStudyPath?.() ?? null;

if (studyPath) {
    // e.g. "CASE0001" or another MVR study folder path
}
```

Notes:

- The value is the study path used by MVR for the active study folder.
- This method is read-only. It does not create, start, finish, or change a
  study.

---

## Recording status

### `window.MvrOverlay.isRecordingActive() -> boolean`

Returns `true` when the main video recorder is currently active. A paused
recording is still considered active because recording has been started and the
current recording file/session has not been stopped yet.

```js
const recordingActive = window.MvrOverlay?.isRecordingActive?.() === true;
```

### `window.MvrOverlay.getRecordingState() -> string`

Returns the exact main recording state:

- `"STOPPED"` — no main recording is active.
- `"RUNNING"` — main recording is actively writing video.
- `"PAUSED"` — main recording is started but currently paused.

```js
const state = window.MvrOverlay?.getRecordingState?.() ?? "STOPPED";

if (state === "RUNNING" || state === "PAUSED") {
    // recording is active
}
```

Notes:

- These methods are read-only. They do not start, stop, pause, or resume
  recording.
- The status is the current in-device state at the moment the method is called;
  call it again when you need a fresh value.

---

## Study timeline: inject a custom event

During an active study MVR keeps a **timeline** of events (study start/finish,
snapshots, recordings, signal changes, …) as a `timeline.ndjson` file inside the
study folder. A web app can add its own **external** events to that timeline.

### `window.MvrOverlay.injectTimelineEvent(json) → boolean`

Records one custom event into the current study's timeline. The argument is a
**JSON object string**; its fields are stored alongside the event. The record is
written as an `"ext"` event with `"ip":"localhost"` and an `"ts"` timestamp
(epoch milliseconds) added by MVR:

```js
const ok = window.MvrOverlay?.injectTimelineEvent(
    JSON.stringify({ marker: "incision", note: "step 1" })
);
// -> resulting timeline line:
// {"ts":1751731200000,"ev":"ext","ip":"localhost","marker":"incision","note":"step 1"}
```

Returns:

- `true` — the event was accepted for recording.
- `false` — there is **no active study** (or it is already finished), or the
  argument is not a valid JSON object.

Notes:

- The study folder is created lazily. Injecting an event **triggers folder
  creation** (like a capture/recording does): the first event on its own is
  enough to materialize the study folder and its `timeline.ndjson` on disk.
- The reserved keys `ts`, `ev` and `ip` are always set by MVR and cannot be
  overridden by the supplied JSON.
- The call is best-effort and returns immediately; the actual disk write happens
  asynchronously.

---

## Active-study overlay: touch pass-through

Only relevant when the web app runs as the **"Run over active Study"** overlay
(transparent layer on top of the live camera preview, with native controls
still tappable underneath).

### `window.MvrOverlay.reportInteractive() → void`

By default a touch on the transparent overlay passes **through** to the native
control underneath. Call `reportInteractive()` from a page gesture handler to
claim that gesture for the web page instead, so the tap is **not** forwarded to
native controls.

```js
element.addEventListener('pointerdown', () => {
    // this tap is for the web UI, not for the native control behind it
    window.MvrOverlay?.reportInteractive();
});
```

Notes:

- The overlay's own chrome (FAB / toolbar) always blocks pass-through; you only
  need `reportInteractive()` for your page's own interactive content.
- The overlay and AOI (area-of-interest) editing are mutually exclusive, since
  AOI's drag handles can't receive touch through the overlay.
- Calling `reportInteractive()` outside overlay mode is harmless (no effect).

---

## Compatibility

- Always feature-detect (`window.MvrOverlay?.method`) — the object is absent in
  ordinary browsers and on MVR firmware predating this bridge.
- All fields are read-only; the bridge exposes no control over the device.
---

# MVR HomeWeb API (live study, AI, and device data)

The **HomeWeb** server hosts the self-hosted web apps of the device. Each one has
a slot and lives in its own sub-folder: `homeweb_<slot>.zip` in the iMave folder,
served at `http://<device>:3335/<slot>/` (slots 1–99 ship with the firmware,
100+ are uploaded by the user). In addition to serving static files it exposes
**Server-Sent Events (SSE)** endpoints that push live device events to the
browser as they happen — no polling required.

Reference your assets **relatively** (`href="styles.css"`), so the page works
under its sub-folder. A bundle that references them from the root
(`/assets/x.js`, the Vite/React default) still loads — the server falls back to
the `Referer` to find the app — but relative paths avoid relying on that.

Two independent SSE feeds exist:

| Feed | SSE endpoint | Poll fallback | Payload |
|------|--------------|---------------|---------|
| **Study / recording** | `GET /study/events` | `GET /study/latest` | one timeline event per message |
| **Vision-AI** | `GET /ai/events` | `GET /ai/latest` | one inference result per message |

Both are **unidirectional** (device → browser). The browser cannot push back
over these; to *write* an event into the study timeline from the page, use
`window.MvrOverlay.injectTimelineEvent(...)` (see
[`MVR_webapp_bridge.md`](MVR_webapp_bridge.md)). Device identity and paid-feature
activation are not served here either — they are read from the same bridge
(`getDeviceInfo()`, `hasFeature(id)`), which is not reachable from an ordinary
browser on the network.

> This document covers the **HomeWeb browser app** only. The transparent
> "Run over active Study" **overlay** WebView uses the separate, pull-only
> `window.MvrOverlay` bridge and does **not** receive these SSE feeds.

---

## Study / recording feed — `/study/events`

This is the feed to use for notifications about **snapshot**, **recording
start/stop**, and **recording pause/resume**, plus study lifecycle and signal
changes. It mirrors, line for line, exactly what the device records to the
study's `timeline.ndjson` — so the browser sees the same authoritative event
stream the device persists to disk.

### Event schema

Each SSE message's `data` is a single JSON object. Every object has:

- `ts` — event time, epoch milliseconds (number)
- `ev` — event name (string)

plus event-specific fields:

| `ev` | Meaning | Extra fields |
|------|---------|--------------|
| `study_start`  | A study session began | `folder_name`, `device_id` |
| `study_finish` | The study session ended | — |
| `rec_start`    | Recording started | `file_name` |
| `rec_pause`    | Recording paused | `file_name` |
| `rec_resume`   | Recording resumed | `file_name` |
| `rec_stop`     | Recording stopped | `file_name` |
| `rec_error`    | Recorder error | `file_name` |
| `snapshot`     | A snapshot/photo was saved | `file_name` |
| `signal_good`  | A camera input got signal | `input_name`, `signal_resolution` |
| `signal_lost`  | A camera input lost signal | `input_name` |
| `signal_change`| Input mode / view layout changed | `mode`, `inputs` (array) |
| `ext`          | External event injected via API or `injectTimelineEvent` | `ip`, plus caller fields |

> The `snapshot`, `rec_*`, `signal_*` set may grow — treat an unknown `ev` as a
> pass-through and switch only on the names you care about.

### Example

```js
const es = new EventSource('/study/events');

es.addEventListener('message', (e) => {
    const ev = JSON.parse(e.data);
    switch (ev.ev) {
        case 'rec_start':  onRecordingStarted(ev.file_name); break;
        case 'rec_stop':   onRecordingStopped(ev.file_name); break;
        case 'rec_pause':  onRecordingPaused(); break;
        case 'rec_resume': onRecordingResumed(); break;
        case 'snapshot':   onSnapshot(ev.file_name); break;
        // study_start / study_finish / signal_* / ext ...
    }
});
```

### Rebuilding current state on connect

When a browser connects **mid-study**, the server immediately replays the most
recent buffered events (up to a few hundred) so the page can reconstruct the
current recording/signal state — you do not have to wait for the next live
event. Fold over the replayed events on load to compute "am I recording right
now?" rather than assuming a clean start.

If you only need a single most-recent value (e.g. a lightweight poll from a page
that can't hold an SSE connection open), `GET /study/latest` returns the last
event object as JSON (or `{}` if none yet).

---

## Vision-AI feed — `/ai/events`

Real-time vision-AI inference results, one JSON object per message, forwarded
verbatim from the on-device native inference process. This is a **latest-only**
feed: a freshly connected browser receives the most recent result immediately,
and there is no history replay. `GET /ai/latest` is the poll fallback.

```js
const es = new EventSource('/ai/events');
es.onmessage = (e) => render(JSON.parse(e.data));
```

---

## Reconnection & delivery semantics (both feeds)

- **Auto-reconnect.** `EventSource` reconnects automatically if the connection
  drops; the server advertises a 3 s retry hint.
- **No duplicates across reconnect.** Every frame carries an SSE `id:`. On
  reconnect the browser automatically sends the last id back via the
  `Last-Event-ID` header, and the server resumes from the next event — you will
  not re-receive events you already processed. (This resume works within the
  server's replay window; after a very long disconnect, older buffered events
  may have aged out.)
- **Keep-alive.** A `: ping` comment line is sent every 15 s so idle connections
  and dead sockets are detected promptly. `EventSource` ignores comment lines;
  you never see them as messages.
- **Back-pressure.** Each client has a bounded per-connection queue; if a browser
  falls badly behind, the oldest queued frames are dropped rather than stalling
  the device. A slow page can therefore miss intermediate events — reconcile
  against state, don't assume every single frame is delivered under overload.
- **Overload.** The AI feed is latest-only by design, so drops there just mean
  "you got a newer frame instead."

---

## Availability / lifecycle notes

- The HomeWeb server (and therefore these endpoints) runs **only** when a
  `LOCAL`-type external web app is configured/enabled on the device. When it is
  off, the endpoints are unreachable.
- The server is **not** tied to a single study — it stays up across studies while
  the home app is enabled. One SSE connection therefore spans multiple studies:
  it delivers `study_finish` for one study and later `study_start` for the next
  over the same stream. **Reset your per-study UI state on `study_start`** (and
  keep in mind the replay buffer on connect may include the tail of a just-ended
  study). A connection actually closing means the home app was disabled or the
  device restarted — treat that as "reconnect", which `EventSource` does for you.
- Both feeds share the same origin/port as the served web app (`:3335`) and live
  at the server root, shared by every hosted app, so
  `new EventSource('/study/events')` just works from any hosted page. A path
  relative to the app's own sub-folder (`new EventSource('study/events')`, which
  resolves to `/<slot>/study/events`) is served as well.

---
