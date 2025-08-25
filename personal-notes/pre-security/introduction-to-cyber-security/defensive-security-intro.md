# 🚪 Room: Defensive Security Intro

## 🎯 Objectives
- Introduction to defensive security and related topics, such as Threat Intelligence, SOC, DFIR, Malware Analysis, and SIEM.

## 🛠️ Tools Used
- IP scanner

## 💬 Summary
- Defensive security
- Security Operations Center (SOC)
- Threat intelligence
- Digital Forensics and incident response (DFIR)
- Incident Response
- Malware Analysis
- Simulating a SIEM

-----

## Notes:

### Task 1:

Defensive security (**Blue Team**) is concerned with two main tasks:
1. Preventing intrusions from occurring.
2. Detecting intrusions when they occur and responding properly.

Some of the tasks related to defensive security include:
- **User cyber security awareness**:  
  Training users to help protect against attacks.
- **Documenting and managing assets**:  
  We need to know the systems and devices to be able to manage and protect them.
- **Updating and patching systems**:  
  Ensuring that computers, servers, and network devices are correctly updated and patched to prevent attacks against known vulnerabilities.
- **Setting up preventative security devices**:  
  Firewalls & IPS (Intrusion Prevention Systems)
- **Setting up logging and monitoring devices**:  
  If a new unauthorised device appears on the network, you want to be able to see it.

We will also look at:
- Security Operations Center (**SOC**)
- Threat Intelligence
- Digital Forensics and Incident Response (**DFIR**)
- Malware Analysis

-----

### Task 2:

**Security Operations Center (SOC):**  
A team of cybersecurity professionals that monitors the network and it's systems to detect malicious cybersecurity events.
    
Main Interests are:
- **Vulnerabilities**:  
  Fixing vulnerabilities by installing updates or patches.
- **Policy violations**:  
  A set of rules is required to protect the network and systems.
- **Unauthorised activity**:  
  When a password and username are stolen by an attacker, this must be fixed as soon as possible.
- **Network intrusions**:  
  Can occur when a user clicks on a malicious link or an attacker exploits a public server.

Threat Intelligence:  
In this context, intelligence refers to information you gather about actual and potential enemies. A threat is any action that can disrupt or adversely affect a system or steal data. 

Examples of adversaries:  
- **Nation State**:  
  Government run hackers for political reasons.
- **Ransomware group**:  
  Intended to lock down systems for a ransom.

The three stages of data collection:
- **Collecting data**:  
  from local sources like network logs and public sources like forums.
- **Processing data**:  
  Reformatting the data for better analysis.
- **Analysing Data**:  
  Find information about the attackers and their motives. Create a list of actionable steps.


**Digital Forensics and incident response (DFIR)**
Digital forensics is about analysing evidence of an attack and the attackers. Including intellectual property theft, cyber espionage, and possession of unauthorised content.

Focus areas are:
- **File System**:  
  Analysing a `digital forensics image` (low-level copy) of a system's storage which reveals installed programs, created files, partially overwritten files, and deleted files.
- **System memory**:  
  Analysing a `digital forensics image` (low-level copy) of a system's memory as an attacker may run their malicious programme in memory without saving it to the disk.
- **System logs**:  
  Logs provide information about everything that happened on a system. Even if the attacher tries to clear their traces.
- **Network logs**:  
  These logs of network packets can help answer questions about whether an attack is occurring.


**Incident Response**
Refers to a data breach or a cyber attack. In some cases it can be something less critical, such as:
- Misconfiguration
- Intrusion attempts
- Policy violation

Examples of cyber attacks:
- An attacker making the Network or System inaccessible.
- Defacing (changing) the public website.
- Data breach (stealing data)

The aim of an `Incident Response` is to reduce damage and recover in the shortest time possible. Ideally, you should have a developed plan ready.

The four major phases of incident response are:
- **Preparation**:  
  A team trained and ready to handle incidents.
- **Detection and Analysis**:  
  Using tools to detect and analyse threats.
- **Containment, Eradication, and recovery**:  
  Detect it, stop it from affecting other systems, eliminate it, and recover the affected systems.
- **Post-incident Activity**:  
  After a successful recovery, a report is produced, and the lessons learned are shared to prevent future incidents.

<img src="/pre-security/introduction-to-cyber-security/assets/incident-response-diagram.png" alt="Incident response diagram" style="width:400px">

**Malware Analysis**  
`Malware` = Malicious software.

Software refers to programs, documents, and files you can save on a disk or send over the network.

Some malware types:
- **Virus**:  
  Code that attaches itself to a programme. Designed to spread from one device to another. It works by altering, overwriting, and deleting files. Damage ranges from slowing machines to making them unusable.
- **Trojan Horse**:  
  A programme that displays itself as something a user would want, but hides a malicious function underneath.
- **Ransomeware**:  
  A malicious programme that encrypts the user's files, seeking ransom payment to unlock them again.

Malware analysis use different means to learn about malicious programs:
- **Static analysis**:  
  Inspecting the programme without running it. Usually requires knowledge of assembly language.
- **Dynamic analysis**:  
  Running the malware in a controlled environment and monitoring its activities.

-----

### Task 3

**The Scenario**
Pretend you are a SOC analyst responsible for protecting a bank. The bank's SOC uses a SIEM tool.

`SIEM` = Security Information and Event Management

The SIEM tools gather security-related information and events from various sources and present them in a dashboard. If it finds something suspicious, it will generate an alert.

Sometimes the alerts are not malicious. It is up to the analyst to investigate which one is harmful. For example, multiple failed login attempts. It is suspicious, but is also quite common.

An alert might be related to connections from unknown IP addresses.

`IP address` = Internet Protocol address.

An IP address is like a home address for you computer on the internet. It tells other computers where to send the information you request. An unknown IP could mean someone new is connecting or someone is attempting unauthorised access.

**Simulating a SIEM**  

I've loaded the site and it is a SIEM dashboard. The instructions say "Inspect the alerts in your SIEM dashboard. Find the malicious IP address from the alerts, make a note of it, and then click on the alert to proceed."

<img src="/pre-security/introduction-to-cyber-security/assets/siem-dashboard.png" alt="SIEM Dashboard" style="width:300px">

Below the charts is aa "Alert Log". Second log down, the message reads "Unauthorised connection attempt detected from IP address 143.110.250.149 to port 22"

After clicking on this log, I'm taken to another set of instructions. "There are websites on the Internet that allow you to check the reputation of an IP address to see whether it's malicious or suspicious."

After entering the IP address, the result comes back as "Malicious".

The next instructions recommend two open-source tools to do searches like this:
- AbuseIPDB
- Cisco Talos Intelligence

Now the instructions are telling me "we need to escalate it to a staff member!"

The next task is choosing who to escalate this event to:
- Sales Executive
- Security Consultant
- Information Security Architect
- SOC team lead (Correct Answer)

Now we have permission to block the malicious IP on the firewall using a block list. After entering the IP address and submitting, the final answer is revealed.


-----

## Questions and Answers

### Task 1:

**q1.** Which team focuses on defensive security?

Answer: Blue Team

-----

### Task 2:

**q1.** What would you call a team of cyber security professionals that monitors a network and its systems for malicious events?

Answer = Security Operations Center


**q2.** What does DFIR stand for?

Answer = Digital Forensics and Incident Response


**q3.** Which kind of malware requires the user to pay money to regain access to their files?

Answer = Ransomware

-----

### Task 3:

**q1.** What is the flag that you obtained by following along?

Answer = THM{THREAT-BLOCKED}

-----
