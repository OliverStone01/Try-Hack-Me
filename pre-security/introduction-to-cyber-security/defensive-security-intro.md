# 🚪 Room: Defensive Security Intro

## 🎯 Objectives
- Introduction to defensive security and related topics, such as Threat Intelligence, SOC, DFIR, Malware Analysis, and SIEM.

## 🛠️ Tools Used
- IP scanner

## 💬 Summary
-

-----

## Notes:

#### Task 1:

Defensive security (**Blue Team**) is concerned with two main tasks:
1. Preventing intrusions from occurring.
2. Detecting intrusions when they occur and responding properly.

Some of the tasks related to defensive security include:
- **User cyber security awareness**:  
  training users to help protect against attacks.
- **Documenting and managing assets**:  
  We need to know the systems and devices to be able to manage and protect them
- **Updating and patching systems**:  
  Ensuring that computers, servers, and network devices are correctly updated and patched to prevent agaist known vulnerabilities.
- **Setting up preventative security devices**:  
  firewalls & IPS (Intrusion prevention systems)
- **Setting up logging and monitoring devices**:  
  If a new unauthorised device appears of the network, you want to be able to see it.

We will also look at:
- Security Operations Center (**SOC**)
- Threat Intelligence
- Digital Forensics and Incident Response (**DFIR**)
- Malware Analysys

-----

#### Task 2:

**Security Operations Center (SOC):**  
A team of cyber security professionals that monitors the network and it's systems to detect malicious cyber security events.
    
Main Intrests are:
- **Vulnerabilities**:  
  Fixing vulnerabilities by installing updates or patches.
- **Policy violations**:  
  A set of rules required to protect the network and systems.
- **Unauthorised activity**:  
  When a password and username are stollen by an attacker, this must be fixed as soon as possible.
- **Network intrusions**:  
  Can occur when a user clicks on on a malicious link or an attcker exploits a public server.

Threat Intelligence:  
In this context, intelligence refers to information you gather about actual and potential enemies. A threat is any action that can disrupt or adversely affect a system or steal data. 

Examples of adversaries:  
- **Nation State**:  
  Goverment run hackers for political reasons.
- **Ransomware group**:  
  Intended to lock down systems for a ransom.

The three stages of data collection:
- **Collecting data**:  
  from local sources like Network logs and public sources like forums.
- **Processing data**:  
  reformating the data for better analysis.
- **Analysing Data**:  
  find information about the attackers and their motives. Create a list of actionable steps.


**Digital Forensics and incident response (DFIR)**
Digital forensics is about analysing evidence of an attack and the attackers. Including intellectual property theft, cyber espionage, and possession of unauthorised content.

Focus areas are:
- **File System**:  
  Analysing a `digital forensics image` (low-level-copy) of a system's storage which reveals installed programs, created files, partially overwritten files, and deleted files.
- **System memory**:  
  Analysing a `digital forensics image` (low-level-copy) of a system's memory as an attacker may run their malicious program in memory without saving it to the disk.
- **System logs**:  
  Logs provide information everything that happened on a system. Even if the attacher tries to clear their traces.
- **Network logs**:  
  These logs of network packets can help answer questions about if an attack is occuring.


**Incident Response**
Refers to a data breach or a cyber attack. In some cases it can be something less critical, such as:
- Misconfiguration
- Intrusion attempts
- Policy violation

Examples of cyber attacks:
- An attacker making the Network or System inaccessible.
- Defacing (changing) the public website.
- Data breach (stealing data)

The aim of a `Incident Response` is to reduce damage and recover in the shortest time possible. Ideally, you should have a developed plan ready.

The four majour phases of incident response:
- **Preparation**:  
  A team trained and ready to handle incidents.
- **Detection and Analysis**:  
  Using tools to detect and analyse threats.
- **Containment, Eradication, and recovery**:  
  Detect it, Stop it from affecting other systems, eliminate it, and recover the affected systems.
- **Post-incident Activity**:  
  After a successful recovery, a report is produced, and the lessons learned are shared to prevent future incidents.

<img src="/pre-security/introduction-to-cyber-security/assets/incident-response-diagram.png" alt="Incident response diagram" style="width:300px">

**Malware Analysis**  
`Malware` = Malicious software.

Software refers to programs, documents, and files you can save on a disk or sent over the network.

Some malware types:
- **Virus**:  
  code that attaches itself to a programme. Designed to spread from one device to another. Works by altering, overwriting, and deleting files. Damage ranges from slowing machines to making them unusable.
- **Trojan Horse**:  
  A programme that displays itself as something a user would want, but hides a malicious function underneath.
- **Ransomeware**:  
  A malicious programme that encypts the user's files seeking ransom payment to unlock again.

Malware analysis use diffrent means to learn about malicious programs:
- **Static analysis**:  
  Inspecting the programme without running it. Usually requires knowledge on assembly language.
- **Dynamic analysis**:  
  Running the malware in a controlled enviroment and monitoring its activities.

-----

#### Task 3

**The Scenario**
Pretend you are a SOC analyst responsable for pretecting a bank. The bank's SOC uses a SIEM tool.

`SIEM` = Security information and event management

The SIEM tools gathers security-related information and events from various sources and presents them in a dashboard. If it finds something suspicious, it will generate an alert.

Sometimes the alerts are not malicious. It is up to the analyst to investigate which one is harmful. For example, multiple failed login attempts. It is suspicious, but is also quite common.

An alert might be related to connections from unknown IP Addresses.

`IP address` = Internet Protocol address.

An IP Address is like a home address for you computer on the internet. It tells other computers where to send the information you request. An unknown IP could mean someone new is connecting or someone is attempting unauthorised access.

**Simulating a SIEM**  

I've loaded the site and it is a SIEM dashboard. The Instructions say "Inspect the alerts in your SIEM dashboard. Find the malicious IP address from the alerts, make a note of it, and then click on the alert to proceed."

<img src="/pre-security/introduction-to-cyber-security/assets/siem-dashboard.png" alt="SIEM Dashboard" style="width:300px">

Below the charts is a "Alert Log". Second log down, the message reads "Unauthorized connection attempt detected from IP address 143.110.250.149 to port 22"

After clicking on this log, Im taken to another set of instructions. "There are websites on the Internet that allow you to check the reputation of an IP address to see whether it's malicious or suspicious."

After entering the IP address, the result comes back as "Malicious".

The next instructions recomend two open source tools to do searches like this:
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

Task 1:

1. Which team focuses on defensive security?

Answer: Blue Team

-----

Task 2:

1. What would you call a team of cyber security professionals that monitors a network and its systems for malicious events?

Answer = Security Operations Center

2. What does DFIR stand for?

Answer = Digital Forensics and Incident Response

3. Which kind of malware requires the user to pay money to regain access to their files?

Answer = Ransomware

-----

Task 3:

What is the flag that you obtained by following along?

Answer = THM{THREAT-BLOCKED}
