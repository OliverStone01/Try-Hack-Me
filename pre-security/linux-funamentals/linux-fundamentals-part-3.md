# 🚪 Room: Linux fundamentals - part 3

## 🎯 Objectives
- Power-up your Linux skills and get hands-on with some common utilities that you are likely to use day-to-day!

## 🛠️ Tools Used
-

## 💬 Summary
- Terminal text editors
- General/useful utilities
- Processes 101
- Maintaining your system: automation
- Maintaining your system: Package management
- Maintaining your system: Logs

-----

## Notes

### Task 3 - Terminal text editors

#### Introducing terminal text editors

There are a few options that you can use. In this task we are going to look at `nano` and also `VIM`

#### Nano

To create a file using `nano` all you need to do is `nano filename`. Once nano has launched, you can begin entering or modiying the text. You can navigate each line using the `up` and `down` arrow keys.

Nano allows you to:
- Searching for text
- Copying and pasting
- Jumping to a line number
- Finding out what line number you are on

To use these features, you the `ctrl` key. 


#### VIM

VIM is much more advanced text editor. Some of VIM's benefits are:
- Customisable - you can modify the keyboard shortcuts
- Syntax highlighting - useful when writing code
- VIM works on all terminals
- Lots of resources.

-----

### Task 4 - General/useful utilities

#### Downloading files (Wget)

A fundamental feature of computing is the ability to transfwe files. For example, you may want to download a program, script, or even picture.

Let's take a look at `wget`. This allows us to download files from the web via HTTP. All we need to do is provide the address of the resource that we wish to download. Say we wanted to download a file named `myfile.txt`, that would look something like this:
```
wget https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt
```


#### Transferring files from your host - SCP (SSH)

`SCP` = Secure copy

SCP is a secure method of copying files. This command allows you to transfer files between two devices using SSH.

Working on a model of SOURCE and DESTINATION, SCP allows you to:
- Copy files & directories from your current system to a remote system
- Copy files & directories from a remote system to your current system

Provided that we know usernames and passwords for a user on your current system and a user on the remote system. For example, let's copy an example file from our machine to a remote machine:
```
Variable                             |  Value
- - - - - - - - - - - - - - - - - - -|- - - - - - - - - -
IP address of the remote system      |  192.168.1.30
- - - - - - - - - - - - - - - - - - -|- - - - - - - - - -
User on the remote system            |  ubuntu
- - - - - - - - - - - - - - - - - - -|- - - - - - - - - -
Name of the file on the local system |  important.txt
- - - - - - - - - - - - - - - - - - -|- - - - - - - - - -
Name to store the file on the remote |  transferred.txt
- - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```

With this information, let's craft our `scp` command:
```
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```

Lets now look at using `scp` to copy a file from a remote computer that we're not logged into:
```
Variable                                |  Value
- - - - - - - - - - - - - - - - - - - - | - - - - - - - - -
IP address of the remote system         |  192.168.1.30
- - - - - - - - - - - - - - - - - - - - | - - - - - - - - -
User on the remote system               |  ubuntu
- - - - - - - - - - - - - - - - - - - - | - - - - - - - - -
Name of the file on the remote system   |  documents.txt
- - - - - - - - - - - - - - - - - - - - | - - - - - - - - -
Name for storing the file on our system |  notes.txt
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```

This command will now look like:
```
scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt
```

#### Serving files from your host - WEB



-----

## Questions and Answers

### Task 1

**q1.** Let's proceed!

Answer = No answer needed

-----

### Task 2

**q1.** I've logged into the Linux Fundamentals Part 3 machine using SSH and have deployed the AttackBox successfully!

Answer = No answer needed

-----

### Task 3

**q1.** Create a file using Nano

Answer = No answer needed


**q2.** Edit "task3" located in "tryhackme"'s home directory using Nano. What is the flag?

Answer = THM{TEXT_EDITORS}

-----







