# 🚪 Room: Windows Fundamentals part 1 

## 🎯 Objectives
- In part 1 of the Windows Fundamentals module, we'll start our journey learning about the Windows desktop, the NTFS file system, UAC, the Control Panel, and more..

## 💬 Summary
- Windows editions
- The desktop (GUI)
- The file system
- The windows/System32 folders
- User accounts, Profiles, and permissions
- User account control
- Settings and the control panel
- Task manager

-----

## Notes

### Task 3 - Windows edition 

The windows operating system dates back to 1985 and is currently the dominant operating system in both home use and corporate networks. Becuase of this, Windows has always been targeted by hackers & malware writers.

Windows XP was a popular version of Windows and had a long running time. Microsoft then announced Windows Vista, which was a complete overhall of the windows operating system. There were many issues with Windows Vista. It wasn't receiced well by Windows users, and it was quickly phased out. 

When Windows announced the end-of-life date for Windows XP, many customers panicked. They all scrambled to test the next viable Windows version, which was Windows 7. Venders had to work against the clock to ensure their products worked with Windows 7.

Windows 11 is the current Windows operating system. Windows 11 comes in 2 options:
- Home
- Pro

The current server version on Windows is Windows Server 2025.

-----

### Task 3 - The desktop (GUI)

The Windows Desktop (GUI - Graphical User Interface), is the screen that welcomes you once you log into a windows 10-11 machine.

Traditionally, you need to pass the login screen first. The login screen is where you need to enter a valid account credentials.

The desktop is made up of the following:
- The Desktop
- Start Menu
- Search Box (Cortana)
- Task View
- Taskbar
- Toolbars
- Notification area

#### The Desktop

The desktop is where you will have shortcuts to programs, files, files, etc. These icons can be well organised in folders or scattered randomly.

You can change the feel of the desktop by right-clicking anywhere on the desktop, a context menu will appear. This menu will alow you to change the sizes of the desktop icons.

Under `display settings`, you can make changes to the screen's resolution and orientation. in case you have multiple computer screens, you can make configurations to the multi-screen setup here.

You can also personalise the background image, change fonts, themes, colour scheme, etc.


#### The start menu

The start menu provides access to all apps/programs, files, utility tools, etc. The start menu can be broken up into the following sections:

**1. The left menu** - Here is a shortcut to actions that you can perform with your acount. Such as making changes to your account, lock the screen, and signing out. Below that are shortcuts specific for files and picutes. Then there is a cog icon that will take you to the settings page. Then you have the power icon where you can power off or restart the device.

**2. Middle section** - This section shows recently added apps/programs at the top and all the installed apps/programs.

**3. Right side** - Here is where you will find icons for specific apps/programs or utilities. These icons are known as tiles.

You can add items to the start menu by right clicking on then and clicking on `pin to start`.


#### The taskbar

Any apps or programs you open will be seen in the taskbar. Hovering over the icon will show you a thumbnail of the running program. This is handy if you have multiple of the same program open as you will be able to see each one running. 


#### The Notification area 

This is located at the bottom right of the Windows screen where the data and time are displayed. Other icons possibly visible in this area. 

-----

### Task 4 - The file system

The `file system` used in modern versions of windows is called `NTFS` (New Technology File System).

Before NTFS, There was `FAT16/FAT32` (File allocation table) and `HPFS` (High performance file system).

You typically see FAT partitions in USB devices, MicroSD cards, etc.

NTFS is known as a journaling file system. in case of a failure, the file system can automatically repair the folder/files on disk using information stored in a log file. This function is not possible with FAT.

NTFS addresses many of the limitations of the previous file systems; such as:
- Supports files larger than 4GB
- Set specific permissions on folders and files.
- Folder and file compression
- Encryption (Encryption file system or EFS)

To check what file system your using, you can right-click on the file-drive and check.

On NTFS volumes, you can set permissions that grant or deny access to files and folders.

The permissions are:
- Full control
- Modify
- Read & Execute
- List folder contents
- Read
- Write

You can view the permissions for a file or folder by:
- Right-click on the file or folder you want to check.
- From the context menu, select `properties`.
- Within properties, click on the `security` tab.
- In the `Group or user names` list, select the user, computer, or group whose permissions you want to view.

Another feature of NTFS is `Alternate Data Streams (ADS)`.

Every file has at least one data steam ($DATA), and ADS allows files to contain more than one stream of data. Natively Windows Explorer doesn't display ADS to the user. There are 3rd party executables that can be used to view this data, but `powershell` gives you the ability to view ADS for file.

From a security perspective, malware writers have used ADS to hide data.

It's not only used maliciously, but it is also used for when you download a file from the internet to indentify that the file was downloaded.

-----

### Task 5 - The Windows\System32 folders

The Windows folder (`C:\Windows`) is traditionally known as the folder which contains the Windows operating system.

The folder doesn't have to reside in the C drive necessarily.

This is where system enviroment variables come into play. Even though not discussed, the system enviroment variable for the Windows directory is `%windir%`.

There are many folders within the `Windows` folder. One of which is `System32`. This hold the important files that are critical for the operating system.

You should proceed with extreme caution when interacting with this folder.

-----

### Task 6 - User accounts, Profiles, and permissions

User accounts can be of two types:
- Administrator
- Standard User

The user account will determine what actions the user can perform on that specific Windows system.
- An Administrator can make changes to the system
- A standared user can only make changes to folders/files attributed to the user & can't perform system-level changes, such as install programs.

There are several ways to determine which user accounts exist on the system.

One way is to click the `start menu` and type `other user`. A shortcut to `system settings > other users` should appear.

As administrator, you can add other people to this PC.

You can clock on the local user account. More options should appear: `Change account type` and `remove`.

When you click on change account type. The value in the drop-down box is the current account type.

When a user account is created, a location for each user profile folder will fall under `C:\Users`. For example, `C:\users\max`.

Each user profile will have the same folder; some of them are:
- Desktop
- Documents
- Downloads
- Music
- Pictures

Another way to access this information, and then some, is using `local user and group management`.

Right-click on the start menu and click `run`. Type `lusrmgr.msc`. You should now see two folders:
- Users
- Groups

If you click on groups, you see all the names of the local groups along with a brief description for each group.

Each group has its own permissions, and users are assigned/added to the group by the administrator. When a user is assigned to a group, the user inherits the permissions of that group.

-----

### Task 7 - User account control

The large majority of home users are logged into their Windows systems as local administrators.

A user does not need to run with high privilages on the system to run tasks that don't require such privileges, such as using the internet, working on a word document, etc. If the user has elevated privileges, it makes it easier for malware to infect the system. 

To protect the local user with such privilages, Microsoft introduced `User account control (UAC)`. By default, UAC is not applied to built in to the local admin accout.

When a user with an account type of administrator logs into a system, the current session doesn't run with elevated permissions. When an operation requiring higher-level privileges needs to execute, the user will be prompted to confirm if they permit the operation to run.

Let's look at a programs properties by right-clicking on the program and clicking on properties. Then clicking on the security tab, you can see which users have permission to use the program.

This shield icon is an indicator that UAC will prompt to allow higher-level privileges to install the program.

-----

### Task 8 - Settings and the control panel

On a Windows system, the primary location to make changes are the Settings menu and the control panel.

For a long time, the control panel has been the go-to location to make changes, such as adding a printer, uninstall a program, etc.

The settings menu was introduced in Windows 8.

Control panel is the menu where you will access more complex settings and perform more complex actions. In some cases, you will start in the settings tab and end up in the control panel.

-----

### Task 9 - Task manager

Task manager provides information about the applications and processes currently running on the system. Other information is also available, such as how much `CPU` and `RAM` are being utilised which falls under `performance`.

You can access task manager by right-clicking the taskbar or by doing `ctrl+shift+escape`.

-----

## Questions and Answers

### Task 1

**q1.** Read above and start the virtual machine.

Answer = No answer needed

-----

### Task 2

**q1.** What encryption can you enable on Pro that you can't enable in Home?

Answer = BitLocker

-----

### Task 3

**q1.** Which selection will hide/disable the Search box?

Answer = Hidden


**q2.** Which selection will hide/disable the Task View button?

Answer = Show Task View button


**q3.** Besides Clock and Network, what other icon is visible in the Notification Area?

Answer = Action Center

-----

### Task 4

**q1.** What is the meaning of NTFS?

Answer = New Technology File System

-----

### Task 5

**q1.** What is the system variable for the Windows folder?

Answer = %windir%

-----

### Task 6

**q1.** What is the name of the other user account?

Answer = tryhackmebilly


**q2.** What groups is this user a member of?

Answer = Remote Desktop Users,Users


**q3.** What built-in account is for guest access to the computer?

Answer = Guest


**q4.** What is the account description?

Answer = window$Fun1!

-----

### Task 7

**q1.** What does UAC mean?

Answer = User Account Control

-----

### Task 8

**q1.** In the Control Panel, change the view to Small icons. What is the last setting in the Control Panel view?

Answer = Windows Defender Firewall

-----

### Task 9

**q1.** What is the keyboard shortcut to open Task Manager?

Answer = Ctrl+Shift+Esc

-----

### Task 10

**q1.** Read above and terminate the Windows machine you deployed in this room.

Answer = No answer needed







