# 🧩 TryHackMe – OSI Model

## 📘 Room Information
- **Path:** Pre-Security → Networking Fundamentals → OSI Model  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-12  
- **Room Link:** [OSI Model – TryHackMe](https://tryhackme.com/room/osimodelzi)

---

> ⚠️ **Disclaimer:**  
> This write-up is for **educational and documentation purposes only**. It does **not contain flags or exact solutions**, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview

This room provides a foundational understanding of the **OSI (Open Systems Interconnection) Model**, a 7-layer framework that defines how data is transmitted and interpreted across networks. Each layer has its own responsibilities and builds on the layer beneath it. The room covers:

- What the OSI model is  
- Each individual layer (1 to 7)  
- TCP vs. UDP  
- Encapsulation and routing  
- A practical OSI layer-based challenge  

---

## 📂 Room Walkthrough

### 🔹 Task 1 – What is the OSI Model?

- A conceptual model that standardizes how networked devices send, receive, and process data  
- Promotes **interoperability** between devices of different types or vendors  
- Consists of **7 layers**, each with specific responsibilities  
- Uses **encapsulation**, where each layer adds metadata to the data as it moves down the stack  

**OSI Model Layers (Top to Bottom):**
1. Application  
2. Presentation  
3. Session  
4. Transport  
5. Network  
6. Data Link  
7. Physical  

---

### 🔹 Task 2 – Layer 1: Physical

- Lowest layer; deals with **physical connections** and **electrical signals**  
- Includes cables, switches, and binary transmission (0s and 1s)  

---

### 🔹 Task 3 – Layer 2: Data Link

- Responsible for **MAC addressing** and **framing data**  
- Adds the recipient’s MAC address to packets before transmission  
- Devices use Network Interface Cards (NICs) with factory-set MAC addresses  
- MAC addresses can be **spoofed**, which is relevant for network security  

---

### 🔹 Task 4 – Layer 3: Network

- Focuses on **routing** and **IP addressing**  
- Determines the optimal path for data across networks  
- Includes protocols like **OSPF (Open Shortest Path First)** and **RIP (Routing Information Protocol)**  
- **Routers** operate at this layer  

Routing decisions consider:
- Shortest physical path  
- Reliability (packet loss history)  
- Speed (e.g. copper vs. fiber)  

---

### 🔹 Task 5 – Layer 4: Transport

- Manages **data transmission reliability and flow control**  
- Uses two key protocols: **TCP** and **UDP**

#### ⚙️ TCP (Transmission Control Protocol)
- Reliable and ordered delivery of packets  
- Connection-oriented and performs **error checking**  
- Used for applications like file transfer, email, and web browsing  

✅ Pros:
- Accurate and complete transmission  
- Prevents data flooding  

⚠️ Cons:
- Slower than UDP  
- Requires a persistent connection  

#### 🚀 UDP (User Datagram Protocol)
- Faster but **unreliable**, with no error correction  
- Used in streaming, gaming, VoIP — where speed is more important than perfection  

✅ Pros:
- Fast and lightweight  
- No need for continuous connection  

⚠️ Cons:
- No guarantee of delivery  
- Poor performance on unstable connections  

---

### 🔹 Task 6 – Layer 5: Session

- Responsible for **starting, maintaining, and closing connections** between devices  
- Creates and manages **sessions**  
- Can include **checkpoints** so only lost portions need to be resent if an error occurs  

---

### 🔹 Task 7 – Layer 6: Presentation

- Acts as a **translator** between the application layer and the rest of the OSI model  
- Handles **encryption, compression, and format standardization**  
- Ensures that data is interpretable regardless of software differences (e.g. different email clients)  

---

### 🔹 Task 8 – Layer 7: Application

- Closest layer to the **end-user**  
- Includes protocols like **DNS**, **HTTPS**, **FTP**  
- Defines how users interact with networked services via software (e.g. browsers, email apps)  

---

## 🧠 Reflections

- This room helped me **understand the OSI layers more clearly**, especially how TCP differs from UDP  
- Visualizing data flow from one layer to another made the process much easier to grasp  
- I now have a better mental model of how protocols and hardware interact in real-world networking  
- I'd like to revisit **Layer 3 and subnetting** in more detail in another lab  

---

## 🛠️ Tools & Techniques Used

- Conceptual learning of the 7-layer OSI model  
- Analysis of TCP vs. UDP transmission models  
- Practical activity simulating packet travel through OSI layers  

---

