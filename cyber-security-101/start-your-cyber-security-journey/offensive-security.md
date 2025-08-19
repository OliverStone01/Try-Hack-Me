# 🚪 Room: Offensive Security Journey

## 🎯 Objectives
- Hack your first website (legally in a safe environment) and experience an ethical hacker's job.

## 🛠️ Tools Used
- Dirb
- 

## 💬 Summary
- What is Offensive Security?
- Your first hack
- Adding funds to the account

-----

## Notes

### Task 1 - What is Offensive Security?

"To outsmart a hacker, you need to think like one."

The core of `Offensive Security` involves breaking into computer systems, exploiting software bugs, and finding loopholes in applications to can unauthorised access. The goal is to understand the hackers tactics and enhance our system defences.


-----

### Task 2 - Starting the Lab

In this room, there is a prepared fake bank application called `FakeBank` that I must safely hack. 


-----

### Task 3 - Your first hack

#### Briefing

Our gial is to find a way to hack the `FakeBank` application to steal money. For that purpose, we have been provided with a bank account in the bank.

One of the easiest ways to try hack the application is by finding hidden features in the application. Sometimes, applications will expose sensitive functionality to users with secret URL's. 

To find hidden URL's, we can use a tool called `dirb`. This tool `Brute-forces` the URL's by taking a list of potential page names and testing one by one to see if they exist.


#### Using dirb to find Hidden website pages

Using dirb is simple. Using the terminal, write the following command followed by the website you want to check.
```
dirb http://fakebank.thm
```

Here is the output of that command.
```
ubuntu@tryhackme:~/Desktop$ dirb http://fakebank.thm 

-----------------
DIRB v2.22    
By The Dark Raver
-----------------

START_TIME: Thu Apr 17 16:29:52 2025
URL_BASE: http://fakebank.thm/
WORDLIST_FILES: /usr/share/dirb/wordlists/common.txt

-----------------

GENERATED WORDS: 4610      

---- Scanning URL: http://fakebank.thm/ ----
+ http://fakebank.thm/bank-deposit (CODE:200|SIZE:4663)                        
+ http://fakebank.thm/images (CODE:301|SIZE:179)           
-----------------
END_TIME: Thu Apr 17 16:29:59 2025
DOWNLOADED: 4610 - FOUND: 2
  
```

The first section of the output tells us the URL_BASE we scanned. It also shows the location of the wordlist file used by dirb. 

The lines starting with `+` are the results of the scan. In this example, dirb found 2 URLS.


-----

### Task 4 - Adding funds to your account

You should have found a secret page that allows you to add funds to a bank account. From this page, you should be able to add funds to your account using the bank account number.


-----

## Questions and Answers


### Task 1

**q1.** Which of the following options better represents the process where you simulate a hacker's actions to find vulnerabilities in a system?

**Answer =** Offensive Security

------

### Task 2

**q1.** What is your bank account number in the FakeBank web application?

**Answer =** 8881

-----

### Task 3

**q1.** Dirb should have found 2 hidden URLs. One of them is http://fakebank.thm/images. What is the other one?

**Answer =** http://fakebank.thm/bank-deposit

-----

### Task 4

**q1.** If your balance is now positive, a pop-up should appear with some green words in it. Input the green words as the answer to this question (all in uppercase).

**Answer =** BANK-HACKED

-----
