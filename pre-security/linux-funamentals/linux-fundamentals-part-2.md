# 🚪 Room: Linux fundamentals - part 2

## 🎯 Objectives
- Continue your learning Linux journey with part two. You will be learning how to log in to a Linux machine using SSH, how to advance your commands, file system interaction.

## 🛠️ Tools Used
-

## 💬 Summary
- Introduction
- Accessing Linux machines using SSH
- Introduction to Flags and Switches
- Filesystem interaction continued
- Permissions 101
- Commom directories
- Conclusions and summaries

-----

## Notes

### Task 1 - Introduction

In this room we will:
- Unlocking the potential of your first few commands by introducing you to using flags and arguments.
- Advancing knowledge of the filesystem to perform some more useful commands such as copying and moving files.
- Discovering how access to files and folders is managed and how we can determine our access.
- Running your first few scripts and executables.

-----

### Task 2 - Accessing your Linux machine using SSH

Today, we are going to be looking at a protocol called `SSH`.

`SSH` = Secure Shell

It is the common method for connecting to and interacting with the command line of a remote Linux machine.

#### What is SSH and how does it work?

SSH is a protocol between devices in an encrypted form. Using cryptography, any input we send in human-readable format is encrypted for travelling over a network. It is then unencrypted once it reaches the remote machine.


#### Using SSH to Login to your Linux machine

The syntax to use SSH is very simple:
1. The IP address of the remote machine
2. Correct credentials to a valid account to login with on the remote machine.

The command to begin the connection is the username@IP address:
```
ssh tryhackme@10.10.10.10
```

Once executed, you will then be asked to trust the device (Y/N). Then you will be asked for the password thats protecting the account.

Once we are connected, any commands we execute will be executed on the remote machine.

-----

### Task 3 - Introduction to Flags and Switches

A majority of commands allow for arguments to be provided. these arguments are identified by a hyphen and a cetrain keyword known as flags or switches.

For example, when using the `ls` command, we can see the directories and files in the working directory. But sometimes files can be hidden. What we can do is use the `-a` argument (short for `--all`) to display any hidden folders.

Files and folders can be hidden by placing a `.` at the begining:
```
tryhackme@linux2:~$ ls -a
.hiddenfolder folder1
```

You can also use the `--help` option to find more commands that will be accepted. This is what is called a `man` page (short for manual).

#### The Man(ual) page

These pages are a great souce of information for both system commands and applications available on Linux machines. To access this documentation, we can use the `man` command. For example, if we wanted to see the documentation for `ls` we can do the following:
```
tryhackme@linux2:~$ man ls
LS(1)        User commands

NAME
...
```

-----

### Task 4 - Filesystem interaction continued

We are going to look at some more commands that will allow us to:
- Create files and folders
- Move files and folders
- Delete files and folders

```
Command  |  Full name       |  Purpose
- - - - -|- - - - - - - - - |- - - - - - - - - - - - - - -
touch    |  Touch           |  Create file
- - - - -|- - - - - - - - - |- - - - - - - - - - - - - - -
mkdir    |  Make directory  |  Create a folder
- - - - -|- - - - - - - - - |- - - - - - - - - - - - - - -
cp       |  Copy            |  Copy a file or folder
- - - - -|- - - - - - - - - |- - - - - - - - - - - - - - - 
mv       |  Move            |  Move a file or folder
- - - - -|- - - - - - - - - |- - - - - - - - - - - - - - - 
rm       |  Remove          |  Remove a file or folder
- - - - -|- - - - - - - - - |- - - - - - - - - - - - - - - 
file     |  File            |  Determine the type of a file
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
```

#### Creating files and folders

Creating files and folders on Linux is very simple. First, lets create a file. All we need to do is use `touch note`. This will create a blank file called `note`.

To create a folder it is very similar. Instead of using touch we use `mkdir` instead (short for make directory) like this `mkdir mydirectory`.


#### Removing files and folders (rm)

To remove a file, all you need to do is `rm filename`. To remove a directory, you need to do the same but provide the `-R` switch alongside the name of the directory like `rm -R mydirectory`.


#### Copying and moving files and folders (cp, mv)

`cp` takes two arguements:
1. The name of the existing file
2. The name we wish to assign to the new file when copying

for example `cp note note2`.

Moving a file also takes two arguements. However, rather than copying and/or creating a new file, `mv` will merge or modify the second file that we provide as an arguement. Not only can you use `mv` to move a file to a new folder, but you can also use `mv` to rename a file or folder. For ecample, we can rename the file `note2` to note3` by doing the following:
```
tryhackme@Linux2:~$ mv note2 note3
```


#### Determining file type

What often is misleading and often catches people out is making assumptions about the types that files are. Files usually have whats known as extensions to make this easier. For example, a text file will have the extention of `.txt`. 

If you are unsure about what tyoe the file is you can use the `file` command. like this:
```
tryhackme@Linux2:~$ file note
note: ASCII text
```

-----

### Task 5 - Permissions 101

As you may know, certain users cannot access certain files or folders. What we can use is the `ls` command with the `-l` flag that will display what we are able to do with the file and much more:
```
tryhackme@linux2:~$ ls -lh
-rw-r--r-- 1 cmnatic cmnatic 0 Feb 19 10:37 file1
-rw-r--r-- 8 cmnatic cmnatic 0 Feb 19 10:37 file2
```

These columns are very important in determining certain characterisitcs of a file or folder and whether we have access or not. There are three types of premisions:
- Read
- Write
- Execute

#### Briefly: The diffrences between users & groups

With Linux, permissions can be so granular, although a user technically owns a file, if the permissions have been set, then a group of users can also have either the same or a diffrent set of permissions to the exact same file without effecting the file ownder itself.


#### Switching between users

Switching between users on a Linux is easy thanks to the `su` command. Unless you are the root user (or using root permissions through sudo), then you are required to know two things to facilitate this transition of user accounts:
- The user we wish to switch to
- The user's password

The `su` command takes a couple of switches that may be relevance. For example, executing a command once you log in or specifying a specific shell to use.

By providing the `-l` switch to the `su` command, we can start a shell that is much more similar to the actual user logging into the system - we inherit a lot more properties of the new user, i.e., enviroment variables and the likes.

-----

### Task 6 - Common directories

#### /etc

This root directory is one of the most important root directories on your system. The `etc` folder is a commonplace location to store system files that are used by your operating system.


#### /var

this directory (short for `variable` data, is one of the main root folders. This folder stores data that is frequently accessed or written by services or applications running on the system.


#### /root

This folder is the home for the `root` system user. 


#### /tmp

This root directory is volitile and us used to store data that is only needed to be accessed once or twice. Similarly to the memory on your computer, once the computer has been restarted, the contents of this folder are cleared out.

-----

## Questions and Answers

### Task 1 

**q1.** Let's proceed!

Answer = No answer needed

-----

### Task 2

**q1.** I've logged into the Linux Fundamentals Part 2 machine using SSH!

Answer = No answer needed

-----

### Task 3

**q1.** Explore the manual page of the ls command

Answer = No answer needed


**q2.** What directional arrow key would we use to navigate down the manual page?

Answer = Down


**q3.** What flag would we use to display the output in a "human-readable" way?

Answer = -h

-----

### Task 4

**q1.** How would you create the file named "newnote"?

Answer = touch newnote


**q2.** On the deployable machine, what is the file type of "unknown1" in "tryhackme's" home directory?

Answer = ASCII text


**q3.** How would we move the file "myfile" to the directory "myfolder" 

Answer = mv myfile myfolder


**q4.** What are the contents of this file?

Answer = THM{FILESYSTEM}


**q5.** Continue to apply your knowledge and practice the commands from this task.

Answer = No answer needed

-----

### Task 5

**q1.** On the deployable machine, who is the owner of "important"?

Answer = user2


**q2.** What would the command be to switch to the user "user2"?

Answer = su user2


**q3.** Now switch to this user "user2" using the password "user2"

Answer = No answer needed


**q4.** Output the contents of "important", what is the flag?

Answer = THM{SU_USER2}

-----

### Task 6

**q1.** Read me!

Answer = No answer needed


**q2.** What is the directory path that would we expect logs to be stored in?

Answer = /var/log


**q3.**What root directory is similar to how RAM on a computer works?

Answer = /tmp


**q4.** Name the home directory of the root user 

Answer = /root


**q5.** Now apply your learning and navigate through these directories on the deployed Linux machine.

Answer = No answer needed

-----

### Task 7

**q1.** Proceed to the next task to continue your learning

Answer = No answer needed

-----

### Task 8

**q1.** Terminate the machine from task 2!

Answer = No answer needed


**q2.** Join Linux Fundamentals Part 3!

Answer = No answer needed

-----



