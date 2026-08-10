# MVR Error Messages — Support Reference

A plain-English explanation of every user-visible error, warning, and failure message the recorder app can show. Use it to triage support tickets where the user only quotes the on-screen message.


## How errors reach the user


Most error dialogs come from two helpers in `app/src/main/kotlin/com/medicapture/fragment/CoreBaseFragment.kt`:


- `showErr(message)` — modal dialog titled **Error**, with a warning icon. The main way an error is surfaced.

- `dialogError(message)` — thin alias around `showErr`.

- `showWarning(...)` / `showWarningCompose(...)` — non-critical warnings (yellow, dismissable).

- `showToast(...)` — brief on-screen toast (transient, often informational, sometimes used for soft errors).


When the user says "I got an error" but can't quote the text, ask whether it was a **dialog they had to dismiss** (showErr / dialogError) or a **toast that disappeared** (showToast). That alone narrows down the source.


Where a message includes a value that the device fills in at runtime (a filename, a count, a modality code, etc.), the heading below shows a realistic *example* in italics — the customer will see a real value in that spot, not the literal text shown here.


---


## Authentication & Login


### "Invalid user name or password"

- **Resource id:** `invalid_user_pass`

- **What it means:** Login was rejected — either against the local user database or against the configured LDAP server.

- **Common causes:** Typo; Caps Lock; user account disabled on LDAP; user not yet added to the device's local user list; password expired and rejected by LDAP.

- **How to fix / prevent:** Verify exact credentials with the customer's IT. For LDAP, confirm the device is on the network and the LDAP server settings are correct. If local, an admin must add or re-enable the account in Settings.


### "Invalid password!"

- **Resource id:** `invalid_password`

- **What it means:** The password failed validation — typically when changing or confirming a password, not at login.

- **Common causes:** New and confirmation passwords don't match; password doesn't meet policy (length/complexity).

- **How to fix / prevent:** Re-enter the password carefully. Check the password policy if one is enforced.


### "You should change your password."

- **Resource id:** `you_should_change_password`

- **What it means:** The user's password age has exceeded the configured renewal interval. The app prompts a password change before allowing further work.

- **Common causes:** Routine expiration based on policy.

- **How to fix / prevent:** User clicks **Change now** and sets a new password. Admin can adjust the renewal interval in Settings if it's too aggressive.


### "Invalid key"

- **Resource id:** `invalid_key`

- **What it means:** A feature-activation / license key was rejected.

- **Common causes:** Key mistyped; key generated for a different device serial; key is for a different product/feature; key has been revoked.

- **How to fix / prevent:** Verify the key matches the device serial exactly. Re-issue a fresh key from licensing.


### "User with this name already exists"

- **Resource id:** `user_already_exists`

- **What it means:** Admin tried to create a local user account with a name that's already in the user database.

- **How to fix / prevent:** Choose a different user name, or edit the existing account instead.


---


## USB & Storage


### "No USB storage is connected."

- **Resource id:** `err_no_usb_storage`

- **What it means:** The app tried to do something that needs a USB stick (copy, export, header image pick, firmware update) but no recognized USB mass-storage device is present.

- **Common causes:** Stick not inserted; stick inserted but not mounted yet (give it 2–3 s); stick formatted with an unsupported filesystem (the device expects FAT32 / exFAT); USB port damaged; "USB Storage is Disabled" in Settings.

- **How to fix / prevent:** Insert a working FAT32/exFAT-formatted stick. Wait until the storage indicator confirms it's mounted. Check Settings → USB Storage is enabled. Try a different USB port.


### "USB Storage is Disabled"

- **Resource id:** `usb_is_disabled`

- **What it means:** USB mass-storage access has been turned off in Settings, so the user can't read from or write to USB sticks even if one is inserted.

- **How to fix / prevent:** Admin enables USB storage in Settings (typically locked behind admin login on hardened deployments).


### "No internal storage is present."

- **Resource id:** `err_no_internal_storage`

- **What it means:** The internal storage partition where recordings normally go is unavailable. This is rare and indicates a hardware or mount problem.

- **Common causes:** Internal storage disabled in Settings; partition failed to mount on boot; underlying eMMC failure.

- **How to fix / prevent:** Reboot the device. If the problem repeats, check Settings and pull logs — this can be a sign of failing flash storage.


### "Not enough free space for *STUDY-1234*."

- **Resource id:** `not_enough_free_space`

- **What it means:** The target storage doesn't have room for the file or study named in the message (e.g. `STUDY-1234`, `video_005.mp4`). Generic variant — the storage name is not specified.

- **Common causes:** Storage near full; very large video file; many leftover unexported studies.

- **How to fix / prevent:** Delete or export old studies; empty the recycle bin; use a larger USB stick.


### "Not enough free space for *STUDY-1234* on *USB* storage."

- **Resource id:** `not_enough_free_space_on_storage`

- **What it means:** Same as above, but the target storage is named explicitly. The first slot is the file/study, the second is the storage name (`USB`, `internal`, `NAS`).

- **How to fix / prevent:** Free space on the named target, or pick a different destination.


### "Storage is not available: *USB*"

- **Resource id:** `storage_is_not_available_`

- **What it means:** A specific storage volume (the slot is filled with `USB`, `internal`, or `NAS`) that the operation needs has gone offline mid-operation.

- **Common causes:** USB unplugged during copy; NAS share unreachable (network drop, credentials expired); volume failed to remount after sleep.

- **How to fix / prevent:** Reconnect the storage. For NAS, verify network and credentials in Settings.


### "No target storage is available."

- **Resource id:** `err_no_available_destination`

- **What it means:** Export/copy/save needs *some* destination and none is configured or reachable.

- **Common causes:** No USB inserted, NAS unreachable, PACS unreachable — *all* possible destinations are unusable simultaneously.

- **How to fix / prevent:** Make at least one destination available (insert USB, fix network, etc.).


---


## File Operations (Copy, Delete, Export)


### "Copying failed"

- **Resource id:** `failed_to_copy`

- **What it means:** A file copy operation aborted with an error. The destination file may be partial or missing.

- **Common causes:** Source file disappeared (USB unplugged); destination ran out of space mid-copy; destination filesystem doesn't accept the filename (e.g. characters not legal on FAT32); permission denied on NAS.

- **How to fix / prevent:** Re-insert media if it was unplugged. Confirm there's enough free space *before* starting. Retry; if it fails again, pull logs.


### "Some files could not be deleted"

- **Resource id:** `delete_failed`

- **What it means:** Bulk delete completed but at least one file couldn't be removed.

- **Common causes:** File is currently being written/read (e.g. a recording in progress); permission denied; file system error.

- **How to fix / prevent:** Wait for any active recording/export to finish, then retry. Check that the file is not on read-only media.


### "Failed files: *5*"

- **Resource id:** `failed_files_`

- **What it means:** Summary line shown after a batch operation. The slot is a count (e.g. `5`) of files that did not succeed. Appears alongside other status (e.g. PACS upload).

- **How to fix / prevent:** Open the per-file error list (if available in the screen) to see which files failed and why; retry those specifically.


### "No image was found"

- **Resource id:** `err_no_header_image_on_usb`

- **What it means:** Settings → Report Header → pick image was used, but no JPG/PNG was found at the root of the USB stick.

- **How to fix / prevent:** Put the header image as a JPG or PNG **at the root** of the USB stick (not inside a sub-folder). Recommended size is around 2048×256 px, roughly 8:1 or 10:1 aspect.


### "No APK file found"

- **Resource id:** `err_no_apk_found`

- **What it means:** External-app install attempted, but no `.apk` file was present on USB.

- **How to fix / prevent:** Place the APK at the root of the USB stick and try again.


### "No files were found"

- **Resource id:** `no_files`

- **What it means:** The selected folder/source has no files matching the current filter.

- **How to fix / prevent:** Adjust the filter, pick a different folder, or check that the source isn't empty.


### "Ignored files: *TXT, ZIP*"

- **Resource id:** `ignored_files_`

- **What it means:** A copy/send/import action skipped files with unsupported extensions. The slot lists the ignored file types.

- **How to fix / prevent:** Use files supported by the current action, or convert/remove unsupported files before retrying.


### "Permission request" / "Write permission is needed for copying files to device storage."

- **Resource ids:** `permission_request`, `permission_request_msg`

- **What it means:** Android storage permission is required before the app can copy files into device storage.

- **How to fix / prevent:** Grant the permission prompt. If it was denied permanently, reset app permissions in Android settings or reinstall/update according to service procedure.


---


## Recording & Camera


### "Camera signal lost"

- **Resource id:** `signal_lost`

- **What it means:** A previously-working video input (HDMI / SDI / USB camera) has dropped its signal. Shown on the affected camera tile.

- **Common causes:** Cable unplugged or loose; source device powered off; resolution/refresh changed beyond what the input can lock to; bad cable; for HDMI: HDCP handshake failed; for LT6911 HDMI bridge cams, kernel driver got stuck (a known issue — see git log).

- **How to fix / prevent:** Re-seat the cable. Verify the source is on and outputting a supported resolution. If it persists after reseating, switching the source's resolution can re-trigger the lock. Pair "Signal recovered" later in the log confirms recovery.


### "Video playback error"

- **Resource id:** `video_playback_error`

- **What it means:** The Review screen tried to play a video and the player gave up.

- **Common causes:** File corrupted (recording was cut off by power loss); codec mismatch (rare — should not happen for files this device wrote itself); file partially deleted.

- **How to fix / prevent:** Try another video to confirm playback works in general. If the failing file matters, attempt the "Fixing file…" recovery (the app does this automatically on next open) or pull the file off-device for inspection.


### "Video is too big: *5.6 GB*. Maximal size is *4.0 GB*."

- **Resource id:** `video_too_big`

- **What it means:** The user tried to send/export/copy a video whose size exceeds a limit imposed by the target (typically PACS or a download endpoint).

- **How to fix / prevent:** Trim the video using the edit screen, or split it into segments, before sending. Raise the limit on the receiving system if appropriate.


### "No segments are defined"

- **Resource id:** `video_edit_no_segments`

- **What it means:** Trim/edit was confirmed but the user hadn't defined any IN/OUT segment yet.

- **How to fix / prevent:** Set at least one segment (mark IN and OUT points) before saving the edit.


---


## Printing


### "Network need to be connected to use printers"

- **Resource id:** `printers_warn_no_network`

- **What it means:** The printer subsystem discovers printers over the local network — and the device currently has no network link.

- **How to fix / prevent:** Connect Ethernet or join Wi-Fi, then re-open the printer screen. USB-tethered printers are not supported by this flow.


### "Printer must be selected before Auto print can be used"

- **Resource id:** `warn_no_printer_selected`

- **What it means:** The "Auto print" toggle was turned on but no default printer is configured, so the device wouldn't know where to send the print.

- **How to fix / prevent:** Open Settings → Printer, pick a default printer, then re-enable Auto print.


### "Auto reporting: Nothing to print"

- **Source:** `AutoReportFragment.kt` / `AutoReportActivity.kt`

- **What it means:** Auto-report generation ran, but the selected study/report mode produced no printable pages.

- **Common causes:** Study has no images; report mode is "Only images" and there are no still images; all selected content was deleted or filtered out.

- **How to fix / prevent:** Confirm the study contains printable images, or change report mode/settings.


---


## Network / PACS / DICOM


### "Net storage init failure: failed to connect to */10.65.102.125 (port 445)* ..."

- **Source:** hardcoded in `MvrApp.kt` (`manageNetworkStorage`)

- **What it means:** The app tried to initialize Network Storage (SMB/Samba/NAS share) and could not open the SMB connection. The example screenshot shows a connection attempt to TCP port **445**, which is the standard SMB file-sharing port.

- **Common causes:** Device is not on the same LAN as the NAS; wrong server IP/host; server is powered off; firewall blocks TCP 445; VLAN/routing issue; Wi-Fi/Ethernet dropped; NAS SMB service is disabled; timeout while reaching the server.

- **How to fix / prevent:** Confirm the recorder has a network link, then ping/reach the NAS IP from another machine on the same network. Verify Settings -> Connections -> Network storage server: host/IP, folder path, domain/workgroup, username, and password. On the NAS/firewall, allow SMB on TCP 445. Retry the Network storage test after changes.

- **Technical suffix guide:** `EHOSTUNREACH` means "no route to host" / the IP cannot be reached from the recorder. `failed to connect ... after 10000000ms` means the SMB connect timed out. `port 445` points specifically to SMB, not PACS/DICOM.


### "Network storage: *failed to connect to ...*" / "Network storage: setup successful"

- **Source:** Network storage setup/test button in web/settings UI

- **What it means:** Result of testing the configured SMB/NAS share. The success form confirms the app could authenticate and access the configured folder. The error form prefixes the underlying Samba/Java error with `Network storage:`.

- **Common causes:** Same as "Net storage init failure"; additionally, bad credentials, wrong domain/workgroup, wrong share/folder name, or a path beginning with `/`.

- **How to fix / prevent:** Fix the Network storage server settings and run the test again before enabling NAS export or Network Storage recording.


### "Network storage: host is not set"

- **Source:** `SambaStorageDevice.create`

- **What it means:** Network Storage is enabled/tested but no SMB server host/IP is configured.

- **How to fix / prevent:** Enter the NAS server IP address or DNS name.


### "Network storage: folder name is not set" / "Network storage: folder name can't start with '/'"

- **Source:** `SambaStorageDevice.create`

- **What it means:** The SMB folder/share path is missing or formatted incorrectly. The app expects a relative share/path, not a Unix-style absolute path.

- **How to fix / prevent:** Enter the share/folder path without a leading slash. Example: `MVR` or `MVR/Room1`, not `/MVR`.


### "Network storage: user is not set" / "Network storage: user password is not set"

- **Source:** `SambaStorageDevice.create`, when Personal mode is enabled

- **What it means:** Network Storage is using the logged-in user's credentials, but no eligible user/password is available.

- **Common causes:** No user is logged in; user account has no password; emergency/synthetic user is active; Personal mode is enabled by mistake.

- **How to fix / prevent:** Log in with a real user that has a password, set that user's password, or disable Personal mode and configure fixed NAS credentials.


### "Device is not connected to LAN"

- **Resource id:** `device_not_on_lan`

- **What it means:** A LAN-only feature was started while the recorder has no usable LAN connection. Seen during network server discovery and remote-login discovery flows.

- **How to fix / prevent:** Connect Ethernet or Wi-Fi/USB tethering as appropriate, then retry discovery.


### "No results"

- **Resource id:** `no_results`

- **What it means:** LAN scan/search completed but found no matching recorder/NAS/server.

- **How to fix / prevent:** Confirm both devices are on the same subnet/VLAN and that discovery traffic is not blocked. Enter the IP address manually if discovery is unavailable on the customer network.


### "Connection is lost"

- **Resource id:** `connection_lost`

- **What it means:** A previously-working network connection (typically to PACS, NAS, worklist, or LDAP) dropped during an operation.

- **Common causes:** Cable unplugged; Wi-Fi roamed/dropped; remote server restarted; firewall closed the session due to inactivity.

- **How to fix / prevent:** Verify Ethernet/Wi-Fi link; ping the remote server from another machine; retry. If recurrent, inspect firewall idle-timeout settings.


### "No connection"

- **Resource id:** `no_connection`

- **What it means:** Displayed as a status when no network is up at all (not just a server reachability issue).

- **How to fix / prevent:** Check cable, switch port, Wi-Fi credentials.


### "LDAP: *Can't connect to server*"

- **Source:** hardcoded prefix in `LoginFragment.kt`

- **What it means:** LDAP authentication failed with a technical reason. The app prefixes the underlying exception with `LDAP:`.

- **Common causes:** LDAP server unreachable; wrong LDAP host/port; SSL mismatch; bind/search settings wrong; user not in any configured role group.

- **How to fix / prevent:** Test the LDAP settings from Settings -> Security/LDAP. Confirm host, port, SSL, naming context, auth path, and group DNs with the customer's IT team.


### "PACS doesn't accept these files: *MP4*  /  Accepted file types: *JPEG, DICOM*"

- **Resource id:** `server_accepts_files_`

- **What it means:** Send to PACS was attempted with files whose modality / SOP class the PACS is configured to reject. The first slot lists rejected types (e.g. `MP4`), the second lists what the PACS will accept (e.g. `JPEG, DICOM`). Displayed on two lines in the dialog.

- **Common causes:** PACS configured for still images only but the study has video; new DICOM SOP class not yet whitelisted on PACS.

- **How to fix / prevent:** Either send only the file types the PACS accepts (filter the selection) or ask the PACS admin to whitelist the additional SOP classes.


### "Server does not accept video. Video will be recorded but will not be sent to PACS."

- **Resource id:** `pacs_warn_no_video`

- **What it means:** Warning at study start. PACS is known not to accept video — recording proceeds locally but auto-send won't include the video.

- **How to fix / prevent:** Either accept this (video lives only on-device / on USB), or have the PACS admin enable video SOP classes.


### "Server does not support Worklist"

- **Resource id:** `server_no_worklist`

- **What it means:** The configured DICOM server returned no response or "not supported" to a Modality Worklist (C-FIND) query.

- **Common causes:** PACS doesn't have a worklist service; worklist is on a different AE/host than the configured one; AE Title not authorized for C-FIND.

- **How to fix / prevent:** Configure the worklist endpoint separately if the customer uses a dedicated worklist server. Verify AE Title is registered on the server.


### "Modality *XC* unsupported. Try *ES*"

- **Resource id:** `modality_x_unsupported_try_other`

- **What it means:** PACS rejected the DICOM modality code attached to the study (the first slot is the rejected code, e.g. `XC`) and the message suggests an alternative the PACS will accept (the second slot, e.g. `ES`).

- **How to fix / prevent:** Change the modality in Settings → DICOM to the suggested value, or have PACS configured to accept the original modality.


### "*PACS* upload errors"

- **Resource id:** `upload_errors_to_`

- **What it means:** Status line indicating files failed to upload to the named destination. The slot is the destination name (`PACS`, `NAS`, etc.). Shown as a status, not a dialog.

- **How to fix / prevent:** Open the destination's status screen for per-file details. Common root causes: PACS rejection, network drop, NAS auth failure.


### "NAS service: network storage not initialized"

- **Source:** `NasExportService.kt` audit/log message

- **What it means:** Export to NAS was started, but the Network Storage device was not ready. Usually follows a failed Network Storage initialization.

- **How to fix / prevent:** Resolve the Network Storage setup/connection error first, then retry NAS export.


---


## Firmware / Updates


### "No update files are found on the USB storage."

- **Resource id:** `err_no_update_files`

- **What it means:** Firmware update was started but the expected update files aren't on the inserted USB stick.

- **How to fix / prevent:** Put the update package (unzipped, at root) on the USB stick. Confirm the package is the one for this device model.


### "Update preparation failed"

- **Resource id:** `failed_to_prepare`

- **What it means:** Title line shown when firmware update couldn't be staged. The second line of the dialog is one of the more specific errors below (`err_copy_firmware_to_internal`, …). On its own this line tells you the firmware-update stage failed; the next line tells you why.


### "Could not copy *"MVR460-260520.upd"* to Internal Storage.  /  *No internal storage is present.*"

- **Resource id:** `err_copy_firmware_to_internal`

- **What it means:** Body of the "Update preparation failed" dialog. The first slot is the firmware file **the user picked from USB** (their original filename, e.g. `MVR460-260520.upd`). The second slot is the reason — either "No internal storage is present." or a technical I/O reason (e.g. *"open failed: ENOSPC (No space left on device)"*).

- **Common causes:**

  - Internal storage not mounted (rare; hardware/mount issue).

  - Internal storage full — older recordings or a previously-staged `.upd` file haven't been cleared.

  - Internal storage read-only or filesystem error.

- **How to fix / prevent:**

  - Reboot the device and retry — covers transient mount failures.

  - Free space on internal storage (delete or export old studies), then retry.

  - If "No internal storage is present." persists across reboots, escalate — the eMMC may be failing. Pull logs.

- **Note for support:** The destination filename internally is a fixed `mvr435.upd` regardless of model. The dialog has been corrected to **never** show that name and to always show the source file the user selected. If a customer report still quotes "mvr435.upd", they are on an older build — get them upgraded.


### "No backup files were found"

- **Resource id:** `no_settings_backup_found`

- **What it means:** Settings restore was opened, but no settings-backup file was found on the USB storage.

- **How to fix / prevent:** Insert the USB stick that contains a previous settings backup, or create a backup first on the source device.


---


## Feature Conflict / Configuration Warnings


These appear as warnings when a setting depends on another setting and the dependency isn't met. The fix is always *"change the other setting first"*.


| Message | Resource id | What it means |
|---|---|---|
| Export can't be enabled: Internal storage is disabled | `warn_export_and_internal_storage` | Export requires internal storage to stage files. Enable Internal Storage first. |
| PACS export can't be enabled: Patient Info must be enabled | `warn_pacs_and_patient` | PACS export needs DICOM patient fields. Enable Patient Info first. |
| NAS export can't be enabled: Network storage is enabled | `warn_export_and_network_storage` | NAS export and Network Storage modes conflict — only one can be active. |
| Timelapse does not record audio | `warn_timelapse_with_audio` | Heads-up at recording: audio is dropped in timelapse mode by design. |
| This option must be enabled while Export to NAS is active. | `warn_nas_export_enabled` | A dependent NAS-export option requires the master toggle to be on. |
| Option "Stamp folder names" must be enabled first. | `warn_stamp_folders_enable` | The option being toggled depends on "Stamp folder names". |
| Parallel recording is disabled | `setting_warn_disable_parallel` | A higher-priority mode disabled Parallel — re-enable the conflicting mode first. |
| Picture in picture is disabled | `setting_warn_disable_pip` | A conflicting mode disabled PiP — disable that mode first. |
| Split view is disabled | `setting_warn_pr_disables_split` | Parallel recording disables Split view. |


---


## Generic / Catch-all


These appear when a more specific error wasn't available — they tell you very little on their own and the **logs are the only way to diagnose**.


### "Operation was not successful"

- **Resource id:** `operation_failed`

- **What it means:** A nonspecific failure. Almost always paired with a more specific Logcat error.

- **How to fix / prevent:** Pull logs (`adb logcat`), reproduce, look for an exception around the time of the dialog.


### "Failure"

- **Resource id:** `failure`

- **What it means:** Generic label. Same advice as above — needs logs.


### "Error" / "Error: *connection refused*"

- **Resource ids:** `error`, `error_`

- **What it means:** Title (and optional one-line body) of the standard error dialog. The slot in the second form is a short technical reason (e.g. `connection refused`, `timeout`). If shown with no body, the calling code passed an empty / generic message.


### Raw technical message only, e.g. "open failed: ENOSPC", "Camera not initialized", "Failed to parse JSON"

- **Source:** several `showErr(e.messageOrClassName)`, `dialogError(e.messageOrClassName)`, and `showToast(e.messageOrClassName)` paths

- **What it means:** The UI surfaced the underlying exception directly instead of wrapping it in a friendly resource string.

- **How to fix / prevent:** Match the technical words to the subsystem active at the time. `ENOSPC` means no space left; `permission denied` points to filesystem/NAS credentials; `failed to connect`, `timeout`, or `EHOSTUNREACH` point to network reachability; camera/codec/decoder messages point to the recording or playback pipeline.


### "Future feature, not available now"

- **Resource id:** `warn_future_version`

- **What it means:** The customer found a UI element that is stubbed for a planned feature. Not actually broken.

- **How to fix / prevent:** Reassure the customer — the option will activate in a future release.


---


## Hardcoded / non-localized messages


These are not in `strings.xml` and won't be translated. They are usually surfaced via `showErr` / `showToast` with literal text.


| Message | Location | Trigger |
|---|---|---|
| `Error: can't load external app` | `ExternalWebAppFragment.kt` | External web app (kiosk URL) failed to load — usually network or wrong URL in Settings → External Apps. |
| `Unsupported app type: WEB_KIOSK` | `App.kt` | Configuration references an external-app type the build doesn't know about (the slot is the unknown type name, e.g. `WEB_KIOSK`). Update the device or remove the offending entry. |
| `Failed to start session: camera busy` | `LiveFragment.kt` | A recording session couldn't be initialized — slot is a short reason (e.g. `camera busy`, `no encoder`). Typically the camera/encoder pipeline failed; pull logs, reboot often clears it. |
| `Cannot edit non-DICOM study info` | `CoreBaseFragment.kt` | User tried to edit patient data on a study created outside the DICOM flow. Expected — that study type doesn't carry the DICOM fields. |
| `Load error` | `ImageView.kt` (Review) | A still image failed to decode in the Review screen. File may be corrupted. |
| `File list error: I/O error` | `ArchiveFragment.kt` | Listing files in Archive failed — slot is a short reason (e.g. `I/O error`, `permission denied`). Usually a storage error (USB pulled, internal mount problem) — see Storage section above. |
| `Invalid IP: 10.65.102.x` | `RemoteLoginFragment.kt` | Remote app/device discovery was given an invalid IP address. Re-enter a numeric IPv4 address. |
| `Fingerprint failed` | `RemoteLoginFragment.kt` | Fingerprint authentication failed or was canceled by the biometric subsystem. Retry or use password login. |
| `RS232 err: ...` / `RS232 init: ...` | `RemoteLoginFragment.kt` | Remote app serial connection failed. Check selected USB/serial device, baud/permission, and cable. |
| `Preview error: ...` | `RemoteLiveSession.kt` | Remote live preview stream failed. Usually network interruption or decoder/stream startup failure. |
| `Power command failed` | `RemoteApp.kt` | Remote app asked the recorder to sleep/shutdown/reboot but the API returned an error. Retry locally or check API connection. |
| `LDAP: ...` | `LoginFragment.kt` | LDAP login failed with the underlying technical reason appended. See LDAP section above. |
| `Net storage init failure: ...` | `MvrApp.kt` | Network Storage/NAS initialization failed. See Network Storage section above. |
| `Network storage: ...` | `ApiRemoteWebAccess.kt`, `NetworkEditServerFragment.kt` | Network Storage setup/test result. See Network Storage section above. |
| `Operation was not successful\n...` | `ReportFragment.kt` | PDF/report generation failed and appended the technical reason. Often storage/permission/corrupt-image related. |
| `Can't save empty bitmap` | `PictureViewBaseFragment.kt` | Image annotation/save was attempted with no decoded bitmap. Usually file decode failed first. |
| `Can't cut this segment` | `VideoPlayFragment.kt` | Video trim/cut command cannot be applied to the selected segment. Check IN/OUT points and file validity. |
| `Nothing to do` | `ArchiveFragment.kt`, `ReviewFragment.kt` | User started a batch action with no applicable selected files. Select files first or change filter. |
| `Unknown user: NAME` | `StartScreenFragment.kt` | Badge/API/user shortcut referenced a user that does not exist in the local user list. |
| `User accounts disabled` | `StartScreenFragment.kt` | User-specific action was attempted while the user-account feature is turned off. |
| `Worklist search is enabled, but feature is not present: DICOM functions` | `StartScreenFragment.kt` | Worklist is configured but the DICOM feature/license is not active. Activate DICOM or disable Worklist search. |
| `Worklist search is enabled, but Worklist server setup is not valid` | `StartScreenFragment.kt` | Worklist search is enabled but server settings are incomplete/invalid. Fix Worklist server settings. |


---


## Suggested triage script for support


1. **Was it a dialog or a toast?** Dialog → `showErr/dialogError` call, message will appear in this file. Toast → `showToast`, may not be here yet.

2. **Quote the exact words.** Match against the section above. Note the `%s` placeholders if any — what value did the customer see?

3. **Decide layer:** USB / Network / PACS / Camera / License / Generic. Most fixes are at the device level (re-insert USB, reboot) or at the customer's IT level (PACS config, LDAP, network).

4. **If "Operation was not successful" or "Failure":** ask for logs. There is nothing in the message itself to act on.