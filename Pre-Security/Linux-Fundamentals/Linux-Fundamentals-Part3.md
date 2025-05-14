# 🧩 TryHackMe – Linux Fundamentals (Part 3)

## 📘 Room Information
- **Path:** Pre-Security → Linux Fundamentals → Linux Fundamentals Part 3  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-14  
- **Room Link:** [Linux Fundamentals Part 3 – TryHackMe](https://tryhackme.com/room/linuxfundamentalspart3)

---

> ⚠️ **Disclaimer:**  
> This write-up is for **educational and documentation purposes only**. It does **not contain flags or exact solutions**, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview
This room covers:
- Terminal text editors (`nano`, `vim`)
- Useful Linux utilities (`scp`, `wget`, `http.server`)
- Process management and backgrounding
- Automation via `cron`
- Package management using `apt`
- System logging under `/var/log`

---

## 📂 Room Walkthrough

---

### 🔹 Task 1 – Introduction
- Just basic introductory information.

---

### 🔹 Task 2 – Deploying Linux Machine
- Set up virtual environment by starting the Attacker and Target machines.
- SSH into the target machine using the provided credentials.

---

### 🔹 Task 3 – Terminal Text Editors

#### 📝 Nano
- Basic terminal text editor.
- Create or edit a file: `nano filename`
- Features:
  - Search (Ctrl + W)
  - Copy/Paste (Ctrl + ^ and Ctrl + K/U)
  - Jump to line number (Ctrl + _)
  - Line info (displayed at bottom)

#### ⚙️ Vim
- More advanced, highly customizable text editor.
- Benefits:
  - Works in all terminals
  - Syntax highlighting
  - Keyboard shortcuts can be customized
  - Large ecosystem of documentation, plugins, and cheatsheets
 
---

### 🔹 Task 4 – General/Useful Utilities

#### 🌐 Downloading Files with `wget`
- Allows downloading from the web using HTTP/HTTPS.
- Example:  
  `wget https://assets.example.com/basic/linux/example.txt`

#### 🔄 Transferring Files with `scp` (Secure Copy)
- Uses SSH for secure file transfer between systems.
- **From remote to local:**  
  `scp user@IP:/path/file.txt newfilename`
- **From local to remote:**  
  `scp file.txt user@IP:/path/newfilename`

#### 🌍 Serving Files with `http.server`
- Use Python's built-in HTTP server to share files.
- Start server in the target folder:  
  `python3 -m http.server`
- On another machine, download with:  
  `wget http://IP:PORT/filename`
- ⚠️ No file indexing — must know exact file path/name.

---

### 🔹 Task 5 – Processes 101

#### 🧠 What is a Process?
- A running program managed by the Linux kernel.
- Each process has a unique **PID** (Process ID).

#### 🔎 Viewing Processes
- `ps` – shows user processes.
- `ps aux` – shows all system/user processes.
- `top` – real-time dynamic view of running processes.

#### 🧹 Managing Processes
- `kill PID` – terminate a process.
- Signals:
  - `SIGTERM` – graceful stop (default).
  - `SIGKILL` – immediate kill.
  - `SIGSTOP` – pause/suspend.

#### ⚙️ How Processes Start
- System uses **namespaces** to isolate processes.
- All processes start from `systemd` (PID 1) at boot.

#### 🔁 Starting Services on Boot
- Controlled via `systemctl`:
  - Start: `systemctl start service`
  - Stop: `systemctl stop service`
  - Enable: `systemctl enable service`
  - Disable: `systemctl disable service`

#### 🌓 Foreground & Background Processes
- Foreground: default execution (e.g. `echo`).
- Background: use `&` or `Ctrl + Z` to suspend.
- Bring back to foreground: `fg`

---

### 🔹 Task 6 – Maintaining Your System: Automation

#### ⏱ What is Cron?
- `cron` is a system daemon used to schedule commands or scripts to run automatically at specified times and dates.
- It uses a configuration file called `crontab`.

#### 📄 Crontab Syntax
A `crontab` entry has **six fields**:
```
* * * * * command_to_run
- - - - -
| | | | |
| | | | +----- Day of the week (0 - 6) (Sunday = 0)
| | | +------- Month (1 - 12)
| | +--------- Day of the month (1 - 31)
| +----------- Hour (0 - 23)
+------------- Minute (0 - 59)
```

#### 📌 Example – Run backup every 12 hours
```bash
0 */12 * * * cp -R /home/example/Documents /var/backups/
```

- `0 */12 * * *` → means every 12 hours at minute 0.
- The `cp -R` command copies recursively from `/home/example/Documents` to `/var/backups/`.

#### ✍️ Edit Crontab
```bash
crontab -e
```
- Opens your personal crontab file in the default text editor.
- You can select nano or vim as your preferred editor.

#### 🪄 Special Time Syntax
- `@reboot` → run at startup
- `@daily` → run once per day
- `@weekly`, `@monthly`, `@yearly`, etc.

#### 💡 Tips
- Use `*` as a wildcard if you want to ignore a field.
- `crontab -l` → list current cron jobs.
---

### 🔹 Task 7 – Maintaining Your System: Package Management

#### 📦 What Are Packages?
- A **package** is a collection of files bundled together for easy installation, configuration, and removal.
- Most Linux distributions use package managers to handle these packages.
- Ubuntu uses **APT** (Advanced Package Tool).

---

#### 🧰 Using APT

- `apt` is the command-line tool used to manage software:
  - `apt update` → updates the list of available packages.
  - `apt upgrade` → upgrades all installed packages to the newest version.
  - `apt install <package>` → installs a new package.
  - `apt remove <package>` → removes an installed package.
  - `apt purge <package>` → removes a package and its configuration files.

---

#### 🗂 Repositories and Software Sources
- Packages are downloaded from **repositories**, which are servers storing available software.
- Ubuntu uses official repos, but you can add custom repos to access third-party software.

---

#### 🔐 GPG Keys
- **GPG keys** verify the authenticity of repositories and packages.
- Without the correct GPG key, you won’t be able to install from the repo (for security reasons).

##### 🛠 Example – Add a third-party text editor repo:
1. Add the GPG key:
   ```bash
   wget -qO - http://example.com/gpg.key | sudo apt-key add -
   ```

2. Add the repository source:
   ```bash
   sudo nano /etc/apt/sources.list.d/text-editor.list
   ```
   Add:
   ```
   deb http://example.com/ubuntu stable main
   ```

3. Update the package list:
   ```bash
   sudo apt update
   ```

4. Install the package:
   ```bash
   sudo apt install text-editor
   ```

---

#### 🧹 Removing Software and Repos
- Remove the package:
  ```bash
  sudo apt remove text-editor
  ```

- Delete the repository file:
  ```bash
  sudo rm /etc/apt/sources.list.d/text-editor.list
  ```

---

#### 💡 Key Benefits of APT
- Automatically checks for updates.
- Ensures dependencies are resolved.
- Verifies integrity via GPG keys.

---

### 🔹 Task 8 – Maintaining Your System: Logs

#### 📁 Where Are Logs Stored?
- Most system logs are stored in the directory:
  ```
  /var/log
  ```
- This folder contains log files created by applications and services running on the system.

---

#### 📄 Examples of Important Log Files:
| File Name        | Description                                      |
|------------------|--------------------------------------------------|
| `/var/log/syslog`| General messages, including boot info & system events |
| `/var/log/auth.log` | Authentication logs (login attempts, sudo)    |
| `/var/log/apache2/access.log` | Access logs from Apache web server |
| `/var/log/apache2/error.log`  | Error logs from Apache web server  |

---

#### 🔄 Log Rotation
- Linux systems **automatically manage logs** to prevent them from filling up your storage.
- This process is known as **log rotation** and is handled by utilities like:
  - `logrotate`
- Rotated logs are usually compressed and renamed, e.g.:
  ```
  syslog.1
  syslog.2.gz
  ```

---

#### 👀 Why Are Logs Important?
- Logs are essential for:
  - 🔧 Troubleshooting services and applications
  - 🔍 Investigating unauthorized access attempts or suspicious behavior
  - 📊 Monitoring system health and performance

---

#### 🧠 Access vs. Error Logs
- **Access Logs**: Log normal activity like visits to a website or usage of an API.
- **Error Logs**: Log problems or failed events (e.g. failed login, server errors).

---

#### 🔐 Pentesting Tip
- Logs can reveal sensitive information about services or usernames.
- Reviewing logs is a key part of **post-exploitation enumeration**.

