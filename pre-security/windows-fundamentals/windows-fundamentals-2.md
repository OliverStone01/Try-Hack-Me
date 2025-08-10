# 🚪 Room: Windows fundamentals part 2

## 🎯 Objectives
- In part 2 of the Windows Fundamentals module, discover more about System Configuration, UAC Settings, Resource Monitoring, the Windows Registry and more..

## 🛠️ Tools Used
- MSConfig

## 💬 Summary
- System Configuration
- Change UAC settings
- Computer Management
- System Information
- Resource monitor
- Command prompt
- Registry editor

-----

## Notes

### Task 2 - System Configuration 

The System Configuration utility (`MSConfig`) is for advanced troubleshooting, and its main purpose is to help diagnose startup issues.

There are several methods to launch system configuration. One method is searching for `system configuration` in the start menu.

You must have local administrator rights to open this utility.

The utility has five tabs accross the top::
- General
- Boot
- Services
- Startup
- Tools

In the `general` tab, we can select what devices and services for Windows to load upon boot.

The options are:
- Normal
- Diagnostic
- Selective

In the `boot` tab, we can define various boot options for the operating system.

The `services` tab lists all services configured for the system regardless of their state (running or stopped). A service is a special type of application that runs in the background.

In the `startup` tab, you can see startup items. Microsoft recomends using task manager for enabling and disabling startup options.

There are a list of various tools in the `tools` tab that we can run to configure the operating system further. There is a brief description of each tool to provide some insight into what the tool is for.

To run a tool, we can use the command to launch the tool via the run prompt, command prompt, or by clicking the `launch` button.

-----

### Task 3 - Change UAC settings

Continuing with tools, `User account control (UAC)` settings can be changed or turned off (not recomended). You can move the slider to see how the features change. 

-----

### Task 4 - Computer Management

The `Computer Management (compmgmt)` utility has three primary sections:
- System tools
- Storage
- Services and applications

#### System tools

`task scheduler` - we can create and manage common tasks that our computer will carry out automatically at the times we specify.

A task can run an application, script, etc., and tasks can be configured to run at any point. A task can run at log in or at log off.

To create a basic task, click on `Create basic task` under actions.

`Event viewer` - allows us to view events that have occured on the computer. These records of events can be seen as audit trail that can be used to understand the activity of the computer system. This information is often used to diagnose problems and investigate actions executed on the system.

Event viewer has three panes:
1. The left pane provides a hierarchical tree listing of the event log providers.
2. The middle pane will display a general overview and summary of the events specific to a selected provider.
3. The pane on the right is the action pane.

There are five types of events that can be logged:
- Error
- Warning
- Information
- Success Audit
- Failure Audit

The standard logs are visible under `Windows Logs`:
- Application
- Security
- System
- customLog


`Shared folders` is where you will see a complete list of shares and folders that others can connect to.

With any object in Windows, you can right-click on a folder to view its properties, such as permissions.

`Sessions` is where you will see a list of users who are currently connected to the shares.

All the folders/files that the connected user access will list user `open files`.

The `local users and groups` section is `lusrmgr.msc`.

In `performance`, you will see a utility called `Performance monitor` (perfmon).

`Perfmon` is used to view performance data either in real-time or from a log file. This utility is useful for troubleshooting performance issues on a computer system, whether local or remote.

`Device manager` allows us to view and configure the hardware.

#### Storage

Under storage is `Windows server backup` and `Disk management`.

Disk management is a system utility in Windows that enables you to perform advanced storage tasks. Some of those tasks are:
- Set up a new drive
- Extend a partition
- Shrink a partition
- Assign or change a drive letter


#### Servies and Applications

WMI control configures and controls the `Windows management instrumentation` service.

-----

### Task 5 - System information

The `System information` (`msinfo32`) tool gathers information about your computer and display a comprehensive view of your hardware, system components, and software enviroment, which you can use to diagnose computer issues.

The information in `system summary` is divided into three sections:
- Hardware resources
- Components
- Software enviroment

System summary will display general technical specifications for the computer, such as processor brand and model.

The information displayed in `Hardware Resources` is not for the average computer user.

Under `components`, you can see specific information about the hardware devices installed on the computer. Some sections don't show any information, but some sections do such as `Display` and `Input`.

In the `Software enviroment` section, you can see information about software baked into the operating system and software you have installed. Other details are visible in this section.

`Enviromental variables` store information about the operating system enviroment.

-----

### Task 6 - Resource monitor

`Resource monitor (resmon)` displays per-process and aggregate CPU, memory, disk, and network usage information. Advanced filtering allows users to isolate the data related to one or more processes.

This tool is maintly used for advance toubleshooting.

In the `overview` tab, Resmon has four sections:
- CPU
- Disk
- Network
- Memory

-----

### Task 7 - Command prompt

The command prompt (`cmd`) in early operating systems was the sole way to interact with the operating system.

When the GUI was introduced, it allowed users to click buttons and interact visually to perform complex tasks.

A computer is still able to interact via the command prompt.

Here are a few simple commands:
- `hostname` - outputs the computers name
- `whoami` - outputs the name of the logged-in user.

Now lets look at some commands that are useful when troubleshooting.

A command used often is `ipconfig`. This command will show the network address settings for the computer.

Each command has its own help manual to explain the expected syntax to execute the command properly. To get access to the help manual, use `/?`.

For example, to see the help manual for `ipconfig`, you can use the following command `ipconfig /?`.

To clear the command screen, use `cls`.


The `netstat` command will display protocol statistics and current TCP/IP network connections.


The `net` command is primarily used to manage network resources. This command supports sub-commands.

If you type `net` without a sub-command, the output will show the syntax for the root command showing a few of the sub-commands you can use.

For the `net` command, using the usual `/?` for the help menu will not work. Instead, you need to use the keyword `help` like:
`net help user`.

-----

### Task 8 - Registry editor

The `Windows registy` is a central hierarchical database used to store information necessary to configure the system for one or more users, applications, and hardware devices.

The registry contains information that Windows continually references during operations, such as:
- Profiles for each user
- Applications installed on the computer and the types of documents that each can create.
- Property sheet settings for folders and application icons.
- What hardware exists on the system
- The ports that are being used

Making changes to the registry can effect normal computer operations.

There are various ways to view/edit the registry. one way is to use the `registry editor (regedit)`


-----

## Questions and Answers

### Task 1

**q1.** Read above and start the virtual machine.

Answer = No answer needed

-----

### Task 2

**q1.** What is the name of the service that lists Systems Internals as the manufacturer?

Answer = PsShutdown


**q2.** Whom is the Windows license registered to?

Answer = Windows User


**q3.** What is the command for Windows Troubleshooting?

Answer = C:\Windows\System32\control.exe /name Microsoft.Troubleshooting


**q4.** What command will open the Control Panel? (The answer is  the name of .exe, not the full path)

Answer = control.exe

-----

### Task 3

**q1.** What is the command to open User Account Control Settings? (The answer is the name of the .exe file, not the full path)

Answer = UserAccountControlSettings.exe

-----

### Task 4 

**q1.** What is the command to open Computer Management? (The answer is the name of the .msc file, not the full path)

Answer = compmgmt.msc


**q2.** At what time every day is the GoogleUpdateTaskMachineUA task configured to run?

Answer = 6:15 AM


**q3.** What is the name of the hidden folder that is shared?

Answer = sh4r3dF0Ld3r

-----

### Task 5

**q1.** What is the command to open System Information? (The answer is the name of the .exe file, not the full path)

Answer = msinfo32.exe


**q2.** What is listed under System Name?

Answer = THM-WINFUN2


**q3.** Under Environment Variables, what is the value for ComSpec?

Answer = %SystemRoot%\system32\cmd.exe


-----

### Task 6

**q1.** What is the command to open Resource Monitor? (The answer is the name of the .exe file, not the full path)

Answer = resmon.exe

-----

### Task 7

**q1.** In System Configuration, what is the full command for Internet Protocol Configuration?

Answer = C:\Windows\System32\cmd.exe /k %windir%\system32\ipconfig.exe


**q2.** For the ipconfig command, how do you show detailed information?

Answer = ipconfig /all

-----

### Task 8

**q1.** What is the command to open the Registry Editor? (The answer is the name of  the .exe file, not the full path)

Answer = regedt32.exe

-----












