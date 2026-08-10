# Structure of Settings of MVR and MTR series devices

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
