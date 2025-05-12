# 🧩 TryHackMe – Intro to LAN

## 📘 Room Information
- **Path:** Pre-Security → Introduction to Cyber Security → Intro to LAN  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-11  
- **Room Link:** [Intro to LAN – TryHackMe](https://tryhackme.com/room/introtolan)

---

> ⚠️ **Disclaimer:**  
> This write-up is for **educational and documentation purposes only**. It does **not contain flags or exact solutions**, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview

This room provides an introduction to **Local Area Networks (LANs)**, explaining how network topologies work, what routers and switches do, and how subnetting, ARP, and DHCP enable communication across devices. It also includes practical simulations to demonstrate the strengths and weaknesses of different network designs.

---

## 🧪 What I Learned

### 🧩 Task 1: LAN Topologies

**Topology** refers to the physical or logical structure of a network.

#### ⭐ Star Topology
- Devices are connected to a central hub or switch.  
- Easy to scale and isolate issues.  
- A single point of failure: if the central device fails, the entire network is impacted.  
- Requires more hardware and cabling.

#### 🚌 Bus Topology
- All devices connect to a single central cable.  
- Simple and cost-effective.  
- Prone to bottlenecks and hard to troubleshoot.  
- If the main cable fails, communication is disrupted.

#### 🔁 Ring Topology
- Devices form a loop, with data circulating through each node.  
- Low hardware requirements and predictable traffic flow.  
- Failure at one point can bring down the entire network.

#### 🔌 What is a Switch?
- Aggregates multiple devices using Ethernet connections.  
- Tracks device MAC addresses and sends data only to the intended recipient.  
- Improves efficiency compared to older hubs.  
- Can be paired with routers to create redundancy in the network.

#### 🌐 What is a Router?
- Connects different networks and manages data transmission between them.  
- Determines the best path for data to travel.  
- Essential for routing traffic from local networks to the internet.

#### 🧪 Practical Simulation
I explored how each topology handles failure:
- A broken cable in a ring topology caused complete network failure.  
- Bus topology slowed down or failed under heavy simultaneous traffic.  
- In a star topology, failure of the central switch caused loss of communication.

---

### 🧠 Task 2: A Primer on Subnetting

**Subnetting** divides a larger network into smaller, manageable sections (subnets), improving efficiency, control, and security.

Subnets use IP addresses in three key ways:

- **Network Address**  
  - Identifies the start of a subnet  
  - Example: `192.168.1.0`  
- **Host Address**  
  - Assigned to individual devices within the subnet  
  - Example: `192.168.1.100`  
- **Default Gateway**  
  - The route out of the local subnet (typically a router)  
  - Example: `192.168.1.254`  

Subnet masks (like `255.255.255.0`) help define how much of the IP address refers to the network vs. the host.

**Real-world Example:**  
A café may use two subnets—one for staff and one for guests—to isolate critical devices from public access.

---

### 📡 Task 3: ARP (Address Resolution Protocol)

**ARP** allows devices on a network to match IP addresses with physical (MAC) addresses.  
Each device keeps a cache that stores these mappings.

**How it works:**
- A device broadcasts an **ARP Request**: “Who has this IP address?”  
- The correct device replies with its MAC address (**ARP Reply**)  
- The requesting device stores this info in its ARP cache for future use

**Analogy:** Asking at a hotel who lives in Room 33 and noting the answer.

---

### 📦 Task 4: DHCP (Dynamic Host Configuration Protocol)

**DHCP** allows devices to obtain an IP address automatically when they join a network.

The process includes:
1. **DHCP Discover** – Device requests an IP  
2. **DHCP Offer** – Server offers an available IP  
3. **DHCP Request** – Device accepts the offer  
4. **DHCP Acknowledgment (ACK)** – Server confirms assignment

This automation makes IP address management easier, especially in larger networks.

---

## ✅ Key Takeaways

- **Topologies:** Different designs have trade-offs in cost, scalability, and reliability  
- **Switch vs. Router:** Switches connect devices within a LAN; routers connect different networks  
- **Subnetting:** Like dividing a city into neighborhoods; helps with efficiency and control  
- **ARP:** Resolves IP to MAC addresses for internal device communication  
- **DHCP:** Automates IP address assignment for ease of use and scalability

---

## 🛠️ Tools & Techniques Used

- Conceptual understanding and simulation of:
  - Network topologies  
  - IP addressing and subnetting  
  - ARP request/reply  
  - DHCP configuration and negotiation

---

## 🧠 No Commands Required
This room focused primarily on concepts and interactive visual simulations rather than command-line input.
