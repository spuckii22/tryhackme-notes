# 🧩 TryHackMe – HTTP in Detail

## 📘 Room Information
- **Path:** Pre-Security → Introduction to Cyber Security → HTTP in Detail  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-12  
- **Room Link:** [HTTP in Detail – TryHackMe](https://tryhackme.com/room/httpindetail)

---

> ⚠️ **Disclaimer:**  
> This write-up is for **educational and documentation purposes only**. It does **not contain exact solutions**, in accordance with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview

This room explains how HTTP and HTTPS work, how websites send and receive data, and what happens behind the scenes in a browser. It covers:

- HTTP vs. HTTPS  
- Requests, responses, methods, and status codes  
- Headers and cookies  
- Making manual requests  
- Practical exercises  

---

## 🧪 What I Learned

### 🧩 Task 1: What is HTTP(S)?

- **HTTP (HyperText Transfer Protocol)** is how websites send data like HTML, images, and videos.  
- **HTTPS** is the secure version — it encrypts the data and ensures you're talking to the correct server.  

---

### 🧩 Task 2: Requests and Responses

- Browsers send requests for resources (HTML, images, etc.) and receive responses.  
- A **URL** tells the browser what to request and where.

#### Parts of a URL:
- **Scheme:** Protocol (HTTP, HTTPS, FTP)  
- **User:** (Optional) login info (user:password)  
- **Host:** Domain or IP (e.g. example.com)  
- **Port:** Default is 80 (HTTP) or 443 (HTTPS), but can be custom  
- **Path:** File or folder (e.g. /view-shop)  
- **Query String:** Extra info (e.g. ?id=1)  
- **Fragment:** Link to part of the page (e.g. #task3)  

You can send a request as simple as `GET / HTTP/1.1`, but headers usually carry extra important info.

---

### 🧩 Task 3: HTTP Methods

- **GET:** Retrieve information  
- **POST:** Send new data (e.g. form submission)  
- **PUT:** Update existing data  
- **DELETE:** Remove data  

---

### 🧩 Task 4: HTTP Status Codes

Status codes tell you what happened with your request.

#### Code Ranges:
- **100–199:** Informational (rare)  
- **200–299:** Success  
- **300–399:** Redirection  
- **400–499:** Client error  
- **500–599:** Server error  

#### Common Status Codes:
- **200 OK:** Successful  
- **201 Created:** Something new was made  
- **301 Moved Permanently:** Page moved  
- **302 Found:** Temporary redirect  
- **400 Bad Request:** Problem in your request  
- **401 Not Authorised:** Login required  
- **403 Forbidden:** Not allowed, even if logged in  
- **404 Not Found:** Page doesn’t exist  
- **405 Method Not Allowed:** Wrong method used  
- **500 Internal Server Error:** Something broke  
- **503 Service Unavailable:** Server down or overloaded  

---

### 🧩 Task 5: Headers

Headers give extra information during requests and responses.

#### Request Headers (sent by client):
- **Host:** Tells the server which site to serve (important if server hosts multiple sites)  
- **User-Agent:** Browser info (for compatibility)  
- **Content-Length:** Size of data being sent  
- **Accept-Encoding:** Types of compression supported  

#### Response Headers (sent by server):
- **Set-Cookie:** Saves data on client for future requests  
- **Cache-Control:** Tells browser how long to store the response  
- **Content-Type:** What kind of file is being sent (HTML, image, etc.)  
- **Content-Encoding:** Compression method used  

---

### 🧩 Task 6: Cookies

- Cookies are small data pieces saved by your browser.  
- Sent back with every request to the server.  
- Help websites "remember" you — like keeping you logged in.  
- Commonly used for authentication.  
- Cookies usually store a token, not your actual password.

#### Example:
1. Request a page  
2. Server responds with a form  
3. You send back the form (e.g. name = Tim)  
4. Server sends a `Set-Cookie` header (e.g. name = Tim)  
5. Browser saves it  
6. Future visits use that cookie (e.g. to skip the form)

---

### 🧩 Task 7: Making Requests (Practical)

- Answered questions based on manually building and understanding HTTP requests.

---

## ✅ Key Takeaways

- HTTP is how websites send and receive data  
- HTTPS encrypts that data for safety  
- HTTP methods (GET, POST, etc.) define actions  
- Status codes explain what happened  
- Headers and cookies carry important extra data  

---

