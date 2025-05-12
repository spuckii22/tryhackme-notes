# 🛡️ TryHackMe – Defensive Security Intro

## 📘 Room Information
- **Path:** Pre-Security → Introduction to Cyber Security → Defensive Security Intro  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-10  
- **Room Link:** [Defensive Security Intro – TryHackMe](https://tryhackme.com/room/defensivesecurityintro)

---

## 🔍 Room Overview

This room focuses on the **defensive side of cybersecurity**, in contrast to offensive roles such as penetration testing or ethical hacking. The two main goals in defensive security are:

1. **Preventing intrusions** from occurring  
2. **Detecting and responding** to intrusions when they happen  

Key components of this approach include:

- **User security awareness:** Training users on cyber threats and safety practices  
- **Asset documentation and management:** Keeping an inventory of systems and devices  
- **System updates and patching:** Ensuring software and hardware are up to date  
- **Preventative security tools:** Implementing firewalls and Intrusion Prevention Systems (IPS)  
- **Logging and monitoring:** Collecting and analyzing activity data from systems and networks  

---

## 🧩 Key Areas of Defensive Security

### 🛰️ Security Operations Center (SOC)

A SOC is a team of professionals who monitor systems and networks for security events and respond to them. Key responsibilities include:

- **Vulnerability Management:** Identifying and patching system weaknesses  
- **Policy Enforcement:** Detecting violations of security policies (e.g., data uploads to unauthorized platforms)  
- **Unauthorized Activity Detection:** Responding to stolen credentials and suspicious access  
- **Network Intrusion Detection:** Monitoring and responding to external attacks or exploitation attempts  

---

### 📊 Threat Intelligence

**Threat Intelligence** refers to gathering and analyzing data to anticipate and defend against cyber threats.  

- Focused on understanding **adversaries**, their **tactics, techniques, and procedures (TTPs)**  
- Intelligence is gathered from:
  - **Local sources:** System and network logs  
  - **Public sources:** Forums, open databases  
- Data must be **collected**, **processed**, and **analyzed** to produce actionable insights  
- Goals: Predict adversary behavior, reduce risks, and develop response strategies  

---

### 🕵️ Digital Forensics and Incident Response (DFIR)

#### 🧪 Digital Forensics  
The forensic investigation of digital incidents and crimes, including:

- **File System Analysis:** Recovering deleted or altered files  
- **Memory Analysis:** Inspecting malicious programs running in system memory  
- **System and Network Logs:** Tracing attacker behavior through event logs  

#### 🚨 Incident Response  
Structured process to handle cyber attacks and breaches:

1. **Preparation:** Policies, tools, and awareness in place  
2. **Detection and Analysis:** Identify and assess incidents  
3. **Containment, Eradication, and Recovery:** Isolate and resolve the issue  
4. **Post-Incident Activity:** Document outcomes and improve future response  

---

### 🦠 Malware Analysis

Malware is malicious software designed to harm or exploit systems. Two primary analysis methods:

1. **Static Analysis:** Inspecting code without running it  
2. **Dynamic Analysis:** Running malware in a controlled environment to observe behavior  

#### Common Malware Types:
- **Virus:** Attaches to programs and spreads by modifying or deleting files  
- **Trojan Horse:** Appears legitimate but performs harmful actions in the background  
- **Ransomware:** Encrypts user files and demands payment for decryption  

---

## 🖥️ Task: Simulating a SIEM (Security Information and Event Management)

**Scenario:**  
As a SOC analyst at a bank, I used a SIEM system to monitor and respond to security events. The platform aggregates logs and alerts into a single dashboard for efficient analysis.

### Key Actions Performed:
1. Reviewed alert messages  
2. Identified a suspicious IP address from the logs  
3. Verified the IP using a reputation scanner (e.g., ISP, domain, country)  
4. Escalated the event to the appropriate authority  
5. Blocked the malicious IP using firewall rules  
6. Found a message left by the attacker (a flag)  
7. Submitted the flag as part of the exercise  

⚠️ **Note:** Not all alerts are malicious — some could be false alarms, like a user forgetting their password. The analyst must investigate and determine the appropriate action.

---

## 🎓 Key Lessons and Takeaways

- Defensive security involves multiple subfields: SOC, Threat Intelligence, DFIR, and Malware Analysis  
- Experience with handling alerts in a simulated SIEM environment  
- Familiarity with open-source IP reputation databases (e.g., AbuseIPDB, Cisco Talos Intelligence)  
- Analysts must decide whether and how to escalate events  
- Firewalls play a critical role in blocking suspicious or malicious traffic  
- Reporting malicious IPs helps make the internet safer  

---

## 🛠️ Tools & Techniques Used
- **SIEM (Security Information and Event Management)** for alert monitoring and investigation  

---

## 🧾 Commands Used
- N/A (This room focused on concepts and alert investigation rather than command-line interaction)
