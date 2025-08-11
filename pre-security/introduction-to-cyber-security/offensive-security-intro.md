# 🚪 Room: Offensive Security Intro

## 🎯 Objectives
- Hack your first website (legally in a safe environment) and experience an ethical hacker's job.

## 🛠️ Tools Used
- Virtual machines
- `DirB` = brute-forces URLs by taking a list of potential page names and testing to see if they exist.

## 💬 Summary
- Used `DirB` to brute-force a bank application to see what hidden pages the bank had on its site.
- Used the link to add funds to the bank account.

-----
## Notes

### Task 1

The core of "Offensive Security" is breaking into computer systems, exploiting software bugs, and finding loopholes in an application to gain unauthorised access.

The goal is to understand hacker tactics and improve system defence.

-----

### Task 2

We use virtual machines to create simulated environments.

In this room, there is a fake bank application (FakeBank). 

<img fakebank src="/pre-security/introduction-to-cyber-security/assets/fakebank.png" alt="Fakebank homepage" style="width:300px">

Once I loaded the bank, I could see information about a bank account. Question 2 asked for the bank account number that was in plain text on the account.

-----

### Task 3

Goal is to hack into the FakeBank application and steal money. All I have is a bank account.

Need to find hidden features in the application. To do this, we are using a tool called `DirB`.

`DirB` brute-forces URLs by taking a list of potential page names and testing to see if they exist.

`DirB` is executed from the computer’s terminal. All you need to do is write `DirB` followed by the URL of the website.
```
dirb http://fakebank.thm
```
Output (taken from task):
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
Breakdown:
- The first section tells us the `URL_BASE`. The url we gave `DirB`, the location of the wordlist, and common page names that are tested.

- The results with `+` are pages found.

-----

### Task 4:

Following the link found in Task 3, it took me to a service on the bank where I could add funds to an account by inputting the account number and amount to deposit.

<img src="/pre-security/introduction-to-cyber-security/assets/add-funds.png" alt="Add funds on fake bank" style="width:300px">

-----

## Questions and Answers

### Task 1

**q1.** Which of the following options better represents the process where you simulate a hacker's actions to find vulnerabilities in a system?

- Offensive security
- Defensive security

Answer = Offensive security

-----

### Task 2

**q1.** What is your bank account number in the FakeBank web application?

Answer = 8881

-----

### Task 3

**q1.** Dirb should have found 2 hidden URLs. One of them is `http://fakebank.thm/images`. What is the other one?

Answer = http://fakebank.thm/bank-deposit

-----

### Task 4

**q1.** If your balance is now positive, a pop-up should appear with some green words in it. Input the green words as the answer to this question (all in uppercase):

Answer = BANK-HACKED
