# 🧩 TryHackMe – Windows Fundamentals Part 1

## 📘 Room Information
- **Path:** Pre-Security → Windows Fundamentals → Windows Fundamentals Part 1  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-14  
- **Room Link:** https://tryhackme.com/room/windowsfundamentals1xbx

---

> ⚠️ **Disclaimer:**  
> This write-up is for educational and documentation purposes only. It does not contain flags or exact solutions, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview
This room introduces fundamental components of the Windows operating system, including the GUI, editions, file system, user account management, settings, and key administrative tools.

**Task Overview:**
- Task 1: Introduction to Windows  
- Task 2: Windows Editions  
- Task 3: The Desktop (GUI)  
- Task 4: The File System  
- Task 5: The Windows\System32 Folder  
- Task 6: User Accounts, Profiles, and Permissions  
- Task 7: User Account Control  
- Task 8: Settings and the Control Panel  
- Task 9: Task Manager

---

## 📂 Room Walkthrough

### 🔹 Task 1 – Introduction to Windows
- Brief overview of the room.
- Start the Remote Machine for hands-on exercises.

---

### 🔹 Task 2 – Windows Editions
- Windows is the dominant OS in homes and enterprises.
- Common versions: XP → Vista → 7 → 8 → 10 → 11.
- Windows 11 Pro supports BitLocker encryption.

---

### 🔹 Task 3 – The Desktop (GUI)
**Main Components:**
1. Desktop  
2. Start Menu  
3. Search Box  
4. Task View  
5. Taskbar  
6. Toolbars  
7. Notification Area  

---

### 🔹 Task 4 – The File System
- Uses NTFS (New Technology File System), a journaling file system.
- Supports:
  - Files larger than 4GB
  - Permissions (Read, Write, Modify, etc.)
  - Compression and encryption (EFS)

**Viewing File Permissions:**
- Right-click → Properties → Security tab → Select user/group

**Alternate Data Streams (ADS):**
- Files can have multiple data streams (e.g. metadata).
- Often abused by malware to hide payloads.

---

### 🔹 Task 5 – The Windows\System32 Folder
- **C:\Windows** = core OS files (can access using `%windir%`)
- **C:\Windows\System32** = critical system executables and libraries.
- Use caution when interacting with files here.

---

### 🔹 Task 6 – User Accounts, Profiles, and Permissions
- **Account Types:**
  - **Administrator**: Can perform system-wide changes.
  - **Standard**: Limited to user-specific operations.

- **User Profiles:**
  - Stored in `C:\Users\Username`
  - Created at first login.

- **Manage with Local Users and Groups (lusrmgr.msc):**
  - Groups assign inherited permissions.
  - A user can belong to multiple groups.

---

### 🔹 Task 7 – User Account Control (UAC)
- Helps mitigate risks from users running as Admins.
- **UAC Behavior:**
  - Admin users are prompted before running privileged tasks.
  - Standard users must input an Admin password for elevated tasks.

---

### 🔹 Task 8 – Settings and the Control Panel
- Two main interfaces for configuring the system:
  - **Settings App**: modern UI for common settings.
  - **Control Panel**: legacy interface for advanced settings.

---

### 🔹 Task 9 – Task Manager
- Provides real-time system monitoring.
- Key tabs:
  - **Processes**: See running apps/services.
  - **Performance**: CPU, RAM, disk usage metrics.

---

## 🛠️ Commands & Shortcuts
```bash
# Open Run Dialog
Win + R

# Open Local User and Group Management
lusrmgr.msc

# Start Task Manager
Ctrl + Shift + Esc

# Open Control Panel
control
