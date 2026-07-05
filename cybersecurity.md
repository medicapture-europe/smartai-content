# Protection of the operating system of the MVR/MTR series of medical video recorders.

* Proprietary MVR/MTR operating system, based on Android with all unnecessary components removed.  
* ARM64 CPU architecture, which is not compatible with x86 PC architecture.  
* Closed system (no direct access to operating system):  
  * No possibility for either users or IT administrators to gain access to the operating system.  
  * There is no “IT administrator” login or system privilege on MVR devices.  
  * There is no possibility to install additional software and/or change or modify existing software modules which might introduce viruses or malware to the system or damage it.  
  * It is not possible to execute any files on an MVR device which might act as malware as the user and IT administrator have no access to the operating system or file manager.  
  * External storage devices, including USB storage, are mounted with no permission to execute any file. (This is a distinctive feature of the Linux OS which is not available in Windows OS)  
  * Application runs in the full-screen mode. There is no access to the generic OS desktop.  
  * No system hotkeys are accepted, all key events are processed by the application. No system-critical tools like Task Manager exist on the MVR OS, all removed.  
  * Application allows file manipulation only under the intended use, there is no generic file manipulation available. Application does not execute and does not allow to execute any files.  
* OS and application files are located on the internal, non-removable eMMC flash storage with the specific proprietary partitioning. System partitions are read-only and are protected from any alteration by the user or IT administrator. There are no means to change read/write permissions for the partitions under any privilege. OS and application always boot fresh in the “factory mode”, retaining only user settings of the application.  
* User files can be images or videos only. User files are always located on a storage device, different from the OS and applications files. No mixup of system and user files on the same storage device.  
* There is no BIOS on the MVR device. The OS bootloader is encrypted and signed with the proprietary key. Booting from the external device is not possible. Booting of the unauthorized unsigned firmware will be rejected.   
* Device firmware is a single file in the proprietary format, signed with the security key. Unauthorized unsigned firmware will be rejected during the proprietary update procedure. Device firmware includes OS and application and updates the whole device software features at once. No software component can be updated separately.  
* Remote access to the device is disabled by default.  
* MVR?MTR devices do not have default user or administrator or factory passwords. Once the remote access feature is enabled, a new password must be assigned. There is no procedure to recover lost passwords.  
* Once the User Accounts feature is enabled, administrator name and password should be assigned. Administrator privileges allow to operate Advanced Settings in the application menu, with no privilege to access OS partitions or files, alter file permissions, no administration rights for OS. Administrator has specific rights only within the application settings. Administrator has the regular “user” rights from the OS point of view.

---
# Appendix x. Cybersecurity

This appendix is intended for the IT network responsible at the organization where the MVR/MTR device is used. It contains technical information regarding the setup of the IT network and the devices connected to the MVR/MTR device. It also contains information regarding the types of data contained in and transmitted from the MVR/MTR device.

The MVR/MTR device is of medium security risk (according to NIST) as:

* The MVR/MTR device does not allow any input from external devices (except video signal devices and secured software updates).  
* Essential functionality is secured in case of network problems.

## Network setup

When preparing the network for connection to the MVR/MTR device, the following should be considered:

| Overview of the existing ports and their communication protocols |  |  |
| :---- | :---- | :---- |
| Item | Used standard | Comment |
| LAN communication | IEEE 802.3, IEEE 802.3ab, IEEE 802.3az, IEEE 802.3bz, PICMG3.1 | The device uses a standard 2.5 Gigabit Ethernet controller supporting a 2.5GBASE-T interface. |
| Access test  | ICMP/ping | Allowing ease-of-discovery for hospital IT infrastructure. |
| Network adaptor configuration | DHCP, Static IP  | Static IP address (IPv4) is configurable in the GUI. |
| Re-routing |  | The device does not support re-routing traffic between networks and cannot act as a NAT (Network Address Translation) gateway. |
| PACS servers  | DICOM | To support a broad range of network infrastructures and PACS servers, the device supports DICOM without CMS (Cryptographic Message Syntax) encryption for transporting photo(s), video(s), and report(s) to the PACS server. |
| Remote control API | TCP/IP, HTTP, HTTPS | Remote control API allows device discovery, and requires authentication for function control. Remote API does not allow any code execution and has no access to the OS. Port 3333 is used for HTTP, and port 3334 is used for HTTPS.
The remote control is disabled, and ports are closed by default. |
| Ports |  | There are no other open ports; the device only accepts TCP responses for DICOM, remote control API and replies to ICMP ping requests. |

## Data at rest and in transit

The MVR/MTR device uses SQLite3 databases and a JSON file to secure information about the device configurations, users, and network configurations. The SQLite database and JSON file are inaccessible from the GUI, but photos and videos can be exported to a PACS server, Network Storage, or USB Storage. The audit log can be exported to a USB disk. A JSON file with device and network configurations can be backed up to a USB disk. The following exportable data are stored:

| Item at rest | Format | Comments |
| :---- | :---- | :---- |
| Image | JPG, PNG | \- |
| Video | MP4 | H.264 or HEVC compression |
| Patient info | TXT, JSON, CSV |  |
| Audit log | TXT | The exported audit log allows users’ activities and system events to be tracked. The Audit log does not contain patient information and can be exported to a USB flash drive by an Administrator. |

Photos and videos can be transferred to a PACS server, USB flash drive, or Network drive.  
The following formats and protocols are used during the transfer:

| Item in transit | Export to | Format | Protocol |
| :---- | :---- | :---- | :---- |
| Photo | PACS | DICOM | DICOM |
|  | Network drive | JPG, PNG | SAMBA |
|  | USB flash drive | JPG, PNG, DICOM |  |
| Video | PACS | DICOM | DICOM |
|  | Network drive | MP4 | SAMBA |
|  | USB flash drive | MP4, DICOM |  |
| Patient info | Network drive | TXT, JSON, CSV | SAMBA |
|  | USB flash drive | TXT, JSON, CSV |  |
| Audit log | USB flash drive | TXT |  |

---
# Network Security

Applicable device models: MVR435, MVR436, MVR450, MVR460, MTR133, MTR156, MTR245.

Network services are **off by default** to minimize the attack surface and provide a secure out-of-the-box experience — Remote Access requires a unique password to be assigned when first enabled. NTP synchronizes automatically with hospital time servers for accurate recording timestamps (see Networking below).

## Communication Ports


| Comms Service | Port Number | Protocol | Direction | Status | Notes |
|---|---|---|---|---|---|
| HTTPS (Remote) | 3333 | TCP | Inbound/Outbound | Disabled by default | Remote device settings and secure video streaming. Server. |
| HTTPS (Remote) | 3334 | TCP | Inbound/Outbound | Disabled by default | Alternative port for remote settings and secure video streaming. Server. |
| HTTPS | 443 | TCP | Inbound/Outbound | Disabled by default | Standard secure web interface access. Server. |
| DICOM Store | 104 | TCP | Outbound | Disabled by default | Transfer of captured studies to PACS/VNA. Client. |
| DICOM MWL | 104 | TCP | Inbound/Outbound | Disabled by default | Modality Worklist queries for patient data. Client. |
| Samba/SMB | 445 | TCP | Outbound | Disabled by default | Mapping network drives for automated file storage. Client. |
| NTP | 123 | UDP | Outbound | Disabled by default | Device initiates requests to external servers for time synchronization. Client. |

---
# Manufacturer Disclosure Statement for Medical Device Security -- MDS2

MediCapture Inc., Models: MVR435, MVR436, MVR450, MVR460, MTR133, MTR156, MTR245.

DOC-1:Manufacturer Name:MediCapture Inc.
DOC-2:Device Description:Medical Video Recorder (with touchscreen)
DOC-3:Device Model:"MVR435, MVR436, MVR450, MVR460, MTR133, MTR156, MTR245"
DOC-4:Document ID:MDS2-MVR
DOC-5:Manufacturer Contact Information:"MediCapture Inc. 2250 Hickory Road, Suite 125, Plymouth Meeting, PA 19462, U.S.A. Tel. 888 922 7887  within the US) Tel. +1 503 445 6935 (outside US)"
DOC-6:Intended use of device in network-connected environment:"Optional use of NAS to storage recordings, optional obtain worklist from HIS, optional send recordings to PACS", 
DOC-7:Document Release Date:2026-03-20
DOC-8:Coordinated Vulnerability Disclosure; Does the manufacturer have a vulnerability disclosure program for this device?:Yes, MediCapture discloses vulnerabilities with security risk MEDIUM or higher directly to the affected customers.)
DOC-9:ISAO: Is the manufacturer part of an Information Sharing and Analysis Organization?:No
DOC-10:Diagram: Is a network or data flow diagram available that indicates connections to other system components or expected external resources?:Yes, See IFU and Supplementary guides
DOC-11:"SaMD: Is the device Software as a Medical Device (i.e. software-only, no hardware)?":No
DOC-11.1,Does the SaMD contain an operating system?: N/A
DOC-11.2,Does the SaMD rely on an owner/operator provided operating system? : N/A
DOC-11.3,Is the SaMD hosted by the manufacturer? : N/A,
DOC-11.4,Is the SaMD hosted by the customer? : N/A

MANAGEMENT OF PERSONALLY IDENTIFIABLE INFORMATION
MPII-1,"Can this device display, transmit, store, or modify personally identifiable information (e.g. electronic Protected Health Information (ePHI))? ": Yes,optional
MPII-2,Does the device maintain personally identifiable information? : Yes,
MPII-2.1,"Does the device maintain personally identifiable information temporarily in volatile memory (i.e., until cleared by power-off or reset)?  ": Yes
MPII-2.2,Does the device store personally identifiable information persistently on internal media? : Yes
MPII-2.3,Is personally identifiable information preserved in the device’s non-volatile memory until explicitly erased?: Yes
MPII-2.4,Does the device store personally identifiable information in a database? : No
MPII-2.5,Does the device allow configuration to automatically delete local personally identifiable information after it is stored to a long term solution?: Yes
MPII-2.6,"Does the device import/export personally identifiable information with other systems (e.g., a wearable monitoring device might export personally identifiable information to a server)?  ": Yes,Send to PACS
MPII-2.7,"Does the device maintain personally identifiable information when powered off, or during power service interruptions? ": Yes
MPII-2.8,"Does the device allow the internal media to be removed by a service technician (e.g., for separate destruction or customer retention)?": No
MPII-2.9,"Does the device allow personally identifiable information records be stored in a separate location from the device’s operating system (i.e. secondary internal drive, alternate drive partition, or remote storage location)? ": Yes,"PACS, NAS"
MPII-3,"Does the device have mechanisms used for the transmitting, importing/exporting of personally identifiable information?": Yes,"DICOM WL, HL7, PACS"
MPII-3.1,"Does the device display personally identifiable information (e.g., video display, etc.)?": Yes
MPII-3.2,Does the device generate hardcopy reports or images containing personally identifiable information?: Yes,"Optional, disabled by default"
MPII-3.3,"Does the device retrieve personally identifiable information from or record personally identifiable information to removable media (e.g., removable-HDD, USB memory, DVD-R/RW,CD-R/RW, tape, CF/SD card, memory stick, etc.)?": Yes,USB memory
MPII-3.4,"Does the device transmit/receive or import/export personally identifiable information via dedicated cable connection (e.g., RS-232, RS-423, USB, FireWire, etc.)?": No
MPII-3.5,"Does the device transmit/receive personally identifiable information via a wired network connection (e.g., RJ45, fiber optic,  etc.)? ": Yes
MPII-3.6,"Does the device transmit/receive personally identifiable information via a wireless network connection (e.g., WiFi, Bluetooth, NFC, infrared, cellular, etc.)?": No
MPII-3.7,"Does the device transmit/receive personally identifiable information over an external network (e.g., Internet)?": No
MPII-3.8,Does the device import personally identifiable information via scanning a document?  : No,
MPII-3.9,Does the device transmit/receive personally identifiable information via a proprietary protocol?: No,
MPII-3.10,"Does the device use any other mechanism to transmit, import or export personally identifiable information? ": Yes,"DICOM WL, HL7, PACS"

AUTOMATIC LOGOFF (ALOF) The device's ability to prevent access and misuse by unauthorized users if device is left idle for a period of time.
ALOF-1,"Can the device be configured to force reauthorization of logged-in user(s) after a predetermined length of inactivity (e.g., auto-logoff, session lock, password protected screen saver)?": Yes
ALOF-2,Is the length of inactivity time before auto-logoff/screen lock user or administrator configurable?: No

AUDIT CONTROLS (AUDT) The ability to reliably audit activity on the device.
AUDT-1,Can the medical device create additional audit logs or reports beyond standard operating system logs?: Yes
AUDT-1.1,Does the audit log record a USER ID?: Yes
AUDT-1.2,Does other personally identifiable information exist in the audit trail?: No,
AUDT-2,"Are events recorded in an audit log? If yes, indicate which of the following events are recorded in the audit log:": Yes
AUDT-2.1,Successful login/logout attempts?: Yes
AUDT-2.2,Unsuccessful login/logout attempts?: Yes
AUDT-2.3,Modification of user privileges?: Yes
AUDT-2.4,Creation/modification/deletion of users?: Yes
AUDT-2.5,"Presentation of clinical or PII data (e.g. display, print)?": No
AUDT-2.6,Creation/modification/deletion of data? : Yes
AUDT-2.7,"Import/export of data from removable media (e.g. USB drive, external hard drive, DVD)?": Yes
AUDT-2.8,Receipt/transmission of data or commands over a network or point-to-point connection?: No
AUDT-2.8.1,Remote or on-site support?: No
AUDT-2.8.2,Application Programming Interface (API) and similar activity? : Yes
AUDT-2.9,Emergency access?: Yes
AUDT-2.10,"Other events (e.g., software updates)?": Yes
AUDT-2.11,Is the audit capability documented in more detail?: No,
AUDT-3,Can the owner/operator define or select which events are recorded in the audit log? : No,
AUDT-4,Is a list of data attributes that are captured in the audit log for an event available?: No
AUDT-4.1,Does the audit log record date/time?: Yes
AUDT-4.1.1,Can date and time be synchronized by Network Time Protocol (NTP) or equivalent time source?: Yes
AUDT-5,Can audit log content be exported?: Yes
AUDT-5.1,Via physical media?: Yes
AUDT-5.2,Via IHE Audit Trail and Node Authentication (ATNA) profile to SIEM?: No
AUDT-5.3,"Via Other communications (e.g., external service device, mobile applications)?": No
AUDT-5.4,Are audit logs encrypted in transit or on storage media? : No
AUDT-6,Can audit logs be monitored/reviewed by owner/operator?: Yes,Admin only
AUDT-7,Are audit logs protected from modification?: Yes
AUDT-7.1,Are audit logs protected from access? : Yes,Admin only
AUDT-8,Can audit logs be analyzed by the device?: No

AUTHORIZATION (AUTH) The ability of the device to determine the authorization of users.
AUTH-1,Does the device prevent access to unauthorized users through user login requirements or other mechanism?: Yes
AUTH-1.1,"Can the device be configured to use federated credentials management of users for authorization (e.g., LDAP, OAuth)? ": Yes,LDAP
AUTH-1.2,"Can the customer push group policies to the device (e.g., Active Directory)? ": Yes
AUTH-1.3,"Are any special groups, organizational units, or group policies required?": Yes
AUTH-2,"Can users be assigned different privilege levels based on 'role' (e.g., user, administrator, and/or service, etc.)?": Yes
AUTH-3,"Can the device owner/operator grant themselves unrestricted administrative privileges (e.g., access operating system or application via local root or administrator account)?  ": No
AUTH-4,Does the device authorize or control all API access requests?: Yes
AUTH-5,"Does the device run in a restricted access mode, or ‘kiosk mode’, by default?": Yes

CYBER SECURITY PRODUCT UPGRADES (CSUP) "The ability of on-site service staff, remote service staff, or authorized customer staff to install/upgrade device's security patches."
CSUP-1,"Does the device contain any software or firmware which may require security updates during its operational life, either from the device manufacturer or from a third-party manufacturer of the software/firmware?  If no, answer “N/A” to questions in this section. ": Yes
CSUP-2,"Does the device contain an Operating System? If yes, complete 2.1-2.4.": Yes
CSUP-2.1,Does the device documentation provide instructions for owner/operator installation of patches or software updates?: Yes
CSUP-2.2,Does the device require vendor or vendor-authorized service to install patches or software updates?: No
CSUP-2.3,Does the device have the capability to receive remote installation of patches or software updates?: No
CSUP-2.4,"Does the medical device manufacturer allow security updates from any third-party manufacturers (e.g., Microsoft) to be installed without approval from the manufacturer?": No
CSUP-3,"Does the device contain Drivers and Firmware? If yes, complete 3.1-3.4.": Yes
CSUP-3.1,Does the device documentation provide instructions for owner/operator installation of patches or software updates?: Yes
CSUP-3.2,Does the device require vendor or vendor-authorized service to install patches or software updates?: No
CSUP-3.3,Does the device have the capability to receive remote installation of patches or software updates?: No
CSUP-3.4,"Does the medical device manufacturer allow security updates from any third-party manufacturers (e.g., Microsoft) to be installed without approval from the manufacturer?": No
CSUP-4,"Does the device contain Anti-Malware Software? If yes, complete 4.1-4.4.": No
CSUP-4.1,Does the device documentation provide instructions for owner/operator installation of patches or software updates?: N/A
CSUP-4.2,Does the device require vendor or vendor-authorized service to install patches or software updates?: N/A
CSUP-4.3,Does the device have the capability to receive remote installation of patches or software updates?: N/A
CSUP-4.4,"Does the medical device manufacturer allow security updates from any third-party manufacturers (e.g., Microsoft) to be installed without approval from the manufacturer?": N/A
CSUP-5,"Does the device contain Non-Operating System commercial off-the-shelf components? If yes, complete 5.1-5.4.": No
CSUP-5.1,Does the device documentation provide instructions for owner/operator installation of patches or software updates?: N/A
CSUP-5.2,Does the device require vendor or vendor-authorized service to install patches or software updates?: N/A
CSUP-5.3,Does the device have the capability to receive remote installation of patches or software updates?: N/A
CSUP-5.4,"Does the medical device manufacturer allow security updates from any third-party manufacturers (e.g., Microsoft) to be installed without approval from the manufacturer?": N/A
CSUP-6,"Does the device contain other software components (e.g., asset management software, license management)? If yes, please provide details or refernce in notes and complete 6.1-6.4.": No
CSUP-6.1,Does the device documentation provide instructions for owner/operator installation of patches or software updates?: N/A
CSUP-6.2,Does the device require vendor or vendor-authorized service to install patches or software updates?: N/A
CSUP-6.3,Does the device have the capability to receive remote installation of patches or software updates?: N/A
CSUP-6.4,"Does the medical device manufacturer allow security updates from any third-party manufacturers (e.g., Microsoft) to be installed without approval from the manufacturer?": N/A
CSUP-7,Does the manufacturer notify the customer when updates are approved for installation?: Yes
CSUP-8,Does the device perform automatic installation of software updates?: No
CSUP-9,Does the manufacturer have an approved list of third-party software that can be installed on the device?: No
CSUP-10,Can the owner/operator install manufacturer-approved third-party software on the device themselves? : No
CSUP-10.1,Does the system have mechanism in place to prevent installation of unapproved software?: Yes
CSUP-11,Does the manufacturer have a process in place to assess device vulnerabilities and updates? : Yes
CSUP-11.1,Does the manufacturer provide customers with review and approval status of updates?: Yes
CSUP-11.2,Is there an update review cycle for the device?: Yes

HEALTH DATA DE-IDENTIFICATION (DIDT) The ability of the device to directly remove information that allows identification of a person.

DIDT-1,Does the device provide an integral capability to de-identify personally identifiable information?: Yes
DIDT-1.1,Does the device support de-identification profiles that comply with the DICOM standard for de-identification?: No

DATA BACKUP AND DISASTER RECOVERY (DTBK) "The ability to recover after damage or destruction of device data, hardware, software, or site configuration information."
DTBK-1,Does the device maintain long term primary storage of personally identifiable information / patient information (e.g. PACS)?: No
DTBK-2,Does the device have a “factory reset” function to restore the original device settings as provided by the manufacturer?: Yes
DTBK-3,Does the device have an integral data backup capability to removable media?: Yes
DTBK-4,Does the device have an integral data backup capability to remote storage?: No,
DTBK-5,"Does the device have a backup capability for system configuration information, patch restoration, and software restoration? ": Yes,User settings only
DTBK-6,Does the device provide the capability to check the integrity and authenticity of a backup?: No

EMERGENCY ACCESS (EMRG) The ability of the device user to access personally identifiable information in case of a medical emergency situation that requires immediate access to stored personally identifiable information.
EMRG-1,Does the device incorporate an emergency access (i.e. “break-glass”) feature?: Yes

HEALTH DATA INTEGRITY AND AUTHENTICITY (IGAU) How the device ensures that the stored data on the device has not been altered or destroyed in a non-authorized manner and is from the originator.
IGAU-1,"Does the device provide data integrity checking mechanisms of stored health data (e.g., hash or digital signature)?": No
IGAU-2,"Does the device provide error/failure protection and recovery mechanisms for stored health data (e.g., RAID-5)? ": No

MALWARE DETECTION/PROTECTION (MLDP) "The ability of the device to effectively prevent, detect and remove malicious software (malware)."
MLDP-1,Is the device capable of hosting executable software? : No
MLDP-2,Does the device support the use of anti-malware software (or other anti-malware mechanism)? Provide details or reference in notes.: No
MLDP-2.1,Does the device include anti-malware software by default? : No
MLDP-2.2,Does the device have anti-malware software available as an option? : No
MLDP-2.3,Does the device documentation allow the owner/operator to install or update anti-malware software? : No
MLDP-2.4,Can the device owner/operator independently (re-)configure anti-malware settings?: No
MLDP-2.5,Does notification of malware detection occur in the device user interface?  : No,
MLDP-2.6,Can only manufacturer-authorized persons repair systems when malware has been detected?  : No,
MLDP-2.7,Are malware notifications written to a log?: No,
MLDP-2.8,"Are there any restrictions on anti-malware (e.g., purchase, installation, configuration, scheduling)?": No,
MLDP-3,"If the answer to MLDP-2 is NO, and anti-malware cannot be installed on the device, are other compensating controls in place or available?": N/A
MLDP-4,Does the device employ application whitelisting that restricts the software and services that are permitted to be run on the device?: Yes
MLDP-5,Does the device employ a host-based intrusion detection/prevention system?: No
MLDP-5.1,Can the host-based intrusion detection/prevention system be configured by the customer?: N/A
MLDP-5.2,Can a host-based intrusion detection/prevention system be installed by the customer?: N/A

AUTHENTICATION (NAUT) The ability of the device to authenticate communication partners/nodes.
NAUT-1,"Does the device provide/support any means of node authentication that assures both the sender and the recipient of data are known to each other and are authorized to receive transferred information (e.g. Web APIs, SMTP, SNMP)?": Yes
NAUT-2,"Are network access control mechanisms supported (E.g., does the device have an internal firewall, or use a network connection white list)?": No
NAUT-2.1,Is the firewall ruleset documented and available for review?: N/A
NAUT-3,Does the device use certificate-based network connection authentication?: No

CONNECTIVITY CAPABILITIES (CONN) All network and removable media connections must be considered in determining appropriate security controls. This section lists connectivity capabilities that may be present on the device.
CONN-1,Does the device have hardware connectivity capabilities?____
CONN-1.1,Does the device support wireless connections?____
CONN-1.1.1,Does the device support Wi-Fi?: No
CONN-1.1.2,Does the device support Bluetooth? : No
CONN-1.1.3,"Does the device support other wireless network connectivity (e.g. LTE, Zigbee, proprietary)?": No
CONN-1.1.4,"Does the device support other wireless connections (e.g., custom RF controls, wireless detectors)? ": No
CONN-1.2,Does the device support physical connections?: Yes
CONN-1.2.1,Does the device have available RJ45 Ethernet ports? : Yes
CONN-1.2.2,Does the device have available USB ports? : Yes
CONN-1.2.3,"Does the device require, use, or support removable memory devices?": No
CONN-1.2.4,Does the device support other physical connectivity?: Yes,"HDMI, DP, SDI"
CONN-2,Does the manufacturer provide a list of network ports and protocols that are used or may be used on the device?: Yes
CONN-3,Can the device communicate with other systems within the customer environment?: Yes
CONN-4,"Can the device communicate with other systems external to the customer environment (e.g., a service host)?": No
CONN-5,Does the device make or receive API calls?: Yes,"Optional, disabled by default"
CONN-6,Does the device require an internet connection for its intended use?: No
CONN-7,Does the device support Transport Layer Security (TLS)?: Yes
CONN-7.1,Is TLS configurable?: Yes,HTTPS/HTTP
CONN-8,"Does the device provide operator control functionality from a separate device (e.g., telemedicine)?": No

PERSON AUTHENTICATION (PAUT) The ability to configure the device to authenticate users.
PAUT-1,Does the device support and enforce unique IDs and passwords for all users and roles (including service accounts)?: Yes,Optional
PAUT-1.1,Does the device enforce authentication of unique IDs and passwords for all users and roles (including service accounts)?: Yes, Optional
PAUT-2,"Is the device configurable to authenticate users through an external authentication service (e.g., MS Active Directory, NDS, LDAP, OAuth, etc.)?": Yes,LDAP
PAUT-3,Is the device configurable to lock out a user after a certain number of unsuccessful logon attempts?: No
PAUT-4,"Are all default accounts (e.g., technician service accounts, administrator accounts) listed in the documentation?": N/A: No default accounts
PAUT-5,Can all passwords be changed?: Yes
PAUT-6,Is the device configurable to enforce creation of user account passwords that meet established (organization specific) complexity rules?: Yes
PAUT-7,Does the device support account passwords that expire periodically?: Yes
PAUT-8,Does the device support multi-factor authentication?: No
PAUT-9,Does the device support single sign-on (SSO)?: No
PAUT-10,Can user accounts be disabled/locked on the device?: Yes
PAUT-11,Does the device support biometric controls?: No
PAUT-12,Does the device support physical tokens (e.g. badge access)?: No
PAUT-13,Does the device support group authentication (e.g. hospital teams)?: No
PAUT-14,Does the application or device store or manage authentication credentials?: Yes
PAUT-14.1,Are credentials stored using a secure method?: Yes

PHYSICAL LOCKS (PLOK) Physical locks can prevent unauthorized users with physical access to the device from compromising the integrity and confidentiality of personally identifiable information stored on the device or on removable media
PLOK-1,"Is the device software only? If yes, answer “N/A” to remaining questions in this section.": No
PLOK-2,"Are all device components maintaining personally identifiable information (other than removable media) physically secure (i.e., cannot remove without tools)? ": Yes
PLOK-3,Are all device components maintaining personally identifiable information (other than removable media) physically secured behind an individually keyed locking device?: Yes
PLOK-4,Does the device have an option for the customer to attach a physical lock to restrict access to removable media?: No,Option to disable all removable media

ROADMAP FOR THIRD PARTY COMPONENTS IN DEVICE LIFE CYCLE (RDMP) Manufacturer’s plans for security support of third-party components within the device’s life cycle.
RDMP-1,"Was a secure software development process, such as ISO/IEC 27034 or IEC 62304, followed during product development?": Yes,IEC 62304
RDMP-2,Does the manufacturer evaluate third-party applications and software components included in the device for secure development practices? : Yes
RDMP-3,Does the manufacturer maintain a web page or other source of information on software support dates and updates?: Yes
RDMP-4,Does the manufacturer have a plan for managing third-party component end-of-life?: No: No end-of-life components

SOFTWARE BILL OF MATERIALS (SBoM) A Software Bill of Material (SBoM) lists all the software components that are incorporated into the device being described for the purpose of operational security planning by the healthcare delivery organization. This section supports controls in the RDMP section.
SBOM-1,Is the SBoM for this product available?: No
SBOM-2,Does the SBoM follow a standard or common method in describing software components?: Yes
SBOM-2.1,Are the software components identified? : Yes
SBOM-2.2,Are the developers/manufacturers of the software components identified?: Yes
SBOM-2.3,Are the major version numbers of the software components identified?: Yes
SBOM-2.4,Are any additional descriptive elements identified?: Yes
SBOM-3,Does the device include a command or process method available to generate a list of software components installed on the device?: No
SBOM-4,Is there an update process for the SBoM?: Yes

SYSTEM AND APPLICATION HARDENING (SAHD) The device's inherent resistance to cyber attacks and malware.
SAHD-1,Is the device hardened in accordance with any industry standards?: Yes
SAHD-2,Has the device received any cybersecurity certifications?: Yes,Internal
SAHD-3,Does the device employ any mechanisms for software integrity checking: Yes
SAHD-3.1,"Does the device employ any mechanism (e.g., release-specific hash key, checksums, digital signature, etc.) to ensure the installed software is manufacturer-authorized?": Yes
SAHD-3.2,"Does the device employ any mechanism (e.g., release-specific hash key, checksums, digital signature, etc.) to ensure the software updates are the manufacturer-authorized updates?": Yes
SAHD-4,"Can the owner/operator perform software integrity checks (i.e., verify that the system has not been modified or tampered with)?": No,Read-only closed OS
SAHD-5,"Is the system configurable to allow the implementation of file-level, patient level, or other types of access controls?": No
SAHD-5.1,Does the device provide role-based access controls?: Yes
SAHD-6,Are any system or user accounts restricted or disabled by the manufacturer at system delivery? : Yes,All accounts are disabled at delivery
SAHD-6.1,Are any system or user accounts configurable by the end user after initial configuration?  : Yes
SAHD-6.2,"Does this include restricting certain system or user accounts, such as service technicians, to least privileged access?": Yes
SAHD-7,"Are all shared resources (e.g., file shares) which are not required for the intended use of the device disabled?": Yes
SAHD-8,Are all communication ports and protocols that are not required for the intended use of the device disabled?: Yes
SAHD-9,"Are all services (e.g., telnet, file transfer protocol [FTP], internet information server [IIS], etc.), which are not required for the intended use of the device deleted/disabled?": Yes
SAHD-10,"Are all applications (COTS applications as well as OS-included applications, e.g., MS Internet Explorer, etc.) which are not required for the intended use of the device deleted/disabled?": Yes
SAHD-11,"Can the device prohibit boot from uncontrolled or removable media (i.e., a source other than an internal drive or memory component)?": Yes
SAHD-12,Can unauthorized software or hardware be installed on the device without the use of physical tools?: No
SAHD-13,Does the product documentation include information on operational network security scanning by users?: No
SAHD-14,Can the device be hardened beyond the default provided state?: Yes
SAHD-14.1,Are instructions available from vendor for increased hardening?: Yes,IFU
SHAD-15,Can the system prevent access to BIOS or other bootloaders during boot?: Yes,
SAHD-16,Have additional hardening methods not included in 2.3.19 been used to harden the device?: Yes,Read-only closed OS

SECURITY GUIDANCE (SGUD) Availability of security guidance for operator and administrator of the device and manufacturer sales and service.
SGUD-1,Does the device include security documentation for the owner/operator?: Yes,IFU
SGUD-2,"Does the device have the capability, and provide instructions, for the permanent deletion of data from the device or media? ": Yes,IFU
SGUD-3,Are all access accounts documented?: Yes,IFU
SGUD-3.1,Can the owner/operator manage password control for all accounts?: Yes
SGUD-4,Does the product include documentation on recommended compensating controls for the device?: No

HEALTH DATA STORAGE CONFIDENTIALITY (STCF) The ability of the device to ensure unauthorized access does not compromise the integrity and confidentiality of personally identifiable information stored on the device or removable media.
STCF-1,Can the device encrypt data at rest? : No
STCF-1.1,Is all data encrypted or otherwise protected?: N/A,
STCF-1.2,Is the data encryption capability configured by default? : N/A,
STCF-1.3,Are instructions available to the customer to configure encryption?: N/A,
STCF-2,Can the encryption keys be changed or configured?: No
STCF-3,Is the data stored in a database located on the device? : No
STCF-4,Is the data stored in a database external to the device?: No

TRANSMISSION CONFIDENTIALITY (TXCF) The ability of the device to ensure the confidentiality of transmitted personally identifiable information.
TXCF-1,Can personally identifiable information be transmitted only via a point-to-point dedicated cable?: No
TXCF-2,Is personally identifiable information encrypted prior to transmission via a network or removable media? : Yes
TXCF-2.1,"If data is not encrypted by default, can the customer configure encryption options?": No
TXCF-3,Is personally identifiable information transmission restricted to a fixed list of network destinations?: Yes
TXCF-4,Are connections limited to authenticated systems?: No
TXCF-5,"Are secure transmission methods supported/implemented (DICOM, HL7, IEEE 11073)?": Yes

TRANSMISSION INTEGRITY (TXIG) The ability of the device to ensure the integrity of transmitted data.
TXIG-1,"Does the device support any mechanism (e.g., digital signatures) intended to ensure data is not modified during transmission?": No
TXIG-2,Does the device include multiple sub-components connected by external cables?: No

REMOTE SERVICE (RMOT) Remote service refers to all kinds of device maintenance activities performed by a service person via network or other remote connection.
RMOT-1,Does the device permit remote service connections for device analysis or repair?: Yes
RMOT-1.1,Does the device allow the owner/operator to initiative remote service sessions for device analysis or repair? : Yes
RMOT-1.2,Is there an indicator for an enabled and active remote session? : Yes
RMOT-1.3,Can patient data be accessed or viewed from the device during the remote session?: No
RMOT-2,Does the device permit or use remote service connections for predictive maintenance data?: No
RMOT-3,"Does the device have any other remotely accessible functionality (e.g. software updates, remote training)?": No
