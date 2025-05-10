# 🧩 TryHackMe – Defensive Security Intro

## 📘 Room Information
- **Path:** -> Pre-Security -> Introduction to Cyber Security ->  Defensive Security Intro
- **Difficulty:** Easy 
- **Completed on:** 2025-05-10
- **Room Link:** https://tryhackme.com/room/defensivesecurityintro

---

## 🔍 Room Overview

> Short summary of the room:
While the previous room was about learning the offensive security side (exploiting software bugs, leveraging insecure setups, taking advantage of unenforced access control policies, pentesting), this room will examine its counterpart.
Two Main tasks:
1. Preventing intrusions from occuring
2. Detecting intrusions when they occur and responding properly

So it's about:
- user cyber security awareness: training users about cyber security
- documenting and managing assets: need to know the systems and devices
- updating and patching systems: ensuring that computers, servers, and network devices are correctly updated and patched
- setting up preventative security devices: firewall and intrusion prevention systems (IPS) -> Firewalls control what network traffic can go inside and what can leave the system or network. IPS blocks any network traffic that matches present rules and attack signatures.
- setting up logging and monitoring devices


---

## 🔍 Room Walkthrough
**Task 2: Areas of Defensive Security**

Cover topics such as:
1. Security Operations Center (SOC) - Threat Intelligence
2. Digital Forensics and Incident Response (DFIR) - Malware Analysis


**Security Operations Center (SOC):**

Team of cyber security professionals that monitors the network and its systems to detect malicious cyber security events

**Main areas of interest:**
> Vulnerabilites(weakness): whenever a system vulnerability is discovered, it is essential to fix it by installing a proper update or patch.
> Policy violations: A security policy is a set of rules required to protect the network and systems. (violation if users upload confidential company data to an online storage device)
> Unauthorized activity: user's login name and password are stolen -> SOC must detect and block such an event asap before further damage is done.
> Network intrusions: Intrusion can occur when a user clicks on a malicious link or an attacker exploits a public server -> must detect it asap


**Threat Intelligence:**
> Intelligence -> information you gather about actual and potential enemies
> Threat -> any action that disrupt or adversely affect a system
> Threat Intelligence -> collects information to help the company better prepare against potential adversaries
> Different companies have different adversaries
> Intelligence needs data -> Data has to be collected, processed, and analyzed.
> Data is collected from local sources (network logs) and public sources (forums)
> Data processing -> arranging the data into a format suitable for analysis.
> Analysis phase -> seeks to find more information about the attackers and their motives and aims to create a list of recommendations and actionable steps.
> Learning about adversaries -> tactics, techniques, procedures
> Result -> identify the adversary and predict their activity -> mitigate their attacks and prepare a response strategy

**Digital Forensics and Incident Response (DFIR):**

**Digital Forensics:**
> Forensics is the application of science to investigate crimes and establish facts
> analyzing evidence of an attack and its perpetrators and other areas (intellectual property theft, cyber espionage, possesion of unauthorized content)
> focuses on differant areas:
> > File System: analyzing a digital forensics image of a system's storage (information about installed programs, created files, partially overwritten files, deleted files)
> > System memory: malicious programs running in memory without saving it to the disk -> forensic image best way to analyze its contents and learn about the attack
> > System logs: provide plenty of information about what happened on a system (some traces always remain)
> > Network logs: logs of the network packets that have traversed a network

**Incident Response:**
> incident -> data breach or cyber attack (in some cases it can be something less critical such as misconfiguration, an intrusion attempt or policy violation)
> Examples of a Cyber Attack -> making network inaccessible, defacing the poublic website, data breach (stealing company data)
> specifies the methodology that should be followed in case of a cyber attack
> aims to reduce damage and recover it in the shortest time possible

> four major phases:
1. Preperation -> prevent/handle incidents
2. Detection and Analysis -> detect incident, analyze any detected incident further
3. Containment, Eradication, and Recovery -> stop it from affecting other systems, eliminate it, recover affected systems (e.g. Stop virus from spreading)
4. Post-Incident Activity: produce report, share lessons learned

**Malware Analysis:**
> Malware = malicious software
> Software = program, documents, files you can save on a disk or send over the network
> aims to learn about malicious programs using:
> 1. Static analysis by inspecting the malicious program without running it
> 2. Dynamic analysis by running the malware in a controlled environment and monitoring its activites

** Malware types:**
> virus = piece of code that attaches itself to a programm and is designed to spread from one computer to another (altering, overwriting, deleting files)
> Trojan Horse = program that shows one desirable function but hides a malicous function underneath (video player that gives attachker complete control over the system)
> Ransomware = malicous program that encrypts the user's files -> makes the files unreadable without knowing the encryption password -> have to pay a "ransom"

**Task 3**

Scenario: I am a SOC analyst responsible for protecting a bank. We use a Security Information and Event Management (SIEM) tool, which gathers security-related information and events from various sources and presents them in one dashboard. If something suspicious happens = alert!

> not all alerts are malicous -> up to the analyst to use their expertise -> may encoutner an alert where a user has failed multiple login attempts (maybe he has forgotten his password or malicous)
> alerts related to connections from unknown IP addresses
> IP address = like a home address from your computer on the internet which tells other computers where to send the information you request. If IP unknown -> someone new is trying to connect or someone is attempting unauthorized access.

** Simulating a SIEM **
> Need to find the flag in this simulated environment
> Have to inspect the alerts and find the malicious IP address from the alerts
> Steps:
> 1. Went over the alert messages
> 2. found the IP
> 3. Entered it to an IP-Scanner -> saw that it was found in a database and that it is malicious (ISP, Domain Name, Country, City)
> 4. Choose to whom I would escalate this event
> 5. Got permission to block that IP -> proceed and implement block rule
> 6. Block malicious IP on the firewall
> 7. Find out what message they left = FLAG FOUND!!!
> 8. Answered the question (Entered the Flag)


> Flag = series of characters with a format like e.g. "THM{Random_WORDS}.

## Key Lessons/Takeaways:
> different subfields (SOC, Threat Intelligence, Malware Analysis, DFIR)
> how to deal with alerts in a simlulated SIEM environment
> There are websites on the Internet that allow me to check the reputation of an IP address to see whether it's malicious or suspicious
> e.g. open soruce databases (AbuseIPDB, Cisco talos Intelligence) where i can perform this reputation check and location check.
> Most security analysts use these tools to aid them with alert investigations.
> You can make the itnernet safer by reporting malicous IPs -> AbuseIPDB
> shouldn't worry too much if it was a failed authentication attempt -> but it was a successful authentication from this malicious IP -> so report
> You need to decide whom you would escalate the event
> Firewalls are designed to block or allow traffic based on various criteria, including IP addresses


## 🛠️ Tools  & Techniques Used
> Security Information and Event Management tool


 ## 🛠️ Commands



