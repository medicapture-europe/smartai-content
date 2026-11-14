# MVX441 Video Matrix — Product Knowledge Base

> Audience: AI assistant for customer support, partner technical support and sales. Covers
> what the MVX441 is, how to install, operate and configure it, its operating modes, the
> Matrix Control UI and its settings, and how it fits into a MediCapture OR integration.
> Control-protocol (API) details are intentionally excluded; API command documentation is
> available from MediCapture upon request for system integrators.
>
> Sources: MVX441 Instructions for Use (firmware V1.10.05 / V1.00.02 and higher) and
> Matrix Control UI version 261110.

---

## 1. What is the MVX441?

The **MediCapture MVX441** is a **medical-grade 4×4 HDMI video switching matrix** — a
seamless, high-speed video routing system for the operating room (OR) and other
professional healthcare environments. It takes up to **4 HDMI video sources** (endoscope
camera systems, surgical microscopes, C-arms, ultrasound, room/PTZ cameras, PCs, video
recorders, etc.) and routes them to up to **4 HDMI destinations** (surgical displays,
wall monitors, video recorders).

Key characteristics:

- **4K60 4:4:4 seamless switching** — sources change on a display without black frames or
  resyncing delays.
- **Multiview**: one output can show several sources at once on a single screen
  (PiP, dual, triple, quad layouts).
- **Built-in scaling**: every output can independently upscale/downscale to match the
  connected display.
- **Web-based control**: managed via the **Matrix Control UI**, a touch-friendly web
  application, pre-installed on MediCapture MSP Smart Control Panels and MTR Touchscreen
  Recorders (it can also run from any browser on the same network).
- **Medical device**: non-invasive, active **Class I** medical device (EU MDR 2017/745,
  FDA Class 1). IEC 60601-1 safety, fanless (silent, passive cooling), IP20, equipotential
  bonding pole, medical-grade external power supply.
- Compact: 270 × 166 × 30 mm, 1.25 kg, white steel housing (RAL9016) with aluminum front.

**Intended use:** interconnection of medical Class 1 imaging devices with HDMI video
output or HDMI video input. Not for diagnosis; not for measuring clinical parameters; no
applied parts (no patient contact). Users: qualified healthcare professionals in
professional healthcare indoor environments. Applies to firmware **V1.10.05 / V1.00.02**
and higher.

---

## 2. Operating modes

The MVX441 has two operating modes selectable in the Matrix Control UI
(Settings → Interface Settings → Mode Selection):

### 2.1 Matrix mode

Independent 4×4 crosspoint. Each of the 4 outputs shows exactly one selected source; any
source can go to any number of outputs simultaneously.

A **Switching Mode** setting controls how the picture changes on a route change:

- **Seamless** — any source can be routed to any output; resolution and color are
  automatically converted (scaled) to the output's setting, and switching an output from
  one source to another is seamless — the monitor never blinks black. Side effect: minor
  video processing latency of under 2 frames (under 30 ms at 60 fps; see §12).
- **Bypass** — the signal passes through without any processing (no scaling, conversion
  or overlay), with zero added latency. Output resolution and chrominance equal the
  selected source (the Resolution/Chrominance settings are greyed out). Side effects: the
  monitor may show black for a few seconds while re-syncing when the source changes, and
  the monitor stays black if it does not support the source's signal format (e.g. a 4K
  source on an HD-only monitor).

**Test pattern (Matrix mode only):** each destination tile has a **Pattern** button. Tap
it to send a test pattern to that output — useful for checking cables and monitors when
no source is connected. Tap it again to return to the previous source. The pattern style
is selected in Interface Settings (§6.4).

### 2.2 Multiview mode

**Output 1** becomes a composite screen combining multiple sources in a selectable layout
("Scene"). While Multiview is active:

- **Output 1** — the Multiview composite (processed, seamless).
- **Outputs 2 and 3** — switch to Bypass mode (unscaled, independent single-source
  outputs, zero latency).
- **Output 4** — can be configured as a **copy** of output 1, 2, or 3 ("Copy From") —
  useful, for example, to record exactly what a display shows. If outputs 1–3 are all
  disabled, copying is unavailable.
- The **Switching Mode** setting is greyed out (it applies to Matrix mode only).
- Output resolution and chrominance are set on **Output 1** only, and apply to all
  outputs. The Multiview resolution defaults to 1920×1080p60. Matrix mode and Multiview
  mode each remember their own resolution settings.

Available Multiview scenes (layouts):

| Scene                                                 | Description                                                                                                            |
| ----------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Full Screen                                           | Single source, full screen                                                                                             |
| PIP Top-Left / Top-Right / Bottom-Left / Bottom-Right | Large main picture with small inset picture; inset size selectable (Small / Medium / Large via the "PiP Size" setting) |
| Dual View                                             | Two sources side by side                                                                                               |
| Triple                                                | One large + two stacked                                                                                                |
| Quad 1                                                | One large left + three stacked right                                                                                   |
| Quad 2                                                | One large top + three across the bottom                                                                                |
| Quad 3                                                | Classic 2×2 quad split                                                                                                 |

To fill a Multiview layout: tap the **SCENE** button on output 1, pick a layout, then tap
a **source**, then tap the **tile** in the layout where that source should appear; repeat
per tile. For output 4, tap its **Copy** button and choose which output to copy.

### 2.3 Video wall (not offered)

The underlying hardware also supports a video-wall mode (e.g. 2×2, 4×1 configurations).
**MediCapture does not promote video-wall mode and provides no controls for it in the
Matrix Control UI.** If a customer asks: it is not a supported/offered function of this
product.

---

## 3. Hardware overview

### 3.1 Front panel

| Control                | Function                                                                                                                                                                                                                  |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **POWER button + LED** | Short press: power on. Press ~1 second: standby. LED green = operating, red = standby. Device powers on automatically when power is applied (useful for video towers / ceiling supply units with a central power switch). |
| **Key 1**              | Info display: shows the matrix IP address and other device info on all connected HDMI display outputs.                                                                                                                    |
| **Key 2**              | Long press (beep) toggles network mode DHCP ↔ static IP. Requires a power-off/on reboot to take effect.                                                                                                                   |
| **Key 3**              | No function assigned (reserved for future use).                                                                                                                                                                           |
| **Key 4**              | Long press (beep): **complete factory reset, including the matrix IP address**.                                                                                                                                           |

Each key has a green activation LED. Keys 1–4 can be **locked** in the Matrix Control UI
(Advanced Settings → Front Panel Control → Front Panel Lock) to prevent accidental
operation; when locked, the keys do not respond. Boot takes under 15 seconds; the power
LED indicates the boot sequence. The device is intended to remain powered continuously so
it can react to control commands at any time. After booting it restores the last used
routing configuration.

### 3.2 Back panel

| Connector              | Description                                                        |
| ---------------------- | ------------------------------------------------------------------ |
| **LAN / Network**      | RJ45, Ethernet 100/1000 Mb/s — TCP/IP control (Matrix Control UI). |
| **Equipotential pole** | 6 mm pole connector (DIN 42801-2) for potential equalization.      |
| **Input 1–4**          | HDMI Type A inputs (signal sources).                               |
| **Output 1–4**         | HDMI Type A outputs (displays/recorders).                          |
| **DC 12V**             | 12 V / 3.0 A input for the supplied medical-grade power adapter.   |

**Warning:** do not connect/disconnect video cables while the power is on; the device gets
warm (normal for the fanless design) — let it cool before recabling. Do not stack devices
on top; ensure adequate air cooling.

---

## 4. Installation and first setup

1. Connect the DC power cord to the device, then the AC cable to the external power
   supply. The device powers on automatically.
2. Connect at least one display to any HDMI output (to view on-screen device info).
3. Connect a network cable to the LAN port.
4. Connect all video inputs and outputs at the rear.
5. Connect the pre-configured MSP Smart Control Panel or MTR Touchscreen Recorder to the
   **same LAN**, and launch the Matrix Control UI.
6. Press **Key 1** on the matrix front panel — device info including the IP address is
   shown on the HDMI outputs. **Default IP address: 192.168.0.100.**
7. If the default address does not fit your network: long-press **Key 2** to switch to
   DHCP (Auto), reboot the matrix (power off/on), then press Key 1 to see the new
   DHCP-assigned address.
8. In the Matrix Control UI, enter the matrix IP address (Settings → Advanced Settings →
   Network Connection → **Connect**).
9. Review the Settings sections before first clinical use.

Static-IP tip: if the matrix stays at 192.168.0.100, put the control device on the same
segment (e.g. 192.168.0.12, mask 255.255.255.0).

**Safety requirement for the live surgical monitor:** when the matrix is used with a
visualisation system such as endoscopy, the monitor used for live viewing of the
procedure must have **fail-safe operation** (it switches to a backup input if no signal is
detected), and the video source must also be connected **directly** to that monitor's
backup input. This way the live picture is not lost if the matrix path is interrupted.

---

## 5. Matrix Control UI — daily operation (operator level)

The Matrix Control UI is designed for touchscreen use with large icon tiles. The **home
page** is where the OR operator (e.g. a nurse) works — no password required.

Typical daily workflow: start the matrix (if in standby) → start the control device (e.g.
Smart Control Panel) → switch on video sources → switch on displays → route video as
needed → power off.

- **Routing:** tap a **Source** tile, then tap the **Destination** tile that should show
  it. Done — switching is immediate.
- **Status indicators:**
  - Green dot on a source or destination — device detected and switched on.
  - Orange dot — not connected, not switched on, or not detected.
  - **Blue bar** under a destination — the routed source is active and recognised.
  - **Orange bar** under a destination — an inactive source is routed there; the
    destination shows nothing.
  - The connection status (Connected / Connecting / Disconnected / Device Standby) is
    shown in the UI.
- **Presets:** save and recall complete configurations by name — typically one preset per
  surgeon/operator or per procedure type.
  - Up to **4 presets**.
  - **Save:** type a name and tap the save (bookmark) button, or tap an empty slot.
  - **Recall:** tap a preset; it becomes the active preset. Tap it again to deselect it.
  - **Update:** tap the save icon on a preset slot to overwrite it with the current setup.
  - **Delete:** tap its delete icon and confirm.
  - A preset stores routing, mode and layout, labels/icons, output formats, tile order and
    the Timer/Stopwatch state. The Timer/Stopwatch state of the active preset is saved
    automatically; everything else changes only when you save the preset.
  - Presets are stored on and synced with the device, so any control panel connected to
    the matrix sees them.
- **Multiview scene selection** (when Multiview mode is enabled): SCENE button on
  output 1, layout selection, and per-tile source assignment (see §2.2).
- **Test pattern** (Matrix mode): Pattern button on a destination tile (see §2.1).
- **Optional tools:** count-down **Timer**, count-up **Stopwatch**, and a live **Clock**;
  each can be shown/hidden, repositioned, and the Timer/Stopwatch can be renamed (Interface
  Settings → Optional Tools).
- Short confirmation messages (toasts) appear after actions such as saving a preset or
  changing the password.

Names and icons: each source/destination tile carries a custom **label** and a **clinical
icon** chosen from a built-in library — None, C-Arm, Camera, Computer, Endoscope, HDMI,
Microscope, PTZ Camera, SDI, Surgical Light Camera, Headlight Camera, Surgical Robot,
Ultrasound, Vital Signs, X-Ray, Archive, Recorder, Media Player, Online Conference, and
numbered icons 1–4. The icon assigned to a source also appears on any destination
currently showing that source.

**Closing the Matrix Control UI on an MSP/MTR:** tap the round blue icon, then tap the
blue **X** at the top of the screen. To move the round icon, tap and hold it for one
second until it turns red, then drag it; the new position is saved.

---

## 6. Settings (administrator level)

Settings open from the home page (gear icon) into five sections. Four of them can be
**password-protected**; System Info is always accessible.

### 6.1 Password protection model — operator vs. administrator

The settings password is a **usage separation, not a security secret**:

- Its purpose is to protect settings from **accidental or unauthorized change** — an
  operator (nurse) can freely switch video, use presets and timers on the home page, but
  cannot (even accidentally) rename channels, change the operating mode, alter the IP
  address, etc.
- **Protected sections:** Advanced Settings, Interface Settings, Source Settings,
  Destination Settings. **Not protected:** the home/routing page and System Info.
- **No password is set by default.** The password is set, updated, or cleared in
  **Advanced Settings → Password Settings** (Set / Update / Clear; updating or clearing
  requires the old password). With no password set, all settings are open.
- Once unlocked, settings stay unlocked for the session; after **10 minutes of
  inactivity** they lock again automatically.
- **Forgot password:** there is no master password, and MediCapture has no access to it.
  Recovery = **"Forgot password?"** on the unlock screen, which resets the system to its
  default settings and permanently erases all settings, presets, and the password.

### 6.2 System Info (always accessible)

Read-only device information: Model, Firmware Version, MAC Address, IP Address, Web UI
Version, Network Mode (Static/DHCP), Power Status, Hostname, Subnet, Gateway, TCP/Telnet
status. The same basic info is available on the connected displays by pressing front-panel
Key 1.

### 6.3 Advanced Settings

- **Network Connection** — enter the matrix IP address and tap **Connect** so the Matrix
  Control UI connects to that matrix.
- **Password Settings** — set / update / clear the settings password (see §6.1).
- **Front Panel Control** — **Front Panel Lock** On / Off. On disables front keys 1–4 to
  prevent accidental operation (e.g. an accidental factory reset).
- **System:**
  - **Matrix Network Settings** — change the matrix's own network configuration: Network
    Mode (Static / DHCP), IP Address, Subnet, Gateway; tap **Set Network** to apply. The UI
    reconnects to the matrix automatically.
  - **Reboot Matrix** — the matrix restarts; video outputs and the connection drop for
    about 15–20 seconds.
  - **Reset to Default Settings** — restores all matrix and UI settings to factory
    defaults **except the IP address**. Labels, presets and the password are erased, and
    routing returns to input 1→output 1 … input 4→output 4. Cannot be undone.

Three ways to reset, from smallest to largest:

| Reset                                         | IP address | Settings, presets, password |
| --------------------------------------------- | ---------- | --------------------------- |
| "Forgot password?" (unlock screen)            | Kept       | Erased (UI defaults)        |
| Advanced Settings → Reset to Default Settings | Kept       | Erased (matrix + UI)        |
| Front panel Key 4 long press                  | Reset to 192.168.0.100 | Erased (complete factory reset) |

### 6.4 Interface Settings

- **Interface Title** — rename the UI header (default "Matrix Control"; e.g. "OR 3").
- **Mode Selection** — Multiview / Matrix (see §2; tooltip explains the output roles in
  Multiview).
- **Language** — English, Simplified Chinese, Traditional Chinese, German, French,
  Spanish, Russian. More languages are planned.
- **Switching Mode** — Seamless (auto conversion, no black blink, under 2 frames latency) /
  Bypass (unprocessed, zero latency, brief black on switch; see §2.1). Available in Matrix
  mode only; greyed out in Multiview.
- **Theme** — Dark Mode / Light Mode.
- **Pattern Style** — the test pattern used by the Pattern button (§2.1): Black, Blue,
  Color Bar, Gray Scale, Cross, Cross Hatch.
- **Font Size** — Small / Normal / Large.
- **PiP Size** — Small / Medium / Large (inset size in PiP scenes).
- **Date Format** — DD/MM/YYYY, MM/DD/YYYY, YYYY/MM/DD, YYYY-MM-DD.
- **Time Format** — 12-hour (AM/PM), 24-hour, HH:MM:SS.
- **Optional Tools** — show/hide and reposition the Presets, Timer, Stopwatch, and Clock
  panels on the home page; Timer and Stopwatch titles can be customized.

### 6.5 Source Settings (video inputs)

Per input 1–4:

- **Label** — name the connected device (e.g. "Endoscope", "C-Arm").
- **Signal Status** — green = source detected and active; orange = not connected, not
  switched on, or not detected.
- **Icon** — pick from the clinical icon library (§5).
- **EDID** — the capability the matrix reports to the source: "4K2K60 444, audio 2-ch" or
  "1080P, audio 2-ch". If a source is not recognised, changing the EDID may help.
- **Enabled / Disabled** — disable unused sources to make the home page simpler.
- **Position arrows** — move the input tile left/right so the on-screen order matches the
  physical location of the devices in the OR.

### 6.6 Destination Settings (video outputs)

Per output 1–4:

- **Label** — name the connected display/recorder.
- **Signal Status** — green = destination detected and switched on; orange = not
  connected, not switched on, or not detected.
- **Resolution** — output scaling target; choose a resolution the connected display
  accepts (check the display's technical data). Quick picks: Auto, 3840×2160 p60,
  1920×1080 p60. Full list: 4096×2160 p60/p50/p30/p25/p24, 3840×2160 p60/p50/p30/p25/p24,
  1920×1080 p60/p50/p30/p25/p24, 1920×1080 i60/i50, 1920×1200 p60rb, 1360×768 p60,
  1280×800 p60, 1280×720 p60/p50, 1024×768 p60, and **Auto**. Matrix mode defaults to Auto.
- **Chrominance** — output color format: RGB 4:4:4, YCbCr 4:4:4, YCbCr 4:2:2, YCbCr 4:2:0.
  Choose one the connected display accepts.
- Resolution and Chrominance are greyed out when Switching Mode is **Bypass**, because the
  output equals the source. In Multiview they are set on Output 1 only (§2.2).
- **Enabled / Disabled** — disable unused outputs to make the home page simpler.
- **Position arrows** — reorder the output tiles to match the physical layout of the OR.
- In Multiview mode, output 1 additionally has **Scene** selection, and output 4 has
  **Copy From** (copy of output 1, 2, or 3).

---

## 7. Integration with MediCapture MTR / MSP products

MediCapture's core products are **medical video recorders**. The Matrix Control UI comes
**pre-installed on the MTR and MSP series**:

- **MSP Smart Control Panels:** MSP156, MSP245.
- **MTR Touchscreen Recorders:** MTR133, MTR156, MTR245.

On these devices the matrix control is a paid feature: it must be **activated with
activation key AKMVX441** (the UI prompts "Activation Required" if not activated).

**Benefits of pairing the MVX441 with an MTR/MSP recorder:**

- **One screen for everything:** control OR video routing *and* recording from the same
  touchscreen.
- **Select what to record:** route any source (or a Multiview composite via output 4
  "copy") into the recorder.
- **Review anywhere:** play back recordings — or compare recordings — on any display in
  the OR by routing the recorder's output through the matrix.

The Matrix Control UI can also be opened from any modern browser on the same network
(it is a web application), and system integrators may control the matrix via a TCP/IP API
with their own interface (API documentation available from MediCapture on request).

---

## 8. Cabling and the OR ecosystem

The MVX441 targets the **integrated operating room**. Typical distance and signal-type
challenges are covered by MediCapture accessories:

- **Hybrid optical HDMI cables** — up to **100 m**, enough for OR boom-to-wall or
  wall-to-rack routing where copper HDMI cannot reach.
- **12G SDI-to-HDMI converters** — connect cameras and sources with SDI output (common on
  medical/broadcast cameras) to the matrix's HDMI inputs.
- DisplayPort or DVI sources connect via adapters.

---

## 9. Technical specifications (summary)

| Item                  | Specification                                                                                                                              |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Function              | 4×4 HDMI video matrix, seamless switching, one Multiview output                                                                            |
| HDMI standard         | HDMI 2.0b, 18 Gbps / 594 MHz bandwidth                                                                                                     |
| Input resolutions     | VGA–WUXGA (up to 1920×1200@60 Hz) and 480i–4K (3840×2160@60 Hz 4:4:4, 4096×2160@60 Hz 4:4:4)                                               |
| Output resolutions    | Up to 4096×2160p60 4:4:4; per-output scaling (see §6.6 for full list)                                                                      |
| Color                 | RGB, YCbCr 4:4:4/4:2:2, YUV 4:2:0; 8/10/12-bit                                                                                             |
| Audio                 | Audio over HDMI (no HDCP encoding)                                                                                                         |
| HDCP                  | Content is not HDCP-encoded (medical sources)                                                                                              |
| Control               | Web UI (Matrix Control UI) over TCP/IP; front-panel keys (lockable); TCP/IP API for integrators                                            |
| Network               | RJ45 Ethernet 100/1000 Mb/s; DHCP or static; default IP 192.168.0.100                                                                      |
| ESD protection        | IEC 61000-4-2: ±8 kV air, ±4 kV contact                                                                                                    |
| Power                 | DC 12 V 3 A; external medical-grade (IEC 60601-1) AC/DC supply, 100–240 V 50/60 Hz; <25 W typical; SELV                                    |
| Cooling / noise       | Passive, fanless — 0 dB; housing gets warm (normal)                                                                                        |
| Mechanical            | 270 × 30 × 166 mm (W×H×D), 1.25 kg; steel housing, aluminum front, white RAL9016                                                           |
| Ingress protection    | IP20 (protected against solid objects > 12.5 mm; no protection against water)                                                             |
| Operating environment | 0…+40 °C, 700–1060 hPa, 20–80 % RH non-condensing                                                                                          |
| Storage/transport     | −20…+60 °C, 540–1060 hPa, 10–90 % RH non-condensing                                                                                        |
| Boot time             | <15 s (max 20 s); restores last routing after boot                                                                                         |
| Box contents          | MVX441, medical power supply 12 V 3 A + power cable, RJ45 cat 7 patch cable, HDMI cable, 2 mounting ears + 8 screws, printed IFU (English) |

**Compliance:** Class I medical device (EU MDR 2017/745, UK MDR 2002, FDA Class 1);
EN/IEC 60601-1 (safety), EN 60601-1-2 (EMC), EN IEC 63000 (RoHS), FCC Part 15 B Class B,
ICES-003, WEEE. CE and UKCA marked. No applied parts; continuous operation; not sterile;
not protected against explosion (do not use in flammable anesthetic atmospheres).

---

## 10. Safety, cleaning, maintenance

- **No user-serviceable parts.** No exchangeable fuse. Repairs only at MediCapture
  service centers. Unauthorized modification voids warranty and regulatory approvals.
- Indoor use only; keep away from rain/moisture and liquids; do not block ventilation;
  use hospital-grade grounded power cord; surge protection recommended.
- **Live surgical monitor:** connect the video source directly to the main monitor as a
  fail-safe backup path (see §4).
- Equipment connected to the inputs/outputs must comply with UL/EN 60601-1 in the patient
  environment; whoever connects equipment configures a medical system and is responsible
  for IEC 60601-1-1 compliance. Patients are not intended operators; never touch the
  device and the patient at the same time.
- **Cleaning/disinfection:** no special maintenance, calibration, or consumables. Clean
  with a dry cloth to remove debris, then disinfect with EPA/FDA-approved surface
  disinfectant — recommended: 70 % ethyl alcohol (e.g. ~5 ml on a sterile swab, or BD
  Alcohol Swabs). Avoid electrical connectors; no liquids inside; no scouring agents or
  solvents.
- After a strong electrical disturbance (lightning, strong ESD) the output may flicker,
  change color or go black — power-cycle the device.
- Any serious incident related to the product must be reported to the manufacturer and
  the competent national authority.
- **Data protection:** the device does not store or process personal data / PHI (GDPR /
  HIPAA not applicable). Firmware updates transmit data to the device only.

---

## 11. Troubleshooting quick reference

| Symptom                                          | Check / action                                                                                                                                                                                                                                                                                                                                           |
| ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Can't reach the Matrix Control UI                | Press Key 1 for the IP address on the displays; confirm control device is on the same subnet; default IP 192.168.0.100; enter the IP in Advanced Settings → Network Connection → Connect; toggle DHCP/static with Key 2 long-press + reboot.                                                                                                            |
| UI shows "Device Standby"                        | The matrix is in standby — short-press the POWER button (LED turns green).                                                                                                                                                                                                                                                                               |
| "Activation Required" on MTR/MSP                 | The matrix-control feature needs activation key **AKMVX441**.                                                                                                                                                                                                                                                                                            |
| Settings ask for a password                      | The administrator set the settings password (see §6.1). Ask the administrator to unlock. Forgotten password → "Forgot password?" resets the system (erases all settings, presets, password).                                                                                                                                                             |
| Front panel keys do nothing                      | Front Panel Lock is on — Advanced Settings → Front Panel Control → Off.                                                                                                                                                                                                                                                                                  |
| No picture on an output                          | Check the source/destination status dots and the bar under the destination (orange = inactive source routed); verify the output is Enabled and its Resolution/Chrominance suit the display (try "Auto"); check cables (connect only with power off). In Bypass a monitor stays black if it cannot handle the source format (e.g. 4K source on HD-only monitor) — switch to Seamless for automatic conversion. |
| Source not recognised (orange status)            | Check the source is on and cabled; try the other EDID setting in Source Settings (e.g. 1080P for an older source).                                                                                                                                                                                                                                      |
| Output shows a test pattern                      | The Pattern button on that destination is active (Matrix mode) — tap it again to return to the previous source. Pattern style is set in Interface Settings.                                                                                                                                                                                               |
| Resolution / Chrominance greyed out              | Switching Mode is Bypass (output equals source), or Multiview is on and it is not Output 1 (set it on Output 1).                                                                                                                                                                                                                                         |
| Switching Mode greyed out                        | Multiview mode is active; Switching Mode applies to Matrix mode only.                                                                                                                                                                                                                                                                                    |
| Output 4 "copying is unavailable"                | Outputs 1–3 are all disabled — enable at least one in Destination Settings.                                                                                                                                                                                                                                                                              |
| Cannot save a new preset                         | All 4 preset slots are used — overwrite or delete an existing preset.                                                                                                                                                                                                                                                                                    |
| Routing change ignored right after a mode switch | Wait a few seconds after switching Matrix ↔ Multiview, then repeat the route.                                                                                                                                                                                                                                                                            |
| Picture flickers/black after lightning or ESD    | Power off, wait a few seconds, power on.                                                                                                                                                                                                                                                                                                                 |
| Network mode changed but nothing happened        | DHCP/static change via Key 2 requires a full power off/on reboot.                                                                                                                                                                                                                                                                                        |
| Device is very warm                              | Normal — passive fanless cooling. Ensure airflow, do not stack devices.                                                                                                                                                                                                                                                                                  |
| Reboot from the UI                               | Advanced Settings → System → Reboot Matrix; outputs and connection drop for ~15–20 s.                                                                                                                                                                                                                                                                    |

**Support contacts:** medicapture.com, phone 888-922-7887 (toll-free in the USA) or
+1-503-445-6935 (outside the USA); MediCapture Smart AI Assistant at
https://smartai.medicapture.com/. IFU translations (PDF): www.medicapture.com/support.

---

## 12. Video processing latency

Latency depends on the operating mode and output. The figures below describe **latency
added by the MVX441**, rather than the total delay from camera to display.

### 12.1 Latency by mode and output

| Operating mode    | Video output(s)                      | MVX441 processing latency                                                                       |
| ----------------- | ------------------------------------ | ----------------------------------------------------------------------------------------------- |
| Matrix / Bypass   | All outputs                          | Zero added latency                                                                              |
| Matrix / Seamless | All outputs                          | Under 2 video frames; under 30 ms at 60 fps                                                     |
| Multiview         | Output 1 — processed composite       | Under 2 video frames                                                                            |
| Multiview         | Outputs 2 and 3 — Bypass             | Zero added latency                                                                              |
| Multiview         | Output 4 — copy of output 1, 2, or 3 | Follows the selected output: processed when copying output 1; Bypass when copying output 2 or 3 |

### 12.2 Which screens need low latency?

Latency is typically most important on the **main surgical screen**, rather than every
screen in the room. In endoscopy and other minimally invasive procedures, the surgeon
uses the live screen image to guide movements, so the surgical viewing path should use
a Bypass output. Any secondary screen used for the same purpose should also use a
Bypass path.

In microscope-based procedures, including neurosurgery **when the surgeon looks directly
through the optics**, video display latency is generally less important because the
screen is not the surgeon's primary view. The deciding factor is how the screen is used,
rather than the specialty alone.

### 12.3 Example: Multiview setup for endoscopy

Multiview mode combines a room overview with Bypass paths for surgical viewing. A
recommended input assignment is:

| Input | Source                                       |
| ----- | -------------------------------------------- |
| 1     | Extra camera                                 |
| 2     | Extra camera                                 |
| 3     | Surgical camera                              |
| 4     | Review/playback — video output of a recorder |

Configure the outputs as follows:

| Output | Configuration                          | Destination and purpose                                                                                                                |
| ------ | -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| 1      | Quad Multiview showing all four inputs | Large wall screen for room overview; the processing delay does not affect surgical guidance when this screen is used only for overview |
| 2      | Bypass; select the required source     | Spare or extra screen with zero added latency                                                                                          |
| 3      | Bypass; route input 3                  | Main surgical screen with zero added latency                                                                                           |
| 4      | Copy of output 3                       | Secondary surgical screen and/or an HDMI split to a recorder                                                                           |

This arrangement keeps the main and secondary surgical viewing paths in Bypass while
the wall screen shows the Multiview composite. Camera, display, and any additional
equipment in a viewing path can contribute their own latency.

---

<!-- VMS section: standalone, maintained separately from the product sections above. -->

## 13. Video Management Solutions (VMS)

**Video Management Solutions (VMS)** are MediCapture bundles that pair the **MVX441 4×4
matrix** with a MediCapture touchscreen device running the Matrix Control UI. Together they
form one ready-to-use system to **route, capture and share** medical video through a
single, unified user interface — no separate control system or custom UI development
needed. Typical users are small and medium-sized practices and ORs.

Available options:

| Option              | Bundle                                                         | What it does                                                                                                                                                              |
| ------------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **MTR + MVX441**    | MTR Touchscreen Recorder (MTR133 / MTR156 / MTR245) + MVX441   | Video routing **and** recording, archiving, annotation and sharing from one touchscreen. DICOM/HL7: patient worklist and storage of recordings to PACS. On the MTR245, **Dual-View** operation shows routing and recording side by side. |
| **MSP + MVX441**    | MSP Smart Control Panel (MSP156 / MSP245) + MVX441             | Touchscreen control of video routing, Multiview and presets, without a recorder.                                                                                          |

Common features: medical grade, only two devices, compact size, 4×4 seamless switching,
Multiview layouts and presets (see §2, §5). Matrix control on the MTR/MSP requires
activation key **AKMVX441** (§7); when sold as a VMS bundle, AKMVX441 is included and
the MTR/MSP ships pre-activated.

On the website the bundles are offered as **Video Management Solution Pro** and
**Video Management Solution Lite**. Datasheets can be requested at
https://medicapture.com/vms/. Availability: medical certifications are complete, and
VMS is available now (announced September 23, 2026).

---
