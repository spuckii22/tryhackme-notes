# 🧩 TryHackMe – Windows Fundamentals Part 3

## 📘 Room Information
- **Path:** Pre-Security → Windows Fundamentals → Windows Fundamentals Part 3  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-14  
- **Room Link:** [TryHackMe – Windows Fundamentals Part 3](https://tryhackme.com/room/windowsfundamentals3xzx)

---

> ⚠️ **Disclaimer:**  
> This write-up is for educational and documentation purposes only. It does not include flags or exact solutions, in line with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview
This room continues the Windows Fundamentals series and introduces key built-in security features of the Windows OS.

**Tasks:**
1. Introduction  
2. Windows Updates  
3. Windows Security  
4. Virus & Threat Protection  
5. Firewall & Network Protection  
6. App & Browser Control  
7. Device Security  
8. BitLocker  
9. Volume Shadow Copy Service  
10. Conclusion

---

## 📂 Room Walkthrough

### 🔹 Task 1 – Introduction
- Quick setup instructions for the virtual environment.

---

### 🔹 Task 2 – Windows Updates
- Windows Updates provide important patches, security fixes, and new features for both the OS and Microsoft applications.

---

### 🔹 Task 3 – Windows Security
- The Windows Security dashboard manages various protection tools for your system.

**Main areas include:**
- Virus & Threat Protection  
- Firewall & Network Protection  
- App & Browser Control  
- Device Security  

**Status indicators:**
- ✅ Green = Everything is fine  
- ⚠️ Yellow = Recommended review  
- ❌ Red = Action needed

---

### 🔹 Task 4 – Virus & Threat Protection

**Sections:**
- **Current Threats**
  - Quick Scan: Scans common malware locations.
  - Full Scan: Checks all files and programs.
  - Custom Scan: Choose specific folders/files to scan.

- **Threat History**
  - Last Scan: Shows most recent scan.
  - Quarantined Threats: Items isolated by Windows Defender.
  - Allowed Threats: Threats the user has allowed.

- **Protection Settings**
  - Real-time Protection: Blocks threats as they occur.
  - Cloud-delivered Protection: Uses cloud-based updates for quicker protection.
  - Automatic Sample Submission: Sends sample files to Microsoft for analysis.
  - Controlled Folder Access: Prevents unauthorized access to critical folders.
  - Exclusions: Lists files/folders that won’t be scanned.
  - Notifications: Configure Defender alert preferences.

- **Updates**
  - Manually check for the latest protection updates.

- **Ransomware Protection**
  - Requires Controlled Folder Access to be turned on.

---

### 🔹 Task 5 – Firewall & Network Protection
- The firewall controls what traffic is allowed in/out of the system.

**Profiles:**
- **Domain:** Used in business networks with domain controllers.  
- **Private:** For trusted home networks.  
- **Public:** For open networks like coffee shops or airports.

---

### 🔹 Task 6 – App & Browser Control
- **SmartScreen:** Protects against malicious websites and downloads.  
- **App & File Check:** Scans programs and files for threats.  
- **Exploit Protection:** Mitigates known attack methods.

---

### 🔹 Task 7 – Device Security

**Core Isolation:**
- Memory Integrity: Blocks malicious code from affecting system processes.

**TPM (Trusted Platform Module):**
- A chip that supports hardware-level security tasks like encryption and authentication.

---

### 🔹 Task 8 – BitLocker
- Built-in Windows tool that encrypts drives to prevent data theft if the device is lost or stolen.

---

### 🔹 Task 9 – Volume Shadow Copy Service
- Creates system restore points or snapshots of files.

**You can:**
- Create restore points  
- Restore the system  
- Configure settings  
- Delete old snapshots  

Malware authors sometimes target these snapshots to prevent system recovery.

---

### 🔹 Task 10 – Conclusion
- The room covered important Windows security tools and how to manage and monitor them effectively.

---

## 🛠️ Commands & Shortcuts
*(None provided for this room)*
