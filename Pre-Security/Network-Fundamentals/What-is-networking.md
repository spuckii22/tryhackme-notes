# 🧩 TryHackMe – What is Networking?

## 📘 Room Information
- **Path:** -> Pre-Security -> Introduction to Cyber Security ->  What is Networking?
- **Difficulty:** Easy 
- **Completed on:** 2025-05-11
- **Room Link:** https://tryhackme.com/room/whatisnetworking

---

## 🔍 Room Overview

> Short summary of the room:
This room is about what is Networking. It included things such as:
> What is Networking?
> What is the Internet?
> Identifying Devices on a Network
> Ping (ICMP)
> LAN

---

## 🔍 Room Walkthrough

- Reading:

** Task 1 - What is Networking? **
> Things connected (friendship circle: similar interests, hoobies, skills, goals, etc.)
> Are everywhere (city's public transportation system, national power grid, meeting and greeting your neighbours, etc.)
> In computing, networking is same idea as the above, just dispersed to technological devices.
> network can be formed by anywhere from 2 devices to billions (laptop, phone, security cameras, etc.)
> very important for cyber security!!

** Task 2 - What is the Internet? **
> giant network consisting of many, many small networks within itself
> repository for storing and sharing information
> the small networks (private networks), networks connecting these small networks (public networks-or internet)
> Devices will use a set of labels to identify themselves on a network
> Tim Berners-Lee invented the World Wide Web (WWW)

** Task 3 - Identifying Devices on Network **
> Humans have (Name and Fingerprints) -> they can change their name but not their fingerprints -> there is always an identity behind it
> Devices have (IP Address, A media access control (MAC) address = serial number)

> ** IP Addresses (Internet Protocol) **
> can be used as a way of identifying a host on a network for a period of time -> IP address can be associated with another device without the IP address changing
> IP address is a set of numbers divided into four octets (1st, 2nd, 3rd and 4th) -> every octat is from 0-255 -> possible IP address (192.168.1.1)
> number is calculated through a technique known as IP addressing & subnetting
> can change from device to device but cannot be active simultaneously more than once within the same network
> follow a set of standards (protocols) -> backbone of networking and force many devices to communicate in the same language
> devices can be both a private and public network -> depending on where they are will determine what type of IP address they have
> Public address is used to identify the device on the Internet vs. private address is used to identify a device amongst other devices
> devices communicate with each other using the private IP addresses -> any data sent to the internet will be identified by the same public IP address (e.g. 86.157.52.21)
> Public IP addresses are given by your Internet Service Provider (ISP)
> Version of the Internet Protocol addressing scheme (IPv4) = numbering system using 2^32 IP addresses (4.29 billion)
>
> ** IPv6 ** is a new iteratino of the Internet Protocol addressing scheme to help tackle the issue of public addresses already in use
> Supports up to 2^128 IP addresses (340 trillion-plus) and more efficient due to new methodologies

** MAC addresses (Media access control) **
> Devices on a network will all have a physical network interface (microchip board found on the device's motherboard)
> This network interface is assigned a unique address at the factory it was build (MAC address)
> twelve-character hexadecimal number (base sixteen numbering system) split into two's and seperated by a colon (a4:c3:f0:85:ac:2d)
> can be faked or "spoofed" -> spoofing occurs when a networked device pretends to identify as another using its MAC address (assume that the device is trustworthy)
> e.g. A firewall is configured to allow any communication going to and from the MAC address of the admin -> if a device were to pretend or spoof this MAC address, the firewall would think that it is communicating with the admin device

** Practical **
> simulated hotel Wi-Fi network where you have to pay for the service (Bob's packets are not allowed; Alice's packets are because she paid)
> I have to change Bob's MAC address to the same as Alice's
> got the flag!

** Task 4: Ping (ICMP) **
> one of the most fundamental network tools available to us
> Uses ICMP (Internet Control Message Protocol) packets to determine the performance of a connection between devices (does the connection exists or is reliable)
> Time taken for ICMP packets to travel between devices is measured by ping -> using ICMP's echo packet and then ICMP's echo reply from target device
> can be performed against devices on a network, such as your home network or resources like websites (Syntax: ping <IP address/website URL>)

** Practical **
> ping address of "8.8.8.8" -> ping -c 4 8.8.8.8 (-c is for the amount of pings in this example 4 times)
> enter flag

## 🛠️ Tools  & Techniques Used
> Ping


 ## 🛠️ Commands



