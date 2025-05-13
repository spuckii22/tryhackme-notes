# 🧩 TryHackMe – Linux Fundamentals (Part 1)

## 📘 Room Information
- **Path:** Pre-Security → Linux Fundamentals → Linux Fundamentals Part 1  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-13  
- **Room Link:** https://tryhackme.com/room/linuxfundamentalspart1

---

> ⚠️ **Disclaimer:**  
> This write-up is for educational and documentation purposes only. It does not contain flags or exact solutions, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview

This room introduces the basics of Linux, including essential commands, filesystem navigation, file searching, and shell operators.  
Topics covered include:

- Linux background and common use cases  
- Terminal-based interaction  
- Navigating the filesystem  
- Using `find`, `grep`, and `wc`  
- Understanding shell operators like `&`, `&&`, `>`, `>>`  

---

## 📂 Room Walkthrough

### 🔹 Task 1 – Introduction

- Linux is an operating system like Windows or macOS.
- It's widely used in servers, smart devices, cars, point-of-sale systems, and more.

---

### 🔹 Task 2 – A Bit of Background on Linux

- Linux is lightweight, open-source, and based on UNIX.
- Popular distributions include Ubuntu and Debian.
- Can run on very low-spec hardware (e.g., 512MB RAM).

---

### 🔹 Task 3 – Interacting with a Linux Machine (In-Browser)

- Deployed and connected to a Linux machine through the TryHackMe in-browser terminal.

---

### 🔹 Task 4 – Running Basic Commands

Introduced to the command-line interface and executed simple commands:

| Command   | Description                                    |
|-----------|------------------------------------------------|
| `echo`    | Prints text to the terminal (`echo "hello"`)   |
| `whoami`  | Shows the current logged-in user               |

---

### 🔹 Task 5 – Navigating the Filesystem

Essential navigation and file inspection commands:

| Command   | Description                                       |
|-----------|---------------------------------------------------|
| `ls`      | Lists files and directories                       |
| `cd`      | Changes the current directory                     |
| `cat`     | Outputs the contents of a file                    |
| `pwd`     | Prints the current working directory (full path)  |

---

### 🔹 Task 6 – Searching for Files

Learned how to locate files and search their contents:

| Command                        | Description                                 |
|--------------------------------|---------------------------------------------|
| `find -name "filename"`        | Searches for files by name                 |
| `find -name "*.txt"`           | Searches for all `.txt` files              |
| `grep "pattern" filename`      | Searches inside a file for a keyword       |
| `wc -l filename`               | Counts the number of lines in a file       |

---

### 🔹 Task 7 – Shell Operators

Introduced to useful shell operators:

| Operator | Purpose                                                                 |
|----------|-------------------------------------------------------------------------|
| `&`      | Runs a command in the background                                       |
| `&&`     | Runs a second command only if the first succeeds                      |
| `>`      | Redirects output to a file (overwrites if file exists)                |
| `>>`     | Appends output to a file without overwriting existing content         |


---

### 🧩 Task 8: Conclusions & Summaries

#### Covered
- why linux is commonplace today
- interacted with first linux machine
- ran some fundamental commands
- introduction to navigating around the filesystem & how we can use commands like "find" and "grep"
- found out about shell operators

---

### Commands
```bash
echo "hello" > file.txt        # Overwrites file.txt with "hello"
echo "world" >> file.txt       # Appends "world" to file.txt
ls                             # lists files/directories
pwd                            # returns current directory
grep                           # used to filter
find -name name                # used to find certain things




