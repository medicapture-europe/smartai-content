# ARCHIVING feature of MVR and MTR series devices

## Internal Storage / USB Storage / External Network Storage

### General storage rules & and advice for MVR and MTR series devices

- Internal Storage is the fastest and most reliable destination for recordings; however, it serves as a buffer or temporary Storage only.
- The internal storage needs to be activated for DICOM export and sending studies to PACS.
- Data should be copied from the Internal Storage to USB Storage, or Sent to PACS or NAS; there is an Internal Storage Backup feature to copy the entire Internal Storage to external USB drive.
- Internal Storage has auto-cleaning rules, user should setup rules and manage data, user is solely responsible of the data loss or leak.
- Size of the Internal Storage: MVR Pro (MVR409) & MVR (MVR420): 128 GB, upgradable up to 512 GB or 1 TB; 1 TB for MVR435 upgradable to 2 TB; None for MVR Lite (MVR400).
- USB storage is portable and an excellent way to save studies for presentations or for handing out data to the patient. It can also be used to copy or back up recordings from Internal Storage.
- USB flash sticks, SSDs, HDDs, or card readers can be connected as USB storage devices.
- MVR recorders support USB Storage formatted as exFAT, FAT32, or NTFS.
- Due to the large capacities of external USB hard drives, it may take approximately 20-60 seconds to recognize the device. Please be patient and wait until the external hard drive has been recognized. The external hard drive is recognized when the USB icon appears on the screen.

### Archive selection for MVR and MTR series devices

Storage locations can be selected for direct (real-time) recording of your studies:

- Internal Storage
- USB Storage
- Network Storage (NAS)
  The maximum video recording resolution can be specified separately for each Storage device; the choices are 2160p, 1080p, and 720p. To record for archiving purposes, select 720p, which will also reduce the recording framerate to 30 or 25 frames per second. Selecting "Only images" will turn off video recording for this Storage. MVR recorder offers the flexibility to select one or two Storages simultaneously. When two Storages are chosen, captured images are stored at both locations, and videos are recorded at both locations. For instance, you can select 'Only images' for the Internal Storage and 720p for the Network Storage. This setting ensures that images are stored in both Internal and Network Storages, while the video is recorded only to the Network Storage in the archive resolution. This setup is ideal for capturing images for further reporting and sending them to PACS, while keeping videos in the network archive for insurance or other purposes.

Note: The maximum video recording resolution limit may only reduce the resolution of the input video but will never increase it. For example, when 2160p is selected, and the video input is 1080p, the recording will be performed at the original input resolution, which is 1080p.

Note to model MVR Lite: Internal storage is unavailable for MVR400 (MVR Lite).

### Video Recording Notes for MVR and MTR series devices

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

### Folder names for MVR and MTR series devices

Folders are named chronologically after CASE numbers CASE0001, CASE0002, etc. If you want the folder to be named using Study date, time, and patient ID, enable the option "Stamp folder names." Since the MVR435 model, the folder name is always time-stamped and contains DeviceID; personal patient data in the folder name is optional and can be enabled in the Settings menu. It is recommended that patient data be avoided in folder names to reduce the possibility of personal data leakage.

## Internal Storage of MVR and MTR series devices: Rules for automatic cleaning

Rules for deleting the internal storage can be set to One of two options for automatic cleaning of the internal storage can be selected.

- Keeping around 20% of free space, but not more than 50 GB, ensures minimum storage space for the subsequent study.
- Keeping the last 7 days should be selected if the internal storage is only a safety backup. MVR435 model offers 28 days instead of 7. Cleaning rules are checked at the Start of the Study to ensure sufficient space for the new Study. Rules are not checked during the active Study. Keep both cleaning options unchecked (not selected) to keep all recordings and delete them manually.

## Disabling (locking) the USB storage for MVR and MTR series devices

USB storage can be completely disabled/locked if portable or removable media is prohibited in your clinical environment. If the USB memory has been deactivated here, it no longer appears in the archive settings for storage selection.

## Internal Storage Backup Feature Description for MVR and MTR series devices

- Internal Storage Backup feature is available in the Archive screen and it copies all Studies from MVR Internal Storage to external USB flash stick (or hard disk or SSD).
- Note: Internal Storage Backup feature does not backup device settings and Activation Keys; device settings backup is available on the "UPDATE / DEFAULT" screen of the Advanced settings.
- A button for the Internal Storage Backup is located at the bottom-left part of the screen, which is shown only when conditions for backup are satisfied: external USB Storage is present.
- Internal Storage Backup feature will check the available space on USB drive before start copy.
- Internal Storage Backup is incremental. It copies only new or changed files and skips previously copied files.
- It does not delete any other files on USB storage; only Study folders (CASExxxx) are created, and files are copied into folders.
- Users can repeatedly do backups on the same USB storage.
- Internal Storage Backup feature does not delete anything; delete data manually or format Internal Storage when backup is complete.
- When file error is encountered during the backup of the Internal Storage, a pop up dialogue will show the error description; tap to "Skip" button to continue Backup process; only corrupted files will be skipped, all good files will be copied from the Internal Storage to USB Storage.

## Creating a shared folder on your Network Server (NAS) to use as Network Storage for MVR and MTR recorder

- Create a shared folder per your NAS Server instructions.
- Ensure the MVR user has sufficient privileges to read and write to the shared folder.
- Take special care if this is a Wi-Fi user connecting via WPA2-Enterprise. They may need additional setup.
- Note the User Name, Password, and Shared Folder name (Example: User name: mm, Password: 123412341234, Shared Folder Name: Shared.) You will need this information to connect the MVR to the Network Server Shared Folder.

## Settings for Network Storage on MVR and MTR series devices

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

## Send to NAS Feature Description of MVR and MTR series devices

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

## Sharing the Internal Storage of MVR and MTR series device over network

This feature enables SAMBA server on MVR device and allows access to the Internal Storage from remote PC. Sharing the Internal Storage is not available for MVR400 (MVR Lite) and MVR435. From the Settings / Advanced/ Storage Rules screen: Tap on Share Internal Storage to enable it; enter password. Address to connect to the internal storage from remote PC will be displayed. Restart MVR device by power off/on after changes been made. From the remote PC point file explorer to the MVR access point, ex: "\\192.168.2.125\storage"; enter credentials: user name: "root" and password for Sharing Internal Storage. Internal Storage of MVR device will appear as folder in PC file explorer.

## How to delete recordings?

Recording can be deleted in the Review screen: select one or several recordings by tapping the right-top corner of the thumbnail and the Delete button. There is also a button to select or unselect ALL recordings. In the Archive screen, the Study folder can be deleted only when it is empty. This prevents the accidental deletion of many recordings at once. When it is necessary to delete a folder, delete all recordings first inside this folder, and then, after returning to the Archive screen, the Detele button will appear to delete the Study folder. There is no feature to delete all the recordings; however, in the Advanced Settings, available to the Administrator only, there is an option to format Internal Storage or USB Storage. The format will delete all the recordings within the selected storage. However, be careful not to lose the important recordings. Ensure all necessary recordings are properly archived—copied, backed up, sent to NAS, sent to PACS, or printed.
