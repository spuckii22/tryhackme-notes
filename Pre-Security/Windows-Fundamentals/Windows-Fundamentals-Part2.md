# 🧩 TryHackMe – Windows Fundamentals Part 2

## 📘 Room Information
- **Path:** Pre-Security → Windows Fundamentals → Windows Fundamentals Part 2  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-14  
- **Room Link:** https://tryhackme.com/room/windowsfundamentals2x0x

---

> ⚠️ **Disclaimer:**  
> This write-up is for educational and documentation purposes only. It does not contain flags or exact solutions, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview
This room is a continuation of the Windows Fundamentals series and introduces several administrative tools used for monitoring and configuring the Windows operating system.

**Task Overview:**
- Task 1: Introduction  
- Task 2: System Configuration  
- Task 3: Change UAC Settings  
- Task 4: Computer Management  
- Task 5: System Information  
- Task 6: Resource Monitor  
- Task 7: Command Prompt  
- Task 8: Registry Editor  
- Task 9: Conclusion

---

## 📂 Room Walkthrough

### 🔹 Task 1 – Introduction
- Just a short intro to set up the virtual environment.

---

### 🔹 Task 2 – System Configuration
- **Tool:** `msconfig`
- Used for advanced troubleshooting and diagnosing startup issues.
- **Tabs:**
  - **General** – Normal, Diagnostic, Selective startup.
  - **Boot** – Define boot options.
  - **Services** – Manage running/stopped services.
  - **Startup** – Now handled by Task Manager.
  - **Tools** – Launch other system utilities with descriptions.

---

### 🔹 Task 3 – Change UAC Settings
- User Account Control (UAC) can be configured via a slider.
- Ranges from "Always notify" to "Never notify."
- Lowering UAC settings increases the risk of unauthorized changes.

---

### 🔹 Task 4 – Computer Management (`compmgmt.msc`)
A centralized utility broken into 3 main sections:

#### 🛠 System Tools
- **Task Scheduler** – Automate script/app execution based on events or schedules.
- **Event Viewer** – Log categories include Application, Security, and System. Event types: Error, Warning, Info, Success/Failure Audit.
- **Shared Folders** – View shared directories, active sessions, and open files.
- **Local Users and Groups** – Manage users, groups, and permissions.
- **Performance Monitor (`perfmon`)** – View system performance metrics in real time or from logs.
- **Device Manager** – Manage hardware components, enable/disable drivers.

#### 💾 Storage
- Includes Disk Management: set up new drives, extend/shrink volumes, assign drive letters.

#### ⚙ Services and Applications
- Enable/disable services, configure service properties.

---

### 🔹 Task 5 – System Information (`msinfo32`)
- Overview of hardware and software.
- **Categories:**
  - **Hardware Resources**
  - **Components** – Detailed info about devices (e.g. display, sound, storage).
  - **Software Environment** – Includes drivers, services, tasks, and environment variables.

---

### 🔹 Task 6 – Resource Monitor (`resmon`)
- Provides real-time monitoring of:
  - CPU usage
  - Memory consumption
  - Disk activity
  - Network traffic
- Great for identifying resource bottlenecks.

---

### 🔹 Task 7 – Command Prompt
- Windows CLI equivalent to the Linux terminal.

#### Common Commands
- `hostname` – Shows the system name.
- `whoami` – Shows current logged-in user.
- `ipconfig` – Network config (IP, gateway, DNS).
- `ipconfig /?` – Shows help for ipconfig command.
- `cls` – Clears the screen.
- `netstat` – Displays network connections and ports.
- `net` – Manage users, shares, etc. (`net help` for usage).

---

### 🔹 Task 8 – Registry Editor (`regedit`)
- Hierarchical database storing OS, app, and user settings.
- Sensitive and critical — only advanced users should make changes.

**Registry stores:**
- User profiles
- Installed apps and their defaults
- Hardware configurations
- Port usage and driver settings

---

## 🛠️ Commands & Shortcuts
```bash
# Open System Configuration
msconfig

# Open Computer Management
compmgmt.msc

# Open System Information
msinfo32

# Open Resource Monitor
resmon

# Open Registry Editor
regedit

# Open Command Prompt
cmd

# Common Command Prompt tools
hostname
whoami
ipconfig
cls
netstat
net help
