# 🧩 TryHackMe – Linux Fundamentals (Part 2)

## 📘 Room Information
- **Path:** Pre-Security → Linux Fundamentals → Linux Fundamentals Part 2  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-13  
- **Room Link:** https://tryhackme.com/room/linuxfundamentalspart2

---

> ⚠️ **Disclaimer:**  
> This write-up is for educational and documentation purposes only. It does not contain flags or exact solutions, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview
This room is about:
- Unlocking the potential of my first few commands by using flags and arguments  
- Advancing knowledge of the filesystem to perform useful commands like copying and moving files  
- Discovering how access to files and folders is managed and how to determine access  

### Task List:
- Task 1: Introduction  
- Task 2: Accessing Linux Machine using SSH  
- Task 3: Introduction to Flags and Switches  
- Task 4: Filesystem Interaction Continued  
- Task 5: Permissions  
- Task 6: Common Directories  
- Task 7: Conclusions and Summaries  

---

## 📂 Room Walkthrough

### 🔹 Task 1 – Introduction
- Just basic introductory content to Linux command-line practice and structure.

---

### 🔹 Task 2 – Accessing Linux Machine using SSH (Deploy)
- I had to deploy a virtual lab with an AttackBox and a target Linux machine.
- SSH (Secure Shell) is a secure protocol to remotely control Linux machines via an encrypted connection.
- It allows remote command execution.
- Login syntax: `ssh username@IP`
- Password is hidden while typing — normal behavior!

---

### 🔹 Task 3 – Introduction to Flags and Switches
- Many commands can be extended with arguments called **flags** or **switches**.
- Example: `ls` only shows visible files by default, but `ls -a` shows hidden files too.
- Hidden files start with a `.` (dot).
- Use `--help` to get short usage info.
- Use `man <command>` to read the full manual page (e.g., `man ls`).

---

### 🔹 Task 4 – Filesystem Interaction Continued

#### File and Folder Commands:
- `touch` → Create a file  
- `mkdir` → Create a folder  
- `cp` → Copy file/folder  
- `mv` → Move or rename  
- `rm` → Remove  
- `file` → Identify file type  

#### Examples:
- `touch example.txt` creates a blank file  
- `mkdir myfolder` makes a new directory  
- `rm myfile` deletes a file  
- `rm -R myfolder` deletes a folder and its contents  
- `cp file1 file2` copies file1 to file2  
- `mv oldname newname` renames/moves file  
- `file myfile` shows what type of file it is  

---

### 🔹 Task 5 – Permissions 101

- Use `ls -l` to list permissions for files and folders.
- Files and folders have **Read (r)**, **Write (w)**, and **Execute (x)** permissions.
- These permissions are set for:
  - The **owner** (user)
  - The **group**
  - **Others** (everyone else)

#### Switching Users
- `su` lets you switch users (needs their password).
- `su -l <username>` starts a full login shell for the new user.

---

### 🔹 Task 6 – Common Directories

- `/etc` → system config files (`passwd`, `shadow`, `sudoers`)  
- `/var` → log files, app data (`/var/log`)  
- `/root` → root user’s home directory  
- `/tmp` → temporary storage, cleared after reboot. Anyone can write here (great for pentesting scripts)

---

### 🔹 Task 7 – Conclusions and Summaries

In this part I learned:
- How to connect to Linux machines using SSH  
- How to use flags and view help pages  
- How to create, move, copy, and delete files/folders  
- How Linux permissions work  
- What common Linux directories are used for  

---

## 🛠️ Commands

```bash
ssh username@IP             # Connect via SSH
ls -a                       # List all files including hidden
man <command>               # Open manual page
touch filename              # Create file
mkdir foldername            # Create folder
cp file1 file2              # Copy file
mv file1 file2              # Move or rename file
rm file                     # Remove file
rm -R folder                # Remove folder recursively
file filename               # Show file type
su -l username              # Switch user with login shell
