# 🧩 TryHackMe – DNS in Detail

## 📘 Room Information
- **Path:** Pre-Security → Introduction to Cyber Security → DNS in Detail  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-12  
- **Room Link:** [DNS in Detail – TryHackMe](https://tryhackme.com/room/dnsindetail)

---

> ⚠️ **Disclaimer:**  
> This write-up is for **educational and documentation purposes only**. It does **not contain flags or exact solutions**, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview

This room covers how DNS works in detail. It includes:

- What DNS is  
- How domains are structured (domain hierarchy)  
- DNS record types  
- What happens when a DNS request is made  
- A hands-on practical DNS query  

---

## 🧪 What I Learned

### 🧩 Task 1: What is DNS?

- DNS (Domain Name System) helps us use website names instead of IP addresses.  
- Just like every house has a unique address, every device on the internet has an IP.  
- Example IP: `192.158.23.1` (4 sets of numbers between 0–255).  
- Instead of remembering this, we use domains like `www.example.com`.

---

### 🧠 Task 2: Domain Hierarchy

#### 🔹 TLD (Top-Level Domain)
- The last part of a domain (e.g. `.com`, `.at`, `.de`).  
- Two types:
  - **gTLD:** General purpose (e.g. `.com`, `.org`, `.edu`, `.gov`)  
  - **ccTLD:** Country-specific (e.g. `.ca`, `.uk`, `.at`)  

#### 🔹 Second-Level Domain
- The name before the TLD, like `example` in `example.com`.  
- Limited to 63 characters.  
- Can use letters, numbers, and hyphens (but not at the start or end, or repeated).

#### 🔹 Subdomain
- Comes before the Second-Level Domain, like `admin` in `admin.example.com`.  
- You can use multiple subdomains like `admin.servers.example.com`.  
- Max total length: 253 characters.

---

### 🧠 Task 3: Record Types

#### DNS Isn’t Just for Websites – Common Records:

- **A Record:** Maps domain to an IPv4 address (e.g. `192.163.1.2`)  
- **AAAA Record:** Maps domain to an IPv6 address  
- **CNAME Record:** Points to another domain (e.g. `store.example.com` → `shops.shopify.com`)  
- **MX Record:** Shows which servers handle emails for a domain; has a **priority** in case one fails  
- **TXT Record:** Stores custom text data; often used to verify domain ownership or prevent spam

---

### 🧠 Task 4: Making a Request

#### What Happens During a DNS Request:

1. Your computer checks its **local DNS cache**  
2. If not found, it asks a **Recursive DNS server** (usually your ISP)  
3. If the Recursive DNS server doesn’t know, it asks the **Root DNS servers**  
4. Root servers redirect to the correct **TLD server** (e.g. `.com` server)  
5. TLD server redirects to the **Authoritative Name Server** (stores the actual record)  
6. The result is sent back to the Recursive server, then back to your computer  
7. The result is stored in cache for a limited time (TTL = Time to Live in seconds)

---

### 🧠 Task 5: Practical

- I used commands to build DNS queries and view the results returned.

---

## ✅ Key Takeaways

- DNS makes the internet user-friendly by translating names to IPs  
- Domains follow a clear structure: TLD → Second-Level → Subdomain  
- Different DNS records serve different purposes (A, AAAA, CNAME, MX, TXT)  
- The DNS request process involves multiple steps and servers  
- Caching and TTL help reduce repeated lookups  

---

## 🛠️ Commands

```bash
nslookup --type={recordtype} domainname
