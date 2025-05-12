# 🧩 TryHackMe – Offensive Security Intro

## 📘 Room Information
- **Path:** Pre-Security → Introduction to Cyber Security → Offensive Security Intro  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-10  
- **Room Link:** [Offensive Security Intro – TryHackMe](https://tryhackme.com/room/offensivesecurityintro)

---

> ⚠️ **Disclaimer:**  
> This write-up is for **educational and documentation purposes only**. It does **not contain flags or exact solutions**, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview

This was my first room involving hands-on offensive security. The challenge simulated a vulnerable web application from a mock banking environment. My goal was to use a command-line tool to enumerate hidden parts of the website and explore how attackers might discover insecure pages or functionalities.

Through this room, I learned about:
- The process of **directory brute-forcing**  
- How web applications often expose hidden resources  
- The importance of **ethical hacking** in identifying and reporting vulnerabilities responsibly

It was a great first step into understanding how attackers think and how defenders can prevent those tactics.

---

## 🧪 What I Did

1. I launched the virtual machine and opened the terminal provided in the room.  
2. Using **Gobuster**, I scanned the website with a wordlist to identify hidden directories.  
3. When the scan returned a successful result, I visited the discovered page in my browser.  
4. I interacted with the available functionality and simulated an action that would typically be a security concern in a real-world banking application.  
5. The process concluded with a validation step that confirmed the success of the simulated interaction.

This flow helped me understand how a small misconfiguration in a website can lead to much larger risks.

---

## 🛠️ Tools & Techniques Used

- **Gobuster**:  
  A tool for brute-forcing URIs (directories and files) in web servers using wordlists.

- **Terminal**:  
  Command-line interface used to interact with the system and tools during the challenge.

- **Directory brute-forcing**:  
  A reconnaissance technique used to discover unlinked or hidden directories on a web server.

---

## 💻 Example Command Used

```bash
gobuster dir -u http://targetsite -w wordlist.txt
