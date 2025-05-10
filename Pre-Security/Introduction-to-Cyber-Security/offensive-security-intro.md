# 🧩 TryHackMe – Offensive Security Intro

## 📘 Room Information
- **Path:** -> Pre-Security -> Introduction to Cyber Security ->  Offensive Security Intro
- **Difficulty:** Easy 
- **Completed on:** 2025-05-10
- **Room Link:** https://tryhackme.com/room/offensivesecurityintro

---

## 🔍 Room Overview

> Short summary of the room (2–3 sentences):
This is my first room where I started my first machine to "hack". In this room a fake bank application called Fakebank has been prepared.
I will use the command-line application called "Gobuster" to brute-force the Fakebank's website to find hidden directories and pages.
Gobuster will take a list of potential page or directory names and try accessing a website with each of them, if the page exists, it tells me.
  
> What did this room teach? What was its purpose?   
This room introduces the concept of offensive security by guiding me through my first legal website hack. It explains the basic process of web attacks.
That most companies have an admin portal page, giving their staff access to basic admin controls.
That there are hidden pages such as (/bank-transfer)
That as an ethical hacker, I would probably find vulnerabilities in the application and rpeort it back to the bank in order to fix them before a hacker exploits them


---

## 🔍 Room Walkthrough
1. Start the terminal -> I started the terminal in order to write commands.
2. Using Gobuster to find hidden website pages/directories -> I typed in the gobuster command and got a Status 200(OK) on the /bank-transfer directory -> found /bank-transfer page
3. Hack the bank -> found the page and entered it into the browser's adress bar (fakebank.thm//bank-transfer)
3.1
3.2 Got access to the admin portal where I can transfer money from a bank account number to another
3.3 Needed to transfer $2000 from bank account 2276 to my account 8881 (Success, transfer completed)
3.4 Had to check if I received the money -> Indeed I did!

---

## 🛠️ Tools  & Techniques Used

- command-line application Gobuster -> lists potential page or directory names and try accessing a website with each of them
- Terminal - allows us to interact with a computer without using a graphical user interface (GUI)
- brute-force attack

---

 ## 🛠️ Commands

Gobuster:
 - gobuster -u http://fakebank.thm -w wordlist.txt dir -> -u is used to state the website I am scanning, -w takes a list of words to iterate through to find hidden pages, dir just says that we search for files/directories
 - scans the website with each word in the list, finding pages that exist on the site. Gobuster will tell me the page/directory names (indicated by Status:200)

