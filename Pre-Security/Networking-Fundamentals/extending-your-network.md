# 🧩 TryHackMe – Extending your Network

## 📘 Room Information
- **Path:** Pre-Security → Introduction to Cyber Security → Extending your Network  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-12  
- **Room Link:** [Extending your Network – TryHackMe](https://tryhackme.com/room/extendingyournetwork)

---

> ⚠️ **Disclaimer:**  
> This write-up is for **educational and documentation purposes only**. It does **not contain exact solutions**, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview

This room explains how to extend a network securely and efficiently. It covers:

- Port forwarding  
- Firewalls and their types  
- VPN basics  
- LAN networking devices (routers and switches)  
- Two practical tasks to apply what was learned  

---

## 🧪 What I Learned

### 🔌 Task 1: Introduction to Port Forwarding

- Port forwarding makes services (like web servers) accessible from the Internet.  
- Without port forwarding, apps are only available within the same local network (intranet).  
- Port forwarding is set up on the router to open specific ports.  

---

### 🔥 Task 2: Firewalls 101

- A firewall is like border security for a network — it controls what traffic can enter or leave.  
- Admins can allow or block traffic based on:
  - Where it's from  
  - Where it's going  
  - Which port it's using  
  - What protocol it's using (TCP, UDP, or both)

#### Types of Firewalls:

**Stateful Firewalls**
- Look at the full connection, not just single packets  
- More dynamic but use more system resources  
- Can block a whole device based on behavior  

**Stateless Firewalls**
- Use simple rules to check each packet  
- Don’t track the whole connection  
- Use fewer resources but are less smart  
- Good for large traffic (like DDoS protection)  

---

### 🧪 Task 3: Practical – Firewall

- I configured a firewall to stop malicious packets from reaching a web server.

---

### 🔐 Task 4: VPN Basics

- A **VPN (Virtual Private Network)** connects devices from different locations using a secure tunnel over the Internet.  
- Devices in different networks can act as if they’re in the same private network.  

#### Benefits of VPNs:
- Connects remote offices or users  
- Provides privacy through encryption  
- Gives anonymity — useful for journalists or people in restricted countries  

#### VPN Technologies:

- **PPP:** Handles authentication and encryption inside a network  
- **PPTP:** Allows PPP data to travel across networks — not very secure  
- **IPSec:** Uses IP for secure communication — harder to set up, but stronger encryption  

---

### 🌐 Task 5: LAN Networking Devices

#### 🛣️ What is a Router?

- A router connects different networks and helps data travel between them  
- It finds the best path for the data  
- Usually configurable through a web interface  
- Works at OSI Layer 3 (Network layer)

#### 🔀 What is a Switch?

- A switch connects multiple devices using Ethernet cables  
- Works at Layer 2 or Layer 3 of the OSI model  

**Layer 2 Switch:**
- Uses MAC addresses to send data (called frames) to the correct device  
- Cannot route data between networks  

**Layer 3 Switch:**
- Can act like a router  
- Uses IP addresses to route data and send frames  

---

### 🧪 Task 6: Practical – Network Simulator

- I used a network simulator to see how a packet travels from point A to point B, step by step.  

---

