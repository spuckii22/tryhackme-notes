# 🧩 TryHackMe – Intro to LAN

## 📘 Room Information
- **Path:** -> Pre-Security -> Introduction to Cyber Security ->  Intro to LAN
- **Difficulty:** Easy 
- **Completed on:** 2025-05-11
- **Room Link:** https://tryhackme.com/room/introtolan

---

## 🔍 Room Overview

> Short summary of the room:
This room is about an introduction to LAN. It is about:
> Introducing LAN Topologies (Star Topology, Bus Topology and Ring Topology)
> What is a Switch?
> What is a router?
> Pracitcal stuff
> A primer of Subnetting
> ARP
> DHCP


---

## 🔍 Room Walkthrough

### Task 1 - Introducing LAN Topologies 
> topology = design or look of the network

** Different Topologies: **

####  Star Topology 
- devices are individually connected via a central networking device such as a switch or hub
- most commonly found today because of its reliability and scalability
- any information sent to a device is sent via the central device

** Disadvantages: **
- more cabling and purchase of networking equipment is required -> more expensive than any of the other topologies
- the more netwworks scales the more maintenance is required -> can make troubleshooting faults much harder
- still prone to failure -> centralised hardware fails -> devices will no longer be able to send or receive data
  
- Advantages: more scalable in nature (very easy to add more devices)

####  Bus Topology 
- relies upon a single connection (backbone cable)
- similar to the leaf off a tree -> devices (leaves) stem from where the branches are on this cable
- all data destined for each device travels along the same cable -> very quickly prone to becoming slow and bottlenecked if devices simultaneously request data
- bottleneck results in very difficult troubleshooting (difficult to identify which device is experiencing issues)
- one of the easier and more cost-efficient topologies
- little redundancy in place in case of failures -> if cable were to break -> devices can no longer receive or transmit data along the bus

####  Ring Topology (Token Topology) 
- Devices are connected directly to each other to form a loop -> little cabling required and less dependence on dedicated hardware
- works by sending data across the loop until it reaches the destined device, using other devices along the loop to forward the data
- device will only send received data from another device if it does not have any to send itself -> if it happens that the device has to send data itself, it will send its own data first
- only one direction for data to travel -> fairly easy to troubleshoot
- not efficient way -> data has to travel across the network (e.g. if last device is the destined one)
- less prone to bottlenecks -> because no large amounts of traffic are travelling across the network at any one time
- cut cable or broken device will result in entire network breaking

####  What is a Switch? 
- dedicated devices within a network to aggregate multiple other devices (computers, printers, etc.) using ethernet
- devices plug into a switch's port
- usually found in larger networks
- more efficient than hubs/repeaters
- keep track of what device is connected to which port -> when they receive a packet, instead of repeating that packet to every port like a hub would do, it send it only to the intended target
- Switches and Routers can be connected to one another -> increases the rendundancy (the reliability) of a network by adding multiple paths for data to take -> e.g. if one path goes down
- may reduce overall performance but there is no downtime

#### What is a Router? 
- device which job is to connect networks and pass data between them (routing)
- Routing = label given to the process of data travelling across networks -> creating a path between networks so data can be successfully delivered
- Routing is usefull when devices are connected by many paths

#### Practical 
- lab takes me through flaws in different network topologies (Ring, Bus, Star Topology)
- see what happens if we cut the cable on the Ring Topolgy -> it breaks everything because packets no longer travel around the network and no devices can talk to each other
- see what happens if we send to many packets at the same time (Bus Topology) -> it also breaks and the Bus network is down
- see what happens if we break the switch (Star Topology) -> network is down because normally the devices are communicate via the switch 

### Task 2: A Primer of Subnetting 
- Subnetting = splitting up a network into smaller networks within itself (Accounting, HR, Finance) -> for deciding who gets what "slice"
- Network admins use subnetting to categorise and assign specific parts of a network
- Subnetting is achieved by splitting up the number of hosts that can fit within the network -> subnet mask -> also represented as a number of four bytes (32 bits) ranging from 0-255

- Subnets use IP addresses in three different ways:
  - Identify the network address
  - identify the host address
  - identify the default gateway
 
  - ** Network Address **
    - ** Purpose: ** identifies the start of the actual network and is used to identify a network's existence
    - ** Explanation: ** e.g. device with IP address (192.168.1.100) will be on the network identified by 192.168.1.0
    - ** Example: ** 192.168.1.0
   
  - ** Host Address **
    - ** Purpose: ** identify device on the subnet
    - ** Explanation: ** e.g device will have network address of 192.168.1.1 
    - ** Example: ** 192.168.1.100

   - ** Default Gateway **
    - ** Purpose: ** special address assigned to a device on a network that is capable of sending information to another network
    - ** Explanation: ** Any data that needs to go to a device that isn't on the same network (i.e. isn't on 192.168.1.0) will be sent to this device. -> can use any host address but usually use either the first or last host address (.1 or .254)
    - ** Example: ** 192.168.1.254

  - On small networks (home) wou will be on one subnet (unlikely that you need more than 254 devices connected at one time)
  - Provides benefits (Efficiency, Security, Full control)

  - ** Example - Café on the street will have two networks **:
  - One for employees, cash registers, and other devices for the facility
  - One for the general public to use as a hotspot
  - ** Subnetting ** allows you to seperate these two cases from eatch other whilst having the benefits of a connection to larger networks such as the internet
 
### Task 3: ARP (Address Resolution Protocol)
- technology that is responsible for allowing devices to identify themselves on a network
- allows a device to associate its MAC address with an IP address on the network -> each device on a network will keep a log of the MAC addresses associated with other devices

- ** How does ARP Work? **
    - each device within a network has a ledger to store information on (cache) -> cache stores the identifiers of other devices on the network
    - ** Example ** -> You ask in the hotel who lives in the room 33 it says "John" and you note it down so you remember
    - In order to map these two identifiers together (IP and MAC address), ARP sends two types of messages:
      1. ARP Request 
      2. ARP Reply
     
      - message is broadcasted on the network to other devices asking: "What is the mac address that owns this IP address?" -> Device responds if it has this IP and will send an ARP reply with its MAC address
      - Requesting device can now remember this mapping and store it in its ARP cache for future use.
     
  ### Task 4: DHCP (Dynamic Host Configuration Protocol)
  - IPs can be assigned either manually (by entering them physically into device) or automatically by using a DHCP server
  - when device connects to a network, if it has not already been manually assigned an IP, it sends out a request (DHCP Discover) to see if any DHCP servers are on the network
  - DHCP server replies back with an IP the device could use (DHCP offer)
  - Device then sends a reply confirming it wans the offered IP (DHCP Request)
  - DHCP server sends a reply acknowledging this has been completed, and the device can start using the IP (DHCP ACK)
 
  - ** Example **
  - DHCP Discover -> Device = "Hey I am new here, is there anyone who can give me an IP Address?
  - DHCP Offer -> DHCP replies = "Hey! Sure thing, yo ucan have 192.169.1.10"
  - DHCP Request -> Device = "Yes, that would be brilliant!"
  - DHCP ACK -> DHCP = "Okay great. You can use that IP Address for the next 24 hours"

    
## Key Takeaways
- Different Topologies have different advantages and disadvantages (Costs, etc.)
- Router vs. Switch -> Router conects different networks and routes data; Switch connects multiple devices within a LAN
- Subnetting = dividng a larger network (like a city) into smaller parts (neighborhoods) so they are easier to manage and secure
- Network Address = neighborhood name -> identifies the ** entire subnet ** or block of IPs and is not assignable to devices
- Host Address = house numbers -> usable IPs assigned to devices
- Default Gateway = main road out -> router's IP on your network to connect your local subnet to the internet or other networks
- DHCP use cases and how it works (DHCP Disover, DHCP Offer, DHCP Request, DHCP ACK)

## 🛠️ Tools  & Techniques Used



## 🛠️ Commands



