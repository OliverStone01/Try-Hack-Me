# 🚪 Room: Linux Fundamentals - part 1

## 🎯 Objectives
- Embark on the journey of learning the fundamentals of Linux. Learn to run some of the first essential commands on an interactive terminal.

## 🛠️ Tools Used
-

## 💬 Summary
- Introduction
- A Bit of Background on Linux
- Interacting With your First Linux Machine
- Running Your First few Commands
- Interacting With the Filesystem
- Searching for Files
- An Introduction to Shell Operators
- Conclusions & Summaries
- Linux Fundamentals Part 2

-----

## Notes

### Task 1 - Introduction

Welcome to the first part of the "Linux Fundamentals" room series. You're most likely using a Windows or Mac machine, both are different in visual design and how they operate. Just like Windows, IOS and MacOS, Linux is just another operating system and one of the most popular in the world powering smart cars, android devices, supercomputers, home appliances, enterprise servers, and more.

-----

### Task 2 - A Bit of Background on Linux

#### Where is Linux used

It's fair to say that linux is a lot more intimidating to approach than Operating Systems (OS) such as Windows. Both variants have their own advantages and disadvantages. For example, Linux is considerably much more lightweight and you'd be suprised to know that there's a good chance you've used Linux in some form or another every day! Linux powers things like:
- Websites you visit
- Car entertainment/control panels
- Point of sale (PoS) systems such as checkout tills.
- Critical infrastructure such as traffic controllers.

#### Flavours of Linux

The name `Linux` is an umbrella term for multiple OS's that are based on UNIX (another operating systems). Thanks to Linux being open-source, varients of Linux come in all shapes and sizes - suited best for what the system is being used for.

For example, Ubuntu & Debian are some of the more commonplace distributions of Linux because it is so extensive. For example, you can use Ubuntu as a server (website & web application) or a desktop.

Ubuntu servers can run on systems with only 512mb of RAM.

-----

### Task 3 - Interacting with your first Linux machine

This room has a Ubuntu Linux machine that you can interact with in your browser.

Press "Start Machine" to interact with your own Linux machine.

-----

### Task 4 - Running your first few commands

As we spoke about before, a large reason you may want to use Ubuntu or any Linux OS is because of how lightweight they can be. This does come with some disadvantages. For example, most of the OS's dont have a GUI (graphical user interface), this is also known as a desktop enviroment that the user can use to interact with the machine vistually. Instead, the user needs to use whats called a `Terminal`.

The `Terminal` is a text-based way of controling the device. Let's look at some of the commands used with the `Terminal` and lets look at the command line:
```
// Command line
tryhackme@linux1:~$ enter commands here
```

Lets now look at some basic functions like navigating to files, outputting their contents and make files:
```
Command    |  Description
- - - - - -|- - - - - - - - - - - - - - - - - - - - - - - - -
echo       | Output any text provided
- - - - - -|- - - - - - - - - - - - - - - - - - - - - - - - - 
whoami     | Find out what user we're currently logged in as.
- - - - - -|- - - - - - - - - - - - - - - - - - - - - - - - -
```

Here is some examples of the echo commands:
```
tryhackme@linux1:~$ echo Hello
Hello

tryhackme@linux1:~$ echo "Hello Friend!"
Hello Friend!
```

As you can see above, if you want to `echo` one word then you don't need the double quotes like you do when you use multiple words.

`whoami` can be used to find the current username we are logged in as:
```
tryhackme@linux1:~$ whoami
```

-----

### Task 5 - Interacting with the filesystem

#### Interacting with the filesystem

Being able to navigate the machine that you are logged into without needing a desktop enviroment is important.
```
Command  |  Full name
- - - - -|- - - - - - - - - - - - - -
ls       |  Listing
- - - - -|- - - - - - - - - - - - - -
cd       |  Change directory
- - - - -|- - - - - - - - - - - - - -
cat      |  Concatenate
- - - - -|- - - - - - - - - - - - - -
pwd      |  Print Working Directory
- - - - - - - - - - - - - - - - - - -
```

#### Listing files in our current directory(s)

Before we can do anything such as finding out the contents of any files or folders, we need to know what exists in the first place. This can be done using the `ls` command:
```
tryhackme@linux1:~$ ls
'Important Files' 'My Documents' Notes Pictures
```

The above shows the following directories and folders:
- Important Files
- My Documents
- Notes
- Pictures

Instead of needing to go into the next directory to see whats in it, you can do `ls Pictures` for example.


#### Changing out current directory (cd)

Now we know what exists inside of a directory, we can enter that directory by using the `cd` command. Say we wanted to open the Pictures directory, we would do `cd Pictures`:
```
tryhackme@linux1:~$ cd Pictures
tryhackme@linux1:~/Pictures$
```

As you can see by the `/Pictures`, we are now inside the pictures directory.


#### Outputting the contents of a file (cat)

To view the contents of a file, we can use the `cat` command:
```
tryhackme@linux1:~/Documents$ ls
todo.txt
tryhackme@linux1:~/Documents$ cat todo.txt
Here's something important for me to do later!
```

You can also use cat from outside of the directory, for example:
```
tryhackme@linux1:~$ cat /Documents/todo.txt
Here's something important for me to do later!
```

#### Finding out the full path to our current working directory (pwd)

It is very easy to lose track of where you are on the filesystem. To combat this, we can use the `pwd` to print the working directory.
```
tryhackme@linux1:~/Documents$ pwd
/home/ubuntu/Documents
```

-----

### Task 6 - Searching for files

To save time, we can search an entire system by using the `find` command.

#### Using find

Here is a list of directories available:
```
tryhackme@linux1:~$ ls
Desktop Documents Pictures folder1
```

Assuming we know the name of the file (in this case `passwords.txt`). We can use `find` liek this:
```
tryhackme@linux1:~$ find -name passwords.txt
./folder1/passwords.txt
```

What if you don't know the name of the file? Or maybe you want to seach for all files that have the extention of `.txt`. What we can do is use `*` as a placeholder like this:
```
tryhackme@linux1:~$ find -name *.txt
./folder1/passwords.txt
./Documents/todo.txt
```

### Using Grep

The `grep` command allows us to search the contents of files for specific values that we are looking for.

For this example, we are first going to use the command `wc` to count the amount of entries in `access.log`.
```
// Using wc to count the number of entries in access.log
tryhackme@linux1:~$ wc -l access.log
244 access.log
```

We are now going to use `grep` to search the contents of the file for everything the ip address `81.143.211.90` has visited.
```
tryhackme@linux1:~$ grep "81.143.211.90" access.log
81.143.211.90 - - [25/Mar/2021:11:17 + 0000] "GET / HTTP/1.1" 200 417 "-" "Mozilla/5.0 (Linux; Android 7.0; Moto G(4))"
```

-----

### Task 7 - An introduction to shell operators

Here are a few operators:
```
Symbol/Operator  |  Description
- - - - - - - - -|- - - - - - - - - - - - - - - - - - - - - -
&                |  Run commands in the background
- - - - - - - - -|- - - - - - - - - - - - - - - - - - - - - -
&&               |  Combine multiple commands together
- - - - - - - - -|- - - - - - - - - - - - - - - - - - - - - -
>                |  Redirector - use the output as the input
- - - - - - - - -|- - - - - - - - - - - - - - - - - - - - - -
>>               |  Same as > but appends instead of replacing
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```

#### Operator &

This allows us to run commands in the background. For example, say we want to copy a large file. This would take a long time and leave us unable to do anything else until its complete.

Using the `&` operator allows us to execute the command and let it run in the background while we execute other commands.


#### Operator &&

We can use `&&` to run a list of commands. For example `command1 && command2`. It is worth noting that `command2` will only run if `command1` was successful.


#### Operator >

This operator is what's known as an output redirector. What this means is we take the output of one command and use that elsewehere.

What we can do, for example, is create a file with the message inside as "hey". We can use the echo and the `>` operator to redirect the result of echo into the file:
```
tryhackme@linux1:~$ echo hey > welcome
```

#### Operator >>

This operator is also a redirector like the previous operator (>). But, what makes this operator diffrent is that rather than overwritting the current data in the file each time, we can use this operator to append to the file:
```
tryhackme@linux1:~$ echo hello >> welcome
```

-----

## Questions and Answers

### Task 1 

**q1.** Let's get started!

Answer = No answer needed

-----

### Task 2

**q1.** Research: What year was the first release of a Linux operating system?

Answer = 1991

-----

### Task 3

**q1.** I've deployed my first Linux machine!

Answer = No answer needed

-----

### Task 4

**q1.** If we wanted to output the text "TryHackMe", what would our command be?

Answer = echo TryHackMe


**q2.** What is the username of who you're logged in as on your deployed Linux machine?

Answer = tryhackme

-----

### Task 5

**q1.** On the Linux machine that you deploy, how many folders are there?

Answer = 4


**q2.** Which directory contains a file? 

Answer = folder4


**q3.** What is the contents of this file?

Answer = Hello World


**q4.** Use the cd command to navigate to this file and find out the new current working directory. What is the path?

Answer = /home/tryhackme/folder4

-----

### Task 6

**q1.** Use grep on "access.log" to find the flag that has a prefix of "THM". What is the flag?

Answer = THM{ACCESS}


**q2.** And I still haven't found what I'm looking for!

Answer = No answer needed

-----

### Task 7

**q1.** If we wanted to run a command in the background, what operator would we want to use?

Answer = &


**q2.** If I wanted to replace the contents of a file named "passwords" with the word "password123", what would my command be?

Answer = echo password123 > passwords


**q3.** Now if I wanted to add "tryhackme" to this file named "passwords" but also keep "passwords123", what would my command be

Answer = echo tryhackme >> passwords


**q4.** Now use the deployed Linux machine to put these into practice

Answer = No answer needed

-----

### Task 8

**q1.** I'll have a play around!

Answer = No answer needed

-----

### Task 9

**q1.** Terminate the machine deployed in this room from task 3. 

Answer = No answer needed


**q2.** Join Linux Fundamentals Part 2!

Answer = No answer needed




