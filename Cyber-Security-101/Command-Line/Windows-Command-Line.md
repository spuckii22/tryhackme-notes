# 🧩 TryHackMe – Windows Command Line

## 📘 Room Information
- **Path:** Cyber Security 101 → Command Line → Windows Command Line  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-16  
- **Room Link:** [TryHackMe – Command Line](https://tryhackme.com/room/windowscommandline)

---

> ⚠️ **Disclaimer:**  
> This write-up is for educational and documentation purposes only. It does not include flags or exact solutions, in line with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview
This room teaches how to use the Windows Command Line (`cmd.exe`) effectively. The focus is on:
- Displaying system information  
- Troubleshooting networks  
- Managing files and folders  
- Viewing and managing running tasks and processes  

**Tasks:**
1. Introduction  
2. Basic System Information  
3. Network Troubleshooting  
4. File and Disk Management  
5. Task and Process Management  
6. Conclusion  

---

## 📂 Room Walkthrough

### 🔹 Task 1 – Introduction
- Compared GUI (Graphical User Interface) vs CLI (Command Line Interface).  
- CLI tools may take more time to learn but are faster and more resource-efficient once mastered.

**Benefits of CLI:**  
- Uses fewer system resources  
- Supports scripting and automation  
- Useful for remote administration (e.g. via SSH)

**Practical:**  
- Started the attacker and target machine and used SSH to connect from AttackerBox to the target machine via `ssh user@IP`.

---

### 🔹 Task 2 – Basic System Information

#### Key Commands:
- `set` → displays system environment variables, including the system PATH  
- `ver` → outputs the current Windows OS version  
- `systeminfo` → displays detailed information such as OS version, install date, system architecture, BIOS version, and available RAM  
  - Add `| more` to scroll output one page at a time  
- `help` → lists available commands with brief descriptions  
- `cls` → clears the terminal screen  

**Practical:**  
- had to find the OS version and the hostname

---

### 🔹 Task 3 – Network Troubleshooting

#### Networking Configuration:
- `ipconfig` → shows basic IP info like IPv4 address, subnet mask, and default gateway  
- `ipconfig /all` → extended info: MAC address, DNS servers, DHCP status  

#### Network Troubleshooting Tools:
- `ping domain.com` → checks if a host is reachable and returns response times  
- `tracert domain.com` → traces and shows the route packets take to the destination (like hops between routers)

#### DNS Lookup:
- `nslookup domain.com` → queries DNS for IP address  
- `nslookup domain.com 1.1.1.1` → performs DNS lookup using the 1.1.1.1 server  

#### Viewing Network Connections:
- `netstat` → displays active connections and ports  
  - `-a` → show all connections and listening ports  
  - `-b` → show the executable creating each connection  
  - `-o` → show PID for each connection  
  - `-n` → use numeric addresses instead of resolving hostnames  

**Practical:**  
- had do look up the name of a process listening on a specific port
- had to find out the subnet mask

---

### 🔹 Task 4 – File and Disk Management

#### Navigating Directories:
- `cd` → display or change current directory  
- `dir` → list contents of directory  
  - `/a` → include hidden/system files  
  - `/s` → recursive list through subfolders  
- `tree` → visual tree structure of directories  
- `cd ..` → go up one directory  
- `mkdir foldername` → create new folder  
- `rmdir foldername` → remove folder  

#### File Operations:
- `type filename.txt` → display file content  
  - Use `| more` to scroll output  
- `copy fileA fileB` → copy a file  
- `move fileA folderB` → move file to folder  
- `del file.txt` or `erase file.txt` → delete a file  
- Use `*` as a wildcard: e.g. `del *.log` → deletes all `.log` files  

**Practical:**  
- had to find out the content of a File

---

### 🔹 Task 5 – Task and Process Management

#### Process Listing and Filtering:
- `tasklist` → lists all running processes  
- `tasklist /FI "imagename eq example.exe"` → shows only Notepad processes  
- `tasklist /FI "PID eq 1234"` → filters by process ID  

#### Terminating a Process:
- `taskkill /PID 1234` → terminates the process with PID 1234  
- `taskkill /IM example.exe` → terminates all processes matching the image name  

**Practical:**  
- Answer some questions (kill process and find running process)

---

### 🔹 Task 6 – Conclusion

This room covered the essential command line tools for working on Windows systems, especially over remote access.

**Key Learnings:**
- Use `more` to paginate output  
  - `type longfile.txt | more`  
  - `systeminfo | more`  
- CLI offers powerful tools for system diagnostics, file management, and network analysis  

#### Extra Useful Commands:
- `chkdsk` → checks disks for errors and bad sectors  
- `driverquery` → lists all installed device drivers  
- `sfc /scannow` → checks integrity of system files and fixes corruption if found  

---

## 🛠️ Commands & Shortcuts

```bash
# System Info
ver
systeminfo | more

# Network Info
ipconfig /all
ping tryhackme.com
tracert tryhackme.com
nslookup tryhackme.com
netstat -abon

# Files
cd ..
dir /a
mkdir test
type example.txt | more

# Tasks
tasklist
taskkill /PID 1234
