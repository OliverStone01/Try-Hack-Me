# 🚪 Room: Windows Fundamentals part 3

## 🎯 Objectives
- In part 3 of the Windows Fundamentals module, learn about the built-in Microsoft tools that help keep the device secure, such as Windows Updates, Windows Security, BitLocker, and more...

## 🛠️ Tools Used
-

## 💬 Summary
- Windows Updates
- Windows Security
- Virus & threat protection
- Firewall & network protection
- App & browser control
- Device security
- Bitlocker
- Volume Shadow Copy Service

-----

## Notes

### Task 2 - Windows Updates

Windows update is a service provided by Microsoft to provide security updates, feature enhancements, and patches for the Windows operating system and other Microsoft products, such as Microsoft Defender.

Updates are typically released on the 2nd Tuesday of every month. This day is called patch Tuesday. That doesn't necessarily mean that a critical update/patch has to wait for the next patch Tuesday to be released. If the update is urgent, then Microsoft will push the update via the Windows Update servce to the Windows devices.

Windows updates are located in the settings panel.

Throughout the years, Windows users have been putting off doing the updated as it usualy requires an update after which can cause lots of delays on the tasks the user is trying to complete.

Microsoft addressed this with Windows 10 by making it so that updates can no longer be ignored, only postponed. 


-----

### Task 3 - Windows Security

Windows Security is the home to manage the tools that protect your device and your data.

Protection areas:
- Virus & threat protection
- Firewall & network protection
- App & browser control
- Device security

When it comes to status icons:
- **Green** means your device is sufficiently protected.
- **Yellow** means there is a safety recommendation for you to review.
- **Red** is a warning that something needs your immediate attention.


-----

### Task 4 - Virus & threat protection

Virus & threat protection is divided into two parts:
- Current threats
- Virus & threat protection settings

#### Current threats

**Scan options**
- Quick scan checks folders in your system where threats are commonly found.
- Full scan checks all files and running programs on your hard disk.
- Custom scan allows the user to choose which files and locations you want to check.

**Threat history**
- Last scan shows the date and type of the last automatic scan the device did.
- Quarantined threats are threats that have been isolated and preventing them from running on your device.
- Allowed threats are items that have previously been identified as threats but have been allowed to run on your device.


#### Virus & threat protection settings

**Manage settings**
- Real-time protection locates and stops malware from installing or running on your device.
- Cloud-delivered protection provides increased and faster protection with access to the latest protection data in the cloud.
- Automatic sample submission sends sample files to Microsoft to help protect you and others from potential threats.
- Controlled folder access protects files, folders, and memory areas on your device from unauthorised changes by unfriendly applications.
- Exclusion tells Windows Defender to exclude the set items.
- Notification will be sent with critical information about the health of the device.

Make sure to manually check for updates to update Windows Defender Antivirus definitions.

Controlled folder access will protect against ransomware.


-----

### Task 5 - Firewall & network protection

A firewall controls the traffic flows into and out of a device through ports. You can think of this as a security guard standing at the door checking the ID of everything that tries to enter or exit.

Microsoft firewalls offer three profiles:
- Domain - applies to networks where the host system can authenticate to a domain controller.
- Private - This is a user-assigned profile and is used to designate private or home networks.
- Public - This is the default profile, used to designate public networks such as WI-FI hotspots at coffee shops, airports, and other locations.

-----

### Task 6 - App & browser control

Microsoft Defender SmartScreen protects against phishing or malware websites and applications, and downloading of potentially malicious files.

-----

### Task 7 - Device security

#### Core isolation

**Memory integrity** prevents attacks from inserting malicious code into high-security processes.

Trusted platform module (TPM) is designed to provide hardware-based security related functions. A TPM chip is a secure crypto-processor that is designed to carry out cryptographic operations. The chip includes multiple physical security mechanisms to make it tamper-resistant, and malicious software is unable to temper with the security functions of the TPM.


-----

### Task 8 - BitLocker

BitLocker Drive Encryption is a data protection deature that integrates with the operating system and addresses the threats of data theft or exposure from lost, stolen, or inappropriately decommissioned computers.

BitLocker provides the most protection when used with a Trusted Platform Module (TPM) version 1.2 or later.

-----

### Task 9 - Volume Shadow Copy Service

The Volume shadow copt service (VSS) coordinates the request actions to create a consistent shadow copy (also known as a snapshot) of the data that is to be backed up.

The Volume Shadow Copies are stores on the system volume information folder on each drive that has protection enabled.

If VSS is enabled, you can perform the following tasks from advanced system settings:
- Create a restore point
- Perform system restore
- Configure restore settings
- Delete restore points

From a security perspectivem malware writers know of this Windows feature and write code in their malware to look for these files and delete them. Doing so makes it impossible to recover from a ransomware attack  unless you have an offline/off-site backup.


-----

## Questions and Answers

### Task 1

**q1.** Read the above and start the virtual machine.

Answer = No answer needed

-----

### Task 2

**q1.** There were two definition updates installed in the attached VM. On what date were these updates installed?

Answer = 5/3/2021

-----

### Task 3

**q1.** Checking the Security section on your VM, which area needs immediate attention?

Answer = Virus & threat protection

-----

### Task 4

**q1.** Specifically, what is turned off that Windows is notifying you to turn on?

Answer = Real-time protection

-----

### Task 5

**q1.** If you were connected to airport Wi-Fi, what most likely will be the active firewall profile?

Answer = Public network

-----

### Task 6

**q1.** Read the above

Answer = No answer needed

-----

### Task 7

**q1.** What is the TPM?

Answer = Trusted Platform Module

-----

### Task 8 

**q1.** We should use a removable drive on systems without a TPM version 1.2 or later. What does this removable drive contain?

Answer = startup key

-----

### Task 9

**q1.** What is VSS?

Answer = Volume Shadow Copy Service

-----

### Task 10

**q1.** Read the above

Answer = No answer needed

-----
