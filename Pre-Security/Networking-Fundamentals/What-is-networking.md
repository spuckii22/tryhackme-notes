# 🧩 TryHackMe – What is Networking?

## 📘 Room Information
- **Path:** Pre-Security → Introduction to Cyber Security → What is Networking?  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-11  
- **Room Link:** [What is Networking? – TryHackMe](https://tryhackme.com/room/whatisnetworking)

---

> ⚠️ **Disclaimer:**  
> This write-up is for **educational and documentation purposes only**. It does **not contain flags or exact solutions**, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview

This room introduces the fundamentals of networking in the context of cybersecurity. It explains how devices communicate, how networks are structured, and how we can identify and interact with devices on a network. Key concepts explored include:

- What networking is  
- What the Internet is  
- How devices are identified (IP and MAC addresses)  
- The use of Ping and ICMP  
- Basics of LAN (Local Area Network) environments  

---

## 🧪 What I Learned

### 🔌 Task 1: What is Networking?
- Networking in computing is similar to human networking—it's about creating connections.  
- A network can consist of just two devices or billions, and includes devices like phones, laptops, and cameras.  
- Networking is foundational to cybersecurity, as it’s the medium over which attacks and defenses occur.

---

### 🌐 Task 2: What is the Internet?
- The Internet is a massive network of smaller, interconnected private and public networks.  
- It allows devices to store, retrieve, and share information globally.  
- Tim Berners-Lee invented the **World Wide Web**, which operates on top of the Internet infrastructure.

---

### 🧠 Task 3: Identifying Devices on a Network

#### 🆔 IP Addresses
- Devices are assigned **IP addresses** to identify them on a network.  
- IPs are divided into four octets (IPv4) with each octet ranging from 0–255.  
- There are **public IPs** (used on the Internet) and **private IPs** (used within local networks).  
- Public IPs are issued by Internet Service Providers (ISPs).  
- The transition to **IPv6** allows more available addresses with 2^128 possibilities.

#### 💾 MAC Addresses
- A **MAC (Media Access Control) address** is a unique identifier assigned to a device’s network interface card (NIC) during manufacturing.  
- It is a 12-character hexadecimal string like `a4:c3:f0:85:ac:2d`.  
- MAC addresses can be spoofed—meaning a device can impersonate another device’s MAC address, which has implications for security.

#### 🧪 Practical Simulation
- The room included a simulation involving network access control using MAC address validation.  
- The exercise demonstrated how MAC spoofing could affect network authorization systems.

---

### 📶 Task 4: Ping (ICMP)
- The **ping** command is a basic networking tool used to test connectivity between devices.  
- It works by sending an ICMP Echo Request and receiving an Echo Reply.  
- It's commonly used to check if a device or website is reachable and how long the response takes (latency).

#### 💻 Example Ping Command
```bash
ping -c 13 12.12.12.1
