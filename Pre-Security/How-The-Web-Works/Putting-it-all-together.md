# 🧩 TryHackMe – Putting it all together

## 📘 Room Information
- **Path:** Pre-Security → How the Web Works → Putting it all together  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-13  
- **Room Link:** https://tryhackme.com/room/puttingitalltogether

---

> ⚠️ **Disclaimer:**  
> This write-up is for educational and documentation purposes only. It does not contain flags or exact solutions, in accordance with TryHackMe’s Terms of Use.

---

## 🔍 Room Overview

This room summarizes all the knowledge gained in the previous web modules. It combines core networking and web technologies to explain how real-world websites operate. Topics include DNS, HTTP, load balancing, CDNs, web servers, databases, and common security setups.

---

## 📂 Room Walkthrough

### 🔹 Task 1 – Putting it All Together

- When requesting a website, the process begins by resolving the server's IP address using DNS.
- The browser then communicates with the web server using the HTTP protocol.
- The server responds with HTML, CSS, JavaScript, images, and other content which the browser uses to render the page.

---

### 🔹 Task 2 – Other Components

#### 🔸 Load Balancers

- Handle high traffic by distributing requests across multiple backend servers.
- Provide high availability and failover in case one server becomes unresponsive.
- Use algorithms like round-robin or weighted balancing to manage traffic efficiently.
- Perform regular health checks to ensure servers are functioning before sending them traffic.

#### 🔸 CDNs (Content Delivery Networks)

- Distribute static content (e.g. CSS, JS, images, videos) across global servers.
- Serve data from the closest server to reduce latency and improve user experience.
- Example: Like Netflix streaming movies from a nearby data center rather than a distant one.

#### 🔸 Databases

- Store and retrieve user and application data.
- Can range from flat files to complex clustered database servers.
- Common database systems include MySQL, PostgreSQL, MongoDB, and MSSQL.

#### 🔸 WAF (Web Application Firewall)

- Acts as a protective layer between incoming web traffic and the web server.
- Detects and blocks malicious requests (e.g. DDoS, injection attacks).
- Implements rate limiting to restrict request volume from specific IPs.
- Drops suspicious requests before they reach the application.

---

### 🔹 Task 3 – How Web Servers Work

#### 🔸 What is a Web Server?

- Software that listens for incoming HTTP connections and delivers web content.
- Examples: Apache, Nginx, IIS, NodeJS.
- Delivers content from a configured root directory.

#### 🔸 Virtual Hosts

- Allow a single web server to host multiple websites/domains.
- Uses the `Host` header in HTTP to determine which site to serve.
- Configured through virtual host files mapping domains to specific root directories.

#### 🔸 Static vs. Dynamic Content

- **Static Content:** Unchanging files like images, stylesheets, and scripts served directly as-is.
- **Dynamic Content:** Content generated on-the-fly (e.g. blog feeds), depending on user input or backend logic.

#### 🔸 Scripting and Backend Languages

- Backend logic is handled by programming languages like PHP, Python, Ruby, and NodeJS.
- These can process user input, access databases, and generate dynamic responses.

---

### 🔹 Task 4 – Quiz

- Final quiz reviewing Requests :

---

## ✅ Key Takeaways

- Building and hosting a modern website involves multiple systems working together: DNS, HTTP, servers, databases, load balancers, and firewalls.  
- Tools like CDNs and WAFs improve performance and security.  
- Frontend and backend responsibilities are clearly separated and serve different purposes.  
- Dynamic websites rely heavily on backend logic and scripting to deliver tailored content.

---


