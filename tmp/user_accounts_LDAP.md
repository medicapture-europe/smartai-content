This document contains information on User Accounts, Authentication, LDAP server authentication for the MVR, MTR and MSP device.

# USER ACCOUNTS for security protection of MVR and MTR series devices

MVR, MTR Medical Video Recorders as well as MSP Smart Control Panels, implement Role-Based Access Control (RBAC) to the device to protect access to data over the hospital networks and to the local recordings. MVR devices can be locked with User accounts for advanced device protection and data security of recorded studies.

Warning: Once user accounts are enabled, you must know your User Names and passwords to operate the MVR device. MediCapture company has no access to user account information, and there is no “Master Password” existing. If you do not remember your user account information, MVR device requires a complete setup to factory default settings, meaning much of your information will get lost.

As a first action, it is advised to create an administrator account to log in at any time.

- Go to the User accounts page: ➤ Settings ➤ Advanced ➤ User Accounts  
- Enable User accounts  
- Enter the User Name  
- Enter a password for this User account

As of firmware release FW220602, User Roles can be assigned. The ADMIN role must be assigned to at least one created User. Different user account levels (roles) protect Settings and Advanced Settings from misuse. **Migration from previous MVR software:** All existing users are assigned USER roles when an update is installed. An administrator can configure users in Advanced settings, where adding, deleting, renaming users, and changing their roles is possible.

## Roles:

- ADMIN: User that has access to all parts of the MVR. At least one user account must be created as ADMIN. MVR checks this and ensures that this condition is met. Only ADMIN has access to Advanced Settings, including setup screens for Connections, Storage Rules, Update and Default, User Accounts, Activation keys, Audit Trail.  
- USER: Standard user. Limitation: Access to Advanced Settings is blocked.  
- GUEST: Limited to access Archive for reviewing only.

All user roles allow connecting to the device stream using a web browser. Emergency login is a unique role called “Break the glass.”: Anybody who can log in from the home screen can create a study but has no rights to do anything else. Emergency User is not configurable.

## Starting an MVR and MTR recorder with a User Account:

Users can LOG IN with their User Name and Password. If the User account information is lost, the administrator can log in with his password and manage the list of users.

## Security feature “Break The Glass” of MVR and MTR series devices

From Firmware 210126\. When user accounts are enabled on the MVR, this new feature allows emergency studies to be started without user login and activated in case of emergency if a password is lost or unavailable. Tap the icon at the top right of the login screen with a cross to start a Study. The Remote App’s Emergency button is available ONLY during direct USB tethering. This function is limited only to the execution of a study; archive information and settings can NOT be viewed. Patient information can be edited afterward using proper login.

## Advanced Security features of MVR and MTR series devices

From firmware 210126: New section “Security” in Advanced Settings for Administrators. Passwords are crucial for safeguarding hospital information systems. It's vital to create secure passwords (minimum eight characters, mixing uppercase and lowercase) and manage them appropriately. The Chief Information Officer enforces these standards. MediCapture, Inc. isn't liable for password misuse by unauthorized parties accessing your LAN or Wi-Fi.

### Renew password

Renewing the password is an optional setting, after which period the user is notified to change the password for his User Account. The MVR only reminds to renew the password but does not force a block of user accounts. Range: From 1 week to 6 months. Default: Never.

### Strength of password

When entering the password for a User Account, the user gets information about the password’s strength. The MVR only informs about the strength but does not block a weak password. Actual enforcement of password strength is the responsibility of the administrator.

### Inactivity Timeout.

The period after which the MVR switches to screen saver mode. Screen saver mode is a black screen with a digital clock showing current time. Clock position is randomly changed to prevent screen burn-through. To quick screen saver mode \- tap screen or hit any key. Logged-in user will need to enter his password again. Inactivity times is disabled during the active Study. Range: From 1 minute to 60 minutes. Default: 10 minutes.

## Security Feature: Audit Trail for MVR and MTR series devices

- Serves two purposes: compliance with specific regulations, and providing better data (log file) for customer support requests.  
- Records (logs) all critical events in the device and necessary user actions.  
- The database keeps the last 5,000 events; older events are automatically deleted.  
- Audit Trail may be accessed from the Advanced Settings screen, Audit Trail Box.  
- To comply with common security regulations, Advanced Settings should be locked under the admin password, and only one admin user can access Audit Trail.  
- Access to the Audit Trail is limited to the local user (using device UI) and remote admin through the web configuration interface.  
- Locally (at the device), the audit log may be filtered, viewed, exported to USB flash, and erased.  
- From the remote web interface, the audit log can be exported and erased.  
- Remote App will not provide access to the Audit Trail; however, all actions performed from the remote App will also be logged.  
- No patient information is saved in the log.

—

# LDAP Authentication Feature for MVR/MTR devices

This security feature enables centralized user control on MVR/MTR devices. In addition to the existing local user control on these devices, it authenticates users over the central server.  
Applicable device models: MVR435, MVR436, MVR450, MVR460, MTR133, MTR156 and newer.  
Introduced since firmware version FW 250225\.  
Available free of charge as a core security feature for new devices and via a firmware update for the devices in the field. 

LDAPS stands for Lightweight Directory Access Protocol Secure. It is a protocol for accessing and managing directory information within a network. Think of it as a phonebook for the network, but instead of just names and numbers, it stores information about users, computers, and other resources.

## Description

MVR Medical Video Recorder implements Role-Based Access Control (RBAC) to the device to protect access to data over the hospital networks and to the local recordings. Three roles are defined:

* Guest: Limited to accessing the Archive for review only and to the live video stream; no access to the MVR device or data;  
* User: Access to the MVR device to record, review, document video content, and view live video stream;  
* Admin: Access all the above features, device settings, user management, and device maintenance.

LDAPS is the security feature of the MVR Medical Video Recorder, allowing access to the MVR device using authentication over the central directory, such as Active Directory. The central authority can grant access to the MVR devices by assigning users to specific groups in the central directory, such as the "MVR operator." It is also possible to use existing group assignments, such as “surgeons, nurses”.

The reason for implementing the LDAPS protocol is that more hospitals have started specifying it as a central user management requirement, which could soon become mandatory. A typical requirement is AsureAD authentication with 2FA; however, simplification of the LDAPS is accepted for devices without a browser.

## LDAP Administrator Workflow

Before setting up the device, communicate with the central LDAP administrator to perform the following actions and obtain the following information:

1. LDAPS server URL or IP address  
2. Port number, if it is different from the default port 636\.  
3. Naming context. Example: ‘cn=accounts,dc=demo1,dc=freeipa,dc=org’  
4. Create several test users. Example: mvrAdmin1, mvrAdmin2, mvrUser1, mvrUser2, mvrGuest.  
5. Provide an example of a full DN for user authentication, like: 'uid=mvrAdmin1,cn=users,cn=accounts,dc=demo1,dc=freeipa,dc=org'  
6. Create three groups: mvradmins, mvrusers, mvrguests, corresponding to the roles: admin, user, guest. It is possible to use existing groups. Provide an example of a full group DN, like:  
    'cn=mvradmins,cn=groups,cn=accounts,dc=demo1,dc=freeipa,dc=org'. Create  
7. Add users mvrAdmin1, mvrAdmin2 to the group mvradmins; mvrUser1, mvrUser2 to group mvrusers; and mvrGuest to group mvrguests.

## Workflow on the MVR/MTR device

Workflow of the LDAPS user authentication:

1. A user enters credentials (user name and password) on the MediCapture MVR/MTR device login screen;  
2. The MVR/MTR device tries to bind (authenticate) the user to the remote LDAPS server (e.g., AzureAD). If binding is successful, an LDAPS search is performed to determine whether the user belongs to a particular group (“MVR,” for example). After all checks are passed, the LDAPS connection is closed, and the user can access the MVR device.  
3. Logout is performed automatically by the timeout or by tapping the logout button.

The LDAP(S) implementation for MVR does not require a special service account and does not store a copy of the LDAP user information in bulk. Instead, the MVR implementation of the LDAP client authenticates every user individually and does not read and store any other information from the LDAP server. The connection to the LDAP(S) server is closed immediately after the login authentication attempt.

### Offline Authentication

Upon successful LDAPS authentication, the user is added to the local list of users for offline authentication with a timeout. The timeout can be set in hours from 0 to 10,000, with the default being 168 hours (one week). When the timer expires, the user is deleted.   
Offline authentication is used only when the LDAPS server is unavailable (offline). Why can the device be offline? The MVR/MTR device may be installed on a mobile trolley—a surgical tower—which is moved from one operating room to another. During surgery, the mobile trolley may not be connected to the network, and the device should be able to authenticate the user offline.  
When LDAPS is online, authentication and group checks are enforced. Successful authentication resets the user's timeout. Failed authentication (when user rights have been removed centrally) deletes the user immediately from the local list, disregarding the timeout.   
The admin can manually review the list of users and delete users when necessary in the same way as managing local users.

## LDAP Server Setup

There are several fields for the LDAP server setup:

* “Enabled” switch: turn it on to enable the use of the LDAP server and the ability to enter or edit other fields.  
* “Server”: input the URL or IP address of the remote LDAP server.  
* “Port”: input port number; leave blank for default port numbers: 389 or 636 with SSL.  
* “Use SSL”: Turn it on to use the secure LDAPS protocol (recommended).  
* “Naming context”: The naming context will be appended to the “Auth path” for user authentication and group paths for group search. This field will be automatically entered after the server Test; edit it to add extra context when necessary. The warning message will show “Authentication is required” when the Test button is pressed and the LDAP server does not allow anonymous binding. In this case, enter the “Naming context” manually. See the test examples below.  
* “Auth path”: optional extra path when the full authentication path is longer than the “Naming context”.  
* “Admin groups”, “User groups”, “Guest groups”: These three groups determine the user role as Admin/User/Guest. groupDN (Distinguished Name) is built using a group path appended with the “Naming context”. Keep empty to avoid this group; for example, no one can get an Admin role. Use \* symbol to allow this role for any user with valid credentials; for example, authenticated users can get a Guest role. Group check is performed from top to down: Admin, User, Guest. A user in multiple groups is assigned the highest priority role.  
* “Caching time” (hours): This specifies how long the logged-in LDAP user can log in again while the device is offline. The default is 168 hours or one week. Enter 0 to disable offline authentication.  
* The “Cancel” button will return to the previous screen without saving changes.  
* The “Test” button performs an anonymous authentication test on the LDAP server connection. The Server, Port, and Use SSL fields are used for server tests. The server may not allow anonymous binding and will respond with the warning “Authentication required”. This also means successful access to the LDAP server.  
* The “Test user” button performs user authentication and group checks.  
* The “Save” button must be used to save all changes. Changes will be lost if not saved.

The recommended LDAP Server Setup flow:

* Input Server, Port, Use SSL, and tap the “Test” button.  
* Edit the “Naming context” field, input the optional “Auth path”, and tap the “Test user” button.   
* Input group paths and “Test user” again for different roles.

### Test examples

The User Accounts feature should be enabled first. It is located in Settings \- Advanced \- User Accounts. At least one user with an Admin role should be created.  
After adding the first Admin user, click the Home button and log in as Admin to verify the account immediately. Keep this account safe; it will be impossible to restore it.   
Return to Settings \- Advanced \- User Accounts and tap the “LDAP” button in the top right corner of the screen.  
Turn ON the “Enabled” slider.   
Input the field Server: ldap.forumsys.com (public LDAP server for basic tests).   
Port: default (empty). Use SSL: no.   
Tap the “Test” button to perform the LDAP server connection test.  
Observe the error message. Ensure the device is online, the URL is not misspelled, and there are no extra spaces or punctuation.  
The example below shows the successful test of the LDAP server and the various information provided by the server. Tap the “OK” button to finish the test. Suggest tapping the “Save” button to save the tested server settings.  
The default naming context is obtained and populated in the “Naming context” field during the server test. Edit it when necessary. In this example, the Naming context is “dc=example,dc=com”. The warning message will show “Authentication is required” when the Test button is pressed and the LDAP server does not allow anonymous binding. In this case, enter the “Naming context” manually.

Tap on “Test user” and enter credentials “tesla/password”. Tick the “Show password” box to verify the correctness of your input.  
When credentials are correct and have been authenticated by the LDAP server, the test result will be shown as “User: tesla. Role: GUEST”. The Guest role has been assigned to “tesla” because we have a symbol “\*” in the “Guest groups” field, meaning that any user with the correct credentials will get this role. Tap the “OK” button to finish the user test.

There are three groups on the server “ldap.forumsys.com”, and we will use them to demonstrate the role assignment:  
ou=scientists: einstein, galieleo, tesla, newton.  
ou=mathematicians: euclid, riemann, euler, gauss, test.  
ou=chemists: curie, boyle, nobel, pasteur.  
The complete group DN is “ou=scientists,dc=example,dc=com.” We should enter only “ou=scientists” into our group field, which will later be automatically appended with the Naming context of “dc=example,dc=com.”  
The password for any user is “password”. One user, “nogroup”, does not belong to any group.   
The “ldap.forumsys.com” server uses a persistent, read-only test configuration so that you can rely on the consistency of the test results.

For the next test, enter “ou=scientists” into the “User groups” field, meaning that users from this group will be assigned the “User” role for the MVR/MTR device. Tap on “Test user” and enter the same credentials, “tesla/password”. The result will show “Role: USER”, because “tesla” indeed belongs to the group “ou=scientists”.  
Update the field “Admin groups” with “ou=chemists” and test user “nobel”. Because “nobel” belongs to the group “ou=chemists”, he will be assigned the Admin role. Experiment with other users and groups for the test server “ldap.forumsys.com”.

SSL (LDAPS) is recommended for enhanced security. An example of the LDAPS server test with “Use SSL” is below, using the public testing server “ipa.demo1.freeipa.org”. This server can be used with enabled or disabled SSL., It is recommended to use SSL whenever possible. The actual certificate is not verified (always trusted) for the initial implementation.  
In this example, the Naming context field will be populated with “dc=demo1,dc=freeipa, dc=org” after the server test.   
Edit the Naming context field as “cn=accounts,dc=demo1,dc=freeipa,dc=org” because this is the common part for the DN (Distinguished Name) for the LDAP server “ipa.demo1.freeipa.org”. Here are examples of the complete DN and group DN:  
DN \= 'uid=admin,cn=users,cn=accounts,dc=demo1,dc=freeipa,dc=org', which is constructed from three parts: user (uid=admin), Auth path (cn=users), and Naming context (cn=accounts,dc=demo1,dc=freeipa,dc=org).  
groupDN \= 'cn=employees,cn=groups,cn=accounts,dc=demo1,dc=freeipa,dc=org', which is constructed from two parts: group (cn=employees,cn=groups) and Naming context (cn=accounts,dc=demo1,dc=freeipa,dc=org).  
Set the “Auth path” field to “cn=users” because this is part of the authentication path, as explained above.  
The list of users for the “ipa.demo1.freeipa.org” demo server: manager, helpdesk, employee, admin, with the password for all users is “Secret123”.  
Please note that the “ipa.demo1.freeipa.org” test server is not persistent. Anyone can temporarily modify its content. FreeIPA's demo server resets daily at 05:00 UTC.   
Tap on “Test user” and enter the credentials “ManageR/Secret123”. The test result will show: “User: ManageR; Role: GUEST”. This example demonstrates that the user name is not case-sensitive.  
Now test the user with the wrong credentials “ManageR/secret123”. The password is case-sensitive, and authentication will fail, showing the message “Error: invalid credentials”.  
Now, populate group fields and perform group roles tests. Set “Admin groups” to “cn=admins,cn=groups”. Set “User groups” to “cn=employees, cn=groups”. Please note that “cn=employees,cn=groups” is a part of the path to a single group 'cn=employees,cn=groups,cn=accounts,dc=demo1,dc=freeipa,dc=org', not two separate groups.   
The group membership is tested against the following LDAP schema attributes: “member”, “uniqueMember”, and “memberUid”.

Test user “admin”. The result should be “User: admin; Role: ADMIN”.

Test user “manager”. The result should be “User: manager; Role: USER”.  
Test user “helpdesk”. The result should be “User: helpdesk; Role: GUEST”.

To complete the LDAPS server setup, remember to tap the “Save” button.

For the actual LDAPS server, the administrator can create two role-based groups, “ou=MVR admins” and “ou=MVR users”, for example. How to set up users and groups within the LDAP server itself is out of the scope of this document; local IT specialists need to be consulted.

## User Login

When user accounts are enabled, the device starts on the login screen. Entering incorrect credentials will cause an error “LDAP: invalid credentials”.  
For login demonstration, we use the last LDAPS settings for the “ipa.demo1.freeipa.org” demo server. Users: manager, admin, helpdesk, all with the same password “Secret123”.  
After the successful authentication by the LDAP server, a user (“manager” in the following example) will be allowed to use the MVR/MTR device with the User role. (See role definitions and privileges in the above text).   
The user name, “manager,” will be shown in the top left corner of the screen. “(LDAP)” note means that the LDAP server performed authentication. An icon on the left of the user name indicates an Admin, User, or Guest role.

## Users Management

Guest users have limited access to functions. A Regular User has no access to the Advanced settings. Log in with the Admin role to access “User accounts” to manage users.  
LDAP-authenticated users will be cached in the local (on-device) list of users for offline authentication. When the last user login time is older than the “Caching time”, the user will be automatically deleted from the list. It is also possible to delete any user manually by tapping the user entry and selecting “Delete” from the pop-up dialogue, followed by an extra confirmation.  
Enabling and using an LDAP server does not affect existing local accounts.   
One local Admin account should always exist on the device to manage LDAP server misconfiguration or faults.  
While the number of local user accounts is limited to 20, the number of temporarily authenticated LDAP users is not limited.

## Frequently Asked Questions

Can local and LDAP users log in simultaneously? What happens if a user exists both locally and in LDAP?  
Answer: User credentials are first checked against the local database and, when not authenticated, checked against the LDAP server.

If the LDAP server is unreachable and a cached user’s timeout hasn’t expired, can they still access the device?  
Answer: Yes.

How does the device handle revoked permissions during offline mode?  
Answer: There is no way to check for the revoked permissions offline. Once online, and the revoked user attempts to log in, rejection from the LDAP server will immediately remove the user from the local list of users.

If a user’s group membership changes on the LDAP server, how does the MVR device reflect this change? Is manual intervention required?  
Answer. No manual intervention is required; the user will be authenticated to the new role according to the current (not previous) group membership. However, when the group name was changed, manual editing of the group name is required on the LDAP server setup screen.

Can we create custom roles beyond Admin/User/Guest or map existing LDAP groups to custom permissions?  
Answer: No new roles or custom permissions are available. However, the existing LDAP group, “ou=surgeons,” for example, can be mapped to the standard User role.

How do I regain access if the LDAP server is misconfigured and the local Admin account is lost?  
Answer: The admin account can be re-created using the Remote configuration feature and a remote access password. If remote access is not configured or the password is lost, the device must be reset to factory defaults, which will wipe all settings.

Can LDAP configurations be backed up or transferred to another MVR device?  
Answer. Yes. Administrators can back up all device settings to the USB drive or use the Remote configuration feature via the local network.

## Glossary of Terms

**LDAPS**: Lightweight Directory Access Protocol Secure. An encrypted version of LDAP that uses SSL/TLS to secure communications between clients and directory servers.    
**Bind**: The LDAP operation to authenticate a client to the directory server.  
**SSL**: Secure Sockets Layer.    
**DN**: Distinguished Name. A unique identifier for an entry in an LDAP directory, structured hierarchically (e.g., \`cn=John Doe,ou=Users,dc=example,dc=com\`).    
**Base DN**: The root entry from which an LDAP search begins (e.g., dc=example,dc=com).  
**DC**: Domain Component. A part of a DN representing a domain name segment (e.g., \`dc=example,dc=com\` corresponds to the domain \`example.com\`).    
**CN**: Common Name. An attribute in a DN specifies the name of an object (e.g., a user, group, or device), such as \`cn=Alice Smith\`.    
**OU**: Organizational Unit. A container in a DN used to group entries by function, department, or role (e.g., \`ou=Engineering,dc=company,dc=org\`).   
**UID**: User Identifier. A unique attribute for a user account (e.g., uid=jdoe).  
**ObjectClass**: Defines the type of object an entry represents (e.g., person, organizationalUnit).  
**Attribute**: A property of an LDAP entry (e.g., mail, telephoneNumber).
