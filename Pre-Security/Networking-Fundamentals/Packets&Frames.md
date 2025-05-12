# 🧩 TryHackMe – Packets & Frames

## 📘 Room Information
- **Path:** Pre-Security → Networking Fundamentals → Packets & Frames  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-12  
- **Room Link:** [Packets & Frames – TryHackMe](https://tryhackme.com/room/packetsframes)

---

> ⚠️ **Disclaimer:**  
> This write-up is for **educational and documentation purposes only**. It does **not contain exact solutions**, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview

This room explains what packets and frames are and how they are used to send data across a network. It covers:

- What packets and frames are  
- The TCP/IP model and the three-way handshake  
- How UDP works  
- Ports and common port numbers  
- Practical tasks to reinforce the concepts  

---

## 📂 Room Walkthrough

### 🔹 Task 1 – What are Packets and Frames

- Packets are small pieces of data that form larger messages.  
- Frames exist on OSI Layer 2 (Data Link) and don’t include IP addresses.  
- Think of a frame like an envelope inside a packet — it helps deliver data efficiently.  
- The process of adding information to the data is called **encapsulation**.  
- Example: When you load an image, it’s sent in small pieces, not all at once.  
- Packets follow specific formats depending on their type.  
- Networking uses rules (protocols) for how data is handled.  

#### Headers in a Packet:
- **Time to Live (TTL):** Makes sure the packet doesn’t stay on the network forever.  
- **Checksum:** Checks for errors in the data.  
- **Source Address:** Where the packet came from.  
- **Destination Address:** Where the packet is going.

---

### 🔹 Task 2 – TCP/IP and the Three-Way Handshake

- TCP is a **connection-based** protocol, meaning it needs to set up a connection before sending data.  
- It’s part of the TCP/IP model (Application, Transport, Internet, Network Interface).  
- Adds headers at each layer (encapsulation), and removes them at the other end (decapsulation).  
- TCP makes sure that all data is received in the correct order.

#### Advantages of TCP:
- Makes sure all data is delivered correctly.  
- Helps devices avoid being flooded.  
- Reliable and accurate.

#### Disadvantages:
- Slower than UDP.  
- If a part of the data is lost, it has to be sent again.  
- Uses more system resources.

#### TCP Headers:
- **Source Port:** Random port used by the sender.  
- **Destination Port:** Port used by the app or service on the receiving end.  
- **Source IP / Destination IP:** Where the packet is coming from and going to.  
- **Sequence Number / Acknowledgement Number:** Used to keep track of the order of data.  
- **Checksum:** Makes sure data hasn’t changed during transfer.  
- **Data:** The actual content being sent.  
- **Flag:** Controls how the connection is handled.

#### TCP Three-Way Handshake:
| Step | Message   | Description                                                |
|------|-----------|------------------------------------------------------------|
| 1    | SYN       | Client starts the connection.                              |
| 2    | SYN/ACK   | Server agrees to the connection.                           |
| 3    | ACK       | Client confirms.                                           |
| 4    | DATA      | Actual data is sent.                                       |
| 5    | FIN       | Connection is closed cleanly.                              |
| #    | RST       | Used if something goes wrong — ends the connection abruptly.|

- Devices use **sequence numbers** to agree on the order of data.

#### TCP Connection Closing:
- When all data has been sent, one side sends a **FIN** packet.  
- The other side confirms, and the connection ends.  

---

### 🔹 Task 3 – Practical

- I helped two people communicate by reassembling a broken TCP handshake in the correct order.  

---

### 🔹 Task 4 – UDP/IP

- UDP is a **stateless** protocol — it doesn’t need a connection before sending data.  
- It’s faster than TCP but doesn’t guarantee that data is received.  
- Useful for things like streaming where some data loss is okay.

#### Advantages of UDP:
- Very fast  
- Doesn’t hold connections open  
- Leaves control to the application

#### Disadvantages:
- Doesn’t check if data arrives  
- Bad connections can cause problems  
- Less reliable

#### UDP Headers:
- **Time to Live (TTL):** Stops packets from staying too long on the network  
- **Source / Destination Address:** Where the data is from and going to  
- **Source / Destination Port:** Port used to send and receive data  
- **Data:** The actual content

---

### 🔹 Task 5 – Ports (Practical)

- Ports are like doors — they allow data to enter or leave a device in a specific way.  
- Each port is identified by a number (0–65535).  
- Ports help devices know which app should receive which data.  
- Most services use **standard ports** so everything works together.

#### Common Port Numbers:
| Service | Port | Description |
|---------|------|-------------|
| FTP     | 21   | File sharing  
| SSH     | 22   | Secure login  
| HTTP    | 80   | Websites (unsecure)  
| HTTPS   | 443  | Secure websites  
| SMB     | 445  | File and device sharing (e.g. printers)  
| RDP     | 3389 | Remote desktop interface  

---

## 🧠 Reflections

- I understood the difference between TCP and UDP better after this room.  
- The three-way handshake steps were easy to follow in the visual lab.  
- I now know what ports are and why they’re important when sending or receiving data.  

---

## 🛠️ Tools & Techniques Used

- **Netcat (nc):** Used to set up a basic raw connection to a given IP and port.
