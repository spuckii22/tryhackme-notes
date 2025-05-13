# 🧩 TryHackMe – How Websites Work

## 📘 Room Information
- **Path:** Pre-Security → How the Web Works → How Websites Work  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-13  
- **Room Link:** [How Websites Work – TryHackMe](https://tryhackme.com/room/howwebsiteswork)

---

> ⚠️ **Disclaimer:**  
> This write-up is for educational and documentation purposes only. It does not contain flags or exact solutions, in accordance with TryHackMe’s Terms of Use.

---

## 🔍 Room Overview

This room explains how websites are built and introduces basic web technologies like HTML and JavaScript. It also covers common security vulnerabilities like sensitive data exposure and HTML injection.

---

## 🔍 Room Walkthrough

### Task 1 – How Websites Work

- When visiting a website, the browser (e.g. Chrome, Safari) makes a request to a web server.
- The web server responds with data that the browser uses to show the website.
- A web server is a remote computer that processes the request and returns content.

Two major components of a website:
1. Front End (Client-Side) – how the website looks and behaves in your browser  
2. Back End (Server-Side) – processes logic, stores data, and returns results

---

### Task 2 – HTML

- Websites are built using:
  - HTML – defines structure  
  - CSS – styles the content  
  - JavaScript – adds interactivity

- HTML (HyperText Markup Language) uses elements like:
  - <!DOCTYPE html> – defines HTML5  
  - <html> – root of the document  
  - <head> – contains metadata and title  
  - <body> – visible content  
  - <h*> – headings  
  - <p> – paragraphs

- Tags can have attributes like:
  - class (for styling)  
  - src (for images or scripts)  
  - id (for JavaScript interaction)
    
---

### Task 3 – JavaScript

- JavaScript is one of the most popular coding languages.
- It allows a website to react to user input, animate elements, and update content without reloading the page.

Example from the room:  
JavaScript code like  
document.getElementById("demo").innerHTML = "Hack the Planet";  
finds a page element with the ID "demo" and changes its content.

- JavaScript is added using <script> tags or loaded externally using src.
- HTML elements can have built-in event handlers like onclick and onhover.

Practical tasks included:
- Changing text on a button click  
- Updating webpage content with JavaScript

---

### Task 4 – Sensitive Data Exposure

- Sensitive data exposure happens when a website accidentally reveals clear-text data to the user.
- This can happen when developers leave credentials or internal links in the page’s source code.

Example:  
An HTML comment might contain something like  
<!-- login: admin, password: 1234 -->

This can be used by attackers to gain access.

Best practice: Always review a website’s source code when evaluating it for security issues.

---

### Task 5 – HTML Injection

- HTML Injection happens when a website includes user input directly into the page without sanitizing it.
- This lets users inject their own HTML (or even JavaScript) into the page.

Example:  
If the site includes your input like  
<h*>Hello</h*>  
instead of plain text, it will render a heading on the page.

This happens when user input is inserted directly into the DOM.

To avoid this:
- Developers must sanitize user input before using it in HTML or JavaScript.
- Never trust user input.

Practical task included:
- Injecting input that displays a malicious link on the website.

---

## ✅ Key Takeaways

- Web browsers and servers communicate using HTTP.  
- Websites consist of HTML (structure), CSS (style), and JavaScript (functionality).  
- Sensitive information can accidentally be left in page source code.  
- HTML Injection is a risk when websites don’t sanitize user input.  
- Always validate and sanitize all frontend input to prevent attacks.

---

## 🛠️ Tools & Techniques Used

- HTML  
- JavaScript  
- Web browser Developer Tools (View Page Source, Inspect Element)

---

## 🛠️ Commands

None used in this room.
