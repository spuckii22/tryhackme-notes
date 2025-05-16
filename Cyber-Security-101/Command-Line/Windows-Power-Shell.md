# 🧩 TryHackMe – Windows PowerShell

## 📘 Room Information
- **Path:** Cyber Security 101 → Command Line → Windows PowerShell  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-16  
- **Room Link:** [TryHackMe – Command Line](https://tryhackme.com/room/windowspowershell)

---

> ⚠️ **Disclaimer:**  
> This write-up is for educational and documentation purposes only. It does not include flags or exact solutions, in line with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview
This room is about learning the Windows PowerShell

**Learning Objectives**
- Learn what PowerShell is and its capabilities
- Understand the basic structure of PowerShell's language
- Learn and run some basic PowerShell commands
- Understand PowerShell's many applications in the cyber security industry

**Tasks**
1. Introduction  
2. What is PowerShell  
3. PowerShell Basics  
4. Navigating the File System and Working with Files  
5. Piping, Filtering, and Sorting Data  
6. System and Network Information  
7. Real-Time System Analysis  
8. Scripting  
9. Conclusion  

---

## 📂 Room Walkthrough

### 🔹 Task 1 – Introduction
- Just some basic information on what I am going to learn.

---

### 🔹 Task 2 – What is PowerShell
- PowerShell is a powerful tool from Microsoft for task automation and configuration management.
- Combines a command-line interface and scripting language built on the .NET framework.
- Is object-oriented and runs on Windows, macOS, and Linux.

#### The Power in PowerShell
- Objects represent items with properties (like name, size) and methods (like copy, delete).
- Cmdlets return structured objects, not plain text like older shells.

---

### 🔹 Task 3 – PowerShell Basics

#### Launching PowerShell
- Start Menu, Run dialog (Win+R), File Explorer, Task Manager, or CMD.

#### Syntax: Verb-Noun
- Examples:
  - `Get-Content` – gets content of a file.
  - `Set-Location` – changes working directory.

#### Basic Cmdlets
- `Get-Command` – lists all available cmdlets.
- `Get-Help` – shows help info about a cmdlet.
- `Get-Alias` – shows aliases like `cd` → `Set-Location`.

#### Downloading Cmdlets
- `Find-Module` – search for modules.
- `Install-Module` – installs a module.

---

### 🔹 Task 4 – Navigating the File System and Working with Files
- `Get-ChildItem` – list files/folders.
- `Set-Location` – change directory.
- `New-Item` – create file/folder.
- `Remove-Item` – delete file/folder.
- `Copy-Item`, `Move-Item` – copy/move.
- `Get-Content` – view file contents.

**Practical:** used to explore files and directories.

---

### 🔹 Task 5 – Piping, Filtering, and Sorting Data
- Use `|` to pipe output from one cmdlet into another.
- Example: `Get-ChildItem | Sort-Object Length`

#### Filtering
- `Where-Object` – filter by conditions (e.g. `-eq`, `-like`, `-gt`).
- `Select-Object` – choose which properties to display.
- `Select-String` – search inside files like `grep`.

---

### 🔹 Task 6 – System and Network Information
- `Get-ComputerInfo` – full system info.
- `Get-LocalUser` – list local users.
- `Get-NetIPConfiguration` – show IP settings.
- `Get-NetIPAddress` – show IP addresses in detail.

**Practical:** answered questions about users, descriptions, and network settings.

---

### 🔹 Task 7 – Real-Time System Analysis
- `Get-Process` – running processes (like Task Manager).
- `Get-Service` – service status.
- `Get-NetTCPConnection` – active TCP connections.
- `Get-FileHash` – compute file hash (verify file integrity).

---

### 🔹 Task 8 – Scripting
- Scripting lets you automate tasks using text files with commands.

#### Cybersecurity Use Cases
- **Blue Team:** automate log analysis, detect threats, reverse-engineer malware.
- **Red Team:** automate enumeration, launch payloads, evade detection.
- **Sysadmins:** monitor health, enforce security, respond to incidents.

#### Useful Cmdlet
- `Invoke-Command -ScriptBlock {}` – run remote commands.

---

## 🛠️ Commands & Shortcuts

- `Get-Command`, `Get-Help`, `Get-Alias`
- `Get-ChildItem`, `Set-Location`, `New-Item`, `Remove-Item`
- `Copy-Item`, `Move-Item`, `Get-Content`
- `Sort-Object`, `Where-Object`, `Select-Object`, `Select-String`
- `Get-ComputerInfo`, `Get-LocalUser`, `Get-NetIPConfiguration`, `Get-NetIPAddress`
- `Get-Process`, `Get-Service`, `Get-NetTCPConnection`, `Get-FileHash`
- `Invoke-Command`

---

