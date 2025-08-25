# 🚪 Room: Linux fundamentals - part 3

## 🎯 Objectives
- Power-up your Linux skills and get hands-on with some common utilities that you are likely to use day-to-day!

## 🛠️ Tools Used
- Nano
- SCP
- http.server

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

Ubuntu machines come pre-packaged with python3. Python provides a lightweight and easy-to-use module called "HTTPServer". This module turns your computer into a quick and easy web server that you can use to serve your own files, where thry can then be downloaded by another computer using the commands `curl` and `wget`.

The server will serve the files from the directory where you run the command. To start the module, all you need to do is run `python3 -m http.server` in the terminal you wish to use. 

In the below example, we are serving from a directory called `webserver`, which has a single file names `file`.
```
tryhackme@linux3:/webserver# python3 -m http.server
Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
```

Now we can use `wget` to downlaod the file using the MACHINE_IP address and the name of the file, and the port that the server is running on:
```
tryhackme@mymachine:~# wget http://MACHINE_IP:8000/myfile
```

One issue with this module is that you have no way of indexing. This means you must know the name and location of the file you wish to use. This is why `updog` is more commonly used. `updog` is a more advanced yet lightweight webserver.

-----

### Task 5 - Processes 101

Processes are the programs that are running on your machine. They are managed by the kernal, where each process has an ID associated with it, known as a `PID` (Process ID). The PID increments for the order in which the process starts. For example, the 60th process will have a PID of 60.

#### Viewing Processesr

We can use the `ps` command to provide a list of the running processes as our user's session and some additional information such as it's status code, the session that is running it, how much usage time of the CPU it is using, and the name of the actual program or command that is being executed.

To see other processes run by other users and those that don't run from a session (System processes), all we need to do is provide `aux` to the `ps` command like this `ps aux`.

The `top` command gives you real-time statistic about the processes running on your system instead of a one-time view. To refresh the current rows, you can use the arrows.


#### Managing processes

You can send signals to terminate processes by using the `kill` command, followed by the PID numbers. For example, `kill 1337`. Here are some other signals we can send tot a process:

- SIGTERM - Kill the process, but allow it to do some cleanup tasks first.
- SIGKILL - Kill the process - doesn't do any cleanup after
- SIGSTOP - Stop/Suspend a process


#### How do processes start?

The Operating system uses `namespaces` to split up the resources available on the computer to processes. Each slice provides a certain amount of processing power for those processes.

Namespaces are great for security as it is a way of isolating processes from another - only those in the same namespace will be able to see each other.


#### Getting Processes/Services to start on boot

Some applications can be started on the boot of the system. For example, web servers, database servers, or file transfer servers. this software is often critical.

In this example, we're going to be tell the system to boot the apache web server manually and boot apache2 on boot.

To do this, we need to use the `systemctl` command. This command allows us to interact with the `systemd` process/daemon. `systemctl` uses the following formatting: `systemctl [option] [service]`.

To start on boot we would do `systemctl start apache2`.
To stop, we can do `systemctl stop apache`.

There are four options we can do:
- Start
- Stop
- Enable
- Disable


#### An introduction to backgroup and foregrounding in Linux

Processes can run in two states: In the background and in the foreground. For example, running echo in the terminal would be classed as a foreground process. 

To run a process in the background, we need to add the `&` operator like this:
```
root@linux3~# echo "Hi THM" &
[1] 16889
root@linux3:~# Hi THM
```

As you can see, when the command is run, we are given a process number as the command is run in the background. Once it's complete processing, the output of echo is printed to the terminal.

This is great for copying files as it allows us to work on other things in the mean time.

We can also do the same with scritps by using `ctrl + z` to background a process.


#### Foregrounding a process

Now that we know how to put a process into the background. we can confirm the process is running using the `ps aux` command. To then bring the process back to the foreground, we can use the `fg` command.

-----

### Task 6 - Maintaining your system: Automation

Users may want to schedule an action or task to take place after the systems has booted. To do this, we are going to be looking at the `cron` process, more spacifically, how we can interact with it via `crontabs`. `crontab` is one of the processes started during boot which is responsible for facilitating and managing cron jobs.

A crontab is a special file with formatting that is recognised by the `cron` process to execute each line. Crontab requires 6 specific values:
```
Value  |  Description
- - - -|- - - - - - - - - - - - - - - - - - - - - - - - - -
MIN    |  What minute to execute at
- - - -|- - - - - - - - - - - - - - - - - - - - - - - - - -
HOUR   |  What hour to execute at
- - - -|- - - - - - - - - - - - - - - - - - - - - - - - - -
DOM    |  What day of the month to execute at
- - - -|- - - - - - - - - - - - - - - - - - - - - - - - - -
MON    |  What month of the year to execute at
- - - -|- - - - - - - - - - - - - - - - - - - - - - - - - -
DOW    |  What day of the week to execute at
- - - -|- - - - - - - - - - - - - - - - - - - - - - - - - -
CMD    |  The actual command that will be executed
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```

Say you wanted to back up your files, specifically you wish to back up `Documents` inside of `cmnatic` every 12 hours. We would do the following:
```
0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/
```

When using crontabs, we can use the placeholder `*` for any information we don't want to provide. Say we don't care what day, we can use `*` in that field and it will ignore that time frame.

There are some good `Crontab Generators` out there you can use.

Crontabs can be edited by using `crontab -e` where you can selector the editor like Nano.


-----

### Task 7 - Maintaining your system: package management

#### Introducing packages & software repos

When developers wish to submit software to the community, they submit it to an `apt` repository. If approved, their programs and tools will be released. This is where two of Linux's features really shine: User accessibility and the merit of open source tools.

Addition repositories can be added by using `apt-add-repository` command.


### Managing your repositories (adding and removing)

`apt` command is part of the package management. `apt` contains a whole suite of tools that allow us to manage the packages and sources of software.

The benefits of using `apt` is that whenever we update our system, it checks for updates and does the updates as its inside of the same repository.

In the following example, we are going to add the text editor `Sublime Text` to our Ubuntu machine. When adding software, the integrity of what we download is guaranteed by the use of what is called `GPG` (Gnu Privacy Guard) keys. These keys are essentially a safety check from the developers. If the keys do not match up to what your system trusts and what the developers used, then the software will not be downloaded.

To start, we need to add the GPG key for the developers of `Subline Text 3`.

1. Download the GPG key and use apt-key to trust it:
```
wget -q0 -https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```

2. Now we can add Sublime Text 3 repository to our apt sources list. A good practice is to have a seperate file for every different community/3rd party repository that we add.

2.1. Create a file named `sublime-text.list` in `/etc/apt/source.list.d` and enter the repository information like this:
```
root@Linux3:/etc/apt/sources.list.d# touch sublime-text.ist
```

2.2. Now use Nano to add & save the Sublime Text 3 repository into the newly created file:
```
deb https://download.sublimetext.com/ apt/stable/
```

2.3. After adding this entry, we need to update apt to recognise this new entry - This is done using the `apt update` command.

2.4. Once updated, we can proceed to install the software that we have trusted and added to apt using `apt install sublime-text`.


To remove a package, we use `add-apt-repository --remove ppa:PPA_Name/ppa`. Once removed, we can use `apt remove [software-name-here]` i.e. `apt remove sumblime-text`.

-----

### Task 8 - Maintaining your system: logs

Located in the `/var/log` directory, these files and folders contain logging information for applications and services running on your system. The operating system has become pretty good at automatically managing these logs in a process that is known as `rotating`.

Some logs that are great at monitoring the health of your system and protecting it are:
- apache2: web server
- fail2ban.log: monitor attempted brute forces
- ufw.log: used as a firewall

The logs for services such as a web server contain information about every single request - allowing developers and administrators to diagnose performance issues or investigate an intruders activity. For example, the two types of log files below that are below are of interest:
- Access log
- error log

These are logs that store information about how the OS is running itseld and actions that are performed by users, such as authentication attempts.

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

### Task 4

**q1.** Ensure you are connected to the deployed instance (MACHINE_IP)

Answer = No answer needed


**q2.** Now, use Python 3's "HTTPServer" module to start a web server in the home directory of the "tryhackme" user on the deployed instance.

Answer = No answer needed


**q3.** Download the file http://MACHINE_IP:8000/.flag.txt onto the TryHackMe AttackBox. Remember, you will need to do this in a new terminal.

What are the contents?

Answer = THM{WGET_WEBSERVER}


**q4.** Create and download files to further apply your learning -- see how you can read the documentation on Python3's "HTTPServer" module. 

Use Ctrl + C to stop the Python3 HTTPServer module once you are finished.

Answer = No answer needed

-----

### Task 5

**q1.** Read me!

Answer = No answer needed


**q2.** If we were to launch a process where the previous ID was "300", what would the ID of this new process be?

Answer = 301


**q3.** If we wanted to cleanly kill a process, what signal would we send it?

Answer = SIGTERM


**q4.** Locate the process that is running on the deployed instance (MACHINE_IP). What flag is given?

Answer = THM{PROCESSES}


**q5.** What command would we use to stop the service "myservice"?

Answer = systemctl stop myservice


**q6.** What command would we use to start the same service on the boot-up of the system?

Answer = systemctl enable myservice


**q7.** What command would we use to bring a previously backgrounded process back to the foreground?

Answer = fg

-----

### Task 6

**q1.** Ensure you are connected to the deployed instance and look at the running crontabs.

Answer = No answer needed


**q2.** When will the crontab on the deployed instance (MACHINE_IP) run?

Answer = @reboot

-----

### Task 7

**q1.** Since TryHackMe instances do not have an internet connection...this task only requires you to read through the material.

Answer = No answer needed

-----

### Task 8

**q1.** Look for the apache2 logs on the deployable Linux machine

Answer = No answer needed


**q2.** What is the IP address of the user who visited the site?

Answer = 10.9.232.111


**q3.** What file did they access?

Answer = catsanddogs.jpg

-----

### Task 9

**q1.** Terminate the machine deployed in this room from task 2. 

Answer = No answer needed


**q2.** Continue your learning in other Linux-dedicated rooms

Answer = No answer needed

-----






