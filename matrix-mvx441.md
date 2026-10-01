# MVX441 Video Matrix — Product Knowledge Base

> Audience: AI assistant for product support. Covers what the MVX441 is, how to install,
> operate and configure it, its operating modes, the Matrix Control UI and its settings,
> and how it fits into a MediCapture OR integration. Control-protocol (API) details are
> intentionally excluded; API command documentation is available from MediCapture upon
> request for system integrators.

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
  FDA Class 1). IEC 60601-1 safety, fanless (silent, passive cooling), IP21, equipotential
  bonding pole, medical-grade external power supply.
- Compact: 270 × 166 × 30 mm, 1.25 kg, white steel housing (RAL9016) with aluminum front.

**Intended use:** interconnection of medical Class 1 imaging devices with HDMI video
output or HDMI video input. Not for diagnosis; not for measuring clinical parameters; no
applied parts (no patient contact). Users: qualified healthcare professionals in
professional healthcare indoor environments. Applies to firmware V1.10.02 / V1.00.02 and
higher.

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
- **Bypass** — the signal passes through unscaled, with zero added latency. Side effects:
  the monitor may show black for a few seconds while re-syncing when the source changes,
  and the monitor stays black if it does not support the source's signal format (e.g. a
  4K source on an HD-only monitor).

### 2.2 Multiview mode

**Output 1** becomes a composite screen combining multiple sources in a selectable layout
("Scene"). While Multiview is active:

- **Output 1** — the Multiview composite.
- **Outputs 2 and 3** — switch to Bypass mode (unscaled, independent single-source
  outputs).
- **Output 4** — can be configured as a **copy** of output 1, 2, or 3 ("Copy From") —
  useful, for example, to record exactly what a display shows.

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
per tile.

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
| **Key 4**              | Long press (beep): factory reset.                                                                                                                                                                                         |

Each key has a green activation LED. Boot takes under 15 seconds; the power LED indicates
the boot sequence. The device is intended to remain powered continuously so it can react
to control commands at any time. After booting it restores the last used routing
configuration.

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
8. In the Matrix Control UI, enter the matrix IP address (Settings → Advanced) to connect.
9. Review the Settings sections before first clinical use.

Static-IP tip: if the matrix stays at 192.168.0.100, put the control device on the same
segment (e.g. 192.168.0.12, mask 255.255.255.0).

---

## 5. Matrix Control UI — daily operation (operator level)

The Matrix Control UI is designed for touchscreen use with large icon tiles. The **home
page** is where the OR operator (e.g. a nurse) works — no password required:

- **Routing:** tap a **Source** tile, then tap the **Destination** tile that should show
  it. Done — switching is immediate.
- **Signal indicators:** each source shows live signal-present / no-signal status.
- **Presets:** save and recall complete routing/layout configurations by name. Typical
  use: one named preset per surgeon/operator or per procedure type. Presets are stored on
  and synced with the device, so any control panel connected to the matrix sees them.
  Presets can be deleted (with confirmation).
- **Multiview scene selection** (when Multiview mode is enabled): SCENE button on
  output 1, layout selection, and per-tile source assignment (see §2.2).
- **On-screen utilities:** count-down **Timer**, count-up **Stopwatch**, and a live
  **Clock**; each can be shown/hidden and the Timer/Stopwatch can be renamed (labels set
  in Interface Settings).

Names and icons: each source/destination tile carries a custom **label** and a **clinical
icon** chosen from a built-in library — C-Arm, Camera, Computer, Endoscope, HDMI,
Microscope, PTZ Camera, SDI, Surgical Light, Surgical Robot, Ultrasound, Vital Signs,
X-Ray, Archive, Recorder, Media Player, Online Conference, and numbered icons 1–4. The
icon assigned to a source also appears on any destination currently showing that source.

---

## 6. Settings (administrator level)

Settings open from the home page into five sections. Four of them can be
**password-protected**; System Info is always accessible.

### 6.1 Password protection model — operator vs. administrator

The settings password is a **usage separation, not a security secret**:

- Its purpose is to protect settings from **accidental or unauthorized change** — an
  operator (nurse) can freely switch video, use presets and timers on the home page, but
  cannot (even accidentally) rename channels, change the operating mode, alter the IP
  address, etc.
- **Protected sections:** Advanced Settings, Interface Settings, Source Settings,
  Destination Settings. **Not protected:** the home/routing page and System Info.
- The password is set, updated, or cleared in **Advanced Settings → Password**
  (Set / Update / Clear Password). With no password set, all settings are open.
- Once unlocked, settings stay unlocked for the session; after **10 minutes of
  inactivity** they lock again automatically.
- **Forgot password:** there is no master password, and MediCapture has no access to it.
  Recovery = full **system reset to factory defaults** (offered via "Forgot Password"),
  which permanently erases all settings, presets, and the password.

### 6.2 System Info (always accessible)

Read-only device information: Model, Firmware Version, MAC Address, IP Address, Web UI
version, Operating Mode, DHCP status, Power state, Hostname, Subnet, Gateway, TCP/Telnet
status. The same basic info is available on the connected displays by pressing front-panel
Key 1.

### 6.3 Advanced Settings

- **Network:** IP Mode (Static / DHCP), IP Address (with Set button), Gateway, Subnet.
- **Password:** set / update / clear the settings password (see §6.1).
- **System:** **Reboot Matrix** button — the matrix restarts; video outputs and the
  connection drop for about 15–20 seconds.

### 6.4 Interface Settings

- **Interface Title** — rename the UI header (e.g. "OR 3").
- **Mode Selection** — Multiview / Matrix (see §2; tooltip explains the output roles in
  Multiview).
- **Language** — English, Traditional Chinese, German, French, Spanish, Russian (more
  planned).
- **Switching Mode** — Seamless (auto conversion, no black blink, under 2 frames latency) /
  Bypass (unscaled, zero latency, brief black on switch; see §2.1 for details).
- **Theme** — Dark Mode / Light Mode.
- **Pattern Style** — test/idle pattern for outputs with no source: Black, Blue,
  Color Bar, Gray, Cross, Cross Hatch.
- **Font Size** — Tiny / Small / Normal / Large.
- **PiP Size** — Small / Medium / Large (inset size in PiP scenes).
- **Date Format / Time Format** — for the on-screen clock.
- **Display Status** — toggle visibility of the Presets, Timer, Stopwatch, and Clock
  panels on the home page; Timer and Stopwatch titles can be customized.

### 6.5 Source Settings (video inputs)

Per input 1–4:

- **Label** — name the connected device (e.g. "Endoscope", "C-Arm").
- **Icon** — pick from the clinical icon library (§5).
- **Enable / Disable** the source.
- **EDID** — advertised capability to the source: "4K2K60 444, audio 2-ch" or
  "1080P, audio 2-ch".

### 6.6 Destination Settings (video outputs)

Per output 1–4:

- **Label** — name the connected display/recorder.
- **Resolution** — output scaling target; choose a resolution the connected display
  accepts. Full list: 4096×2160 p60/p50/p30/p25/p24, 3840×2160 p60/p50/p30/p25/p24,
  1920×1080 p60/p50/p30/p25/p24, 1920×1080 i60/i50, 1920×1200p60RB, 1360×768p60,
  1280×800p60, 1280×720 p60/p50, 1024×768p60, and **auto**.
- **Enable / Disable** the output.
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
| Control               | Web UI (Matrix Control UI) over TCP/IP; limited front-panel keys; TCP/IP API for integrators                                               |
| Network               | RJ45 Ethernet 100/1000 Mb/s; DHCP or static; default IP 192.168.0.100                                                                      |
| ESD protection        | IEC 61000-4-2: ±8 kV air, ±4 kV contact                                                                                                    |
| Power                 | DC 12 V 3 A; external medical-grade (IEC 60601-1) AC/DC supply, 100–240 V 50/60 Hz; <25 W typical; SELV                                    |
| Cooling / noise       | Passive, fanless — 0 dB; housing gets warm (normal)                                                                                        |
| Mechanical            | 270 × 166 × 30 mm (W×D×H, without connectors), 1.25 kg; steel housing, aluminum front, white RAL9016                                       |
| Ingress protection    | IP21                                                                                                                                       |
| Operating environment | 0…+40 °C, 540–1060 hPa, 20–80 % RH non-condensing                                                                                          |
| Storage/transport     | −20…+60 °C, 700–1060 hPa, 10–90 % RH non-condensing                                                            |
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
- Equipment connected to the inputs/outputs must comply with UL/EN 60601-1 in the patient
  environment; whoever connects equipment configures a medical system and is responsible
  for IEC 60601-1-1 compliance. Patients are not intended operators; never touch the
  device and the patient at the same time.
- **Cleaning/disinfection:** no special maintenance, calibration, or consumables. Clean
  with a dry cloth to remove debris, then disinfect with EPA/FDA-approved surface
  disinfectant — recommended: 70 % ethyl alcohol (e.g. ~5 ml on a sterile swab, or BD
  Alcohol Swabs). Avoid electrical connectors; no liquids inside; no scouring agents or
  solvents.
- After a strong electrical disturbance (lightning, strong ESD) the output may flicker or
  go black — power-cycle the device.
- **Data protection:** the device does not store or process personal data / PHI (GDPR /
  HIPAA not applicable). Firmware updates transmit data to the device only.

---

## 11. Troubleshooting quick reference

| Symptom                                          | Check / action                                                                                                                                                                                                                                                                                                                                           |
| ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Can't reach the Matrix Control UI                | Press Key 1 for the IP address on the displays; confirm control device is on the same subnet; default IP 192.168.0.100; toggle DHCP/static with Key 2 long-press + reboot.                                                                                                                                                                               |
| "Activation Required" on MTR/MSP                 | The matrix-control feature needs activation key **AKMVX441**.                                                                                                                                                                                                                                                                                            |
| Settings ask for a password                      | The administrator set the settings password (see §6.1). Ask the administrator to unlock. Forgotten password → factory reset (erases all settings, presets, password).                                                                                                                                                                                    |
| No picture on an output                          | Check source signal indicator on the home page; verify the output is Enabled and its Resolution suits the display (try "auto"); check cables (connect only with power off). In Bypass switching mode a monitor stays black if it cannot handle the source format (e.g. 4K source on HD-only monitor) — switch to Seamless mode for automatic conversion. |
| Output shows a test pattern                      | No source routed / no signal — pattern style is configurable in Interface Settings.                                                                                                                                                                                                                                                                      |
| Routing change ignored right after a mode switch | Wait a few seconds after switching Matrix ↔ Multiview, then repeat the route.                                                                                                                                                                                                                                                                            |
| Picture flickers/black after lightning or ESD    | Power off, wait a few seconds, power on.                                                                                                                                                                                                                                                                                                                 |
| Network mode changed but nothing happened        | DHCP/static change via Key 2 requires a full power off/on reboot.                                                                                                                                                                                                                                                                                        |
| Device is very warm                              | Normal — passive fanless cooling. Ensure airflow, do not stack devices.                                                                                                                                                                                                                                                                                  |
| Reboot from the UI                               | Advanced Settings → Reboot Matrix; outputs and connection drop for ~15–20 s.                                                                                                                                                                                                                                                                             |

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
