# Day 16 of Internship

## Learning New Software for Web Application Security: Burp Suite

Today, I learned about **Burp Suite**, a powerful tool used in cybersecurity for web application penetration testing. Here's a breakdown of what I learned and did:

### Installing and Configuring Burp Suite

To begin using Burp Suite, I first needed to set up the **FoxyProxy** extension in my browser. This extension allows Burp Suite to intercept the traffic between the browser and the web server.

#### Steps to Configure FoxyProxy:
1. Download and install the **FoxyProxy** extension from the browser's extension store.
2. After installation, set up a new proxy in FoxyProxy with the following settings:
   - **Proxy Type**: HTTP
   - **Proxy IP**: 127.0.0.1
   - **Proxy Port**: 8080
3. Apply and save the configuration.

*Below is a screenshot of the FoxyProxy configuration:*

![FoxyProxy Configuration]![image](https://github.com/user-attachments/assets/52363efe-068d-4077-b443-ae203980b311)


### Intercepting Data with Burp Suite

Once Burp Suite and FoxyProxy were configured, I started **intercepting data** transmitted over the network. This helped me understand how cookies, headers, and other information are exchanged between the client and server.

#### Steps to Intercept Data:
1. Launch Burp Suite and ensure that intercept is enabled under the **Proxy** tab.
2. Perform actions on the web browser, such as logging into a website, to capture requests and responses.
3. Analyze the intercepted data to understand the structure of HTTP requests and responses, including headers, cookies, and payloads.

*Below is a screenshot of an intercepted request:*

![Intercepted Data]!![Screenshot at 2024-09-04 09-58-18](https://github.com/user-attachments/assets/058a27d0-b2df-4e5a-854e-73485badb243)

## Installing and Exploring DVWA

# DVWA: Damn Vulnerable Web Application

## Introduction to DVWA

**Damn Vulnerable Web Application (DVWA)** is a PHP/MySQL web application intentionally designed to be vulnerable. It serves as an educational tool for learning and practicing web application security vulnerabilities. DVWA is widely used by cybersecurity enthusiasts, students, and professionals to gain hands-on experience in identifying and exploiting security flaws in a safe, controlled environment.

## Key Features of DVWA

DVWA offers a comprehensive set of features that cover various aspects of web application security:

### 1. **Security Levels**

DVWA allows users to set different security levels to simulate varying degrees of security measures:
- **Low**: The application has minimal or no security measures, making it easily exploitable. This level is ideal for beginners to understand the basics of web vulnerabilities.
- **Medium**: Basic security defenses are in place, but they are still relatively easy to bypass. This level provides an intermediate challenge.
- **High**: Advanced security features are enabled, making it difficult to exploit vulnerabilities. This level is designed for more experienced users who want to test their skills against stronger security defenses.
- **Impossible**: The application is configured to be highly secure, making exploitation nearly impossible. This level is used to demonstrate how a secure web application should behave.

### 2. **Modules for Various Web Vulnerabilities**

DVWA includes several modules, each focused on a specific type of web application vulnerability:

- **SQL Injection (SQLi)**: This module allows users to practice exploiting SQL injection vulnerabilities. SQL injection occurs when an attacker can manipulate SQL queries to gain unauthorized access to the database.
  
- **Cross-Site Scripting (XSS)**: DVWA includes both reflected and stored XSS vulnerabilities. Users can learn how to inject malicious scripts into web pages and understand the impact of XSS attacks on users.

- **Command Injection**: This module allows users to execute arbitrary commands on the server by exploiting vulnerable input fields that pass user input directly to the system shell.

- **File Inclusion**: DVWA provides Local File Inclusion (LFI) and Remote File Inclusion (RFI) vulnerabilities. These vulnerabilities occur when an attacker can include unauthorized files on the web server.

- **Cross-Site Request Forgery (CSRF)**: In this module, users can learn how to exploit CSRF vulnerabilities, which occur when an attacker tricks a user into performing actions on a web application without their consent.

- **File Upload**: This feature demonstrates the risks associated with insecure file upload mechanisms. Users can practice uploading malicious files to the server to execute arbitrary code.

- **Brute Force**: This module allows users to simulate brute force attacks on login forms. It highlights the importance of secure password policies and account lockout mechanisms.

- **Insecure CAPTCHA**: DVWA includes a module for testing the strength of CAPTCHA implementations and demonstrates how weak CAPTCHAs can be bypassed.

### 3. **Interactive Learning Environment**

DVWA provides a highly interactive learning environment with the following features:

- **User-Friendly Interface**: The application offers a simple and intuitive GUI, making it accessible to users of all experience levels.
  
- **Real-Time Feedback**: As users attempt to exploit vulnerabilities, DVWA provides real-time feedback, helping them understand the impact of their actions and learn from their mistakes.

- **Comprehensive Documentation**: DVWA includes extensive documentation and guides, making it easier for users to understand each vulnerability and how to exploit it.

### 4. **Customizable Security Configurations**

DVWA allows users to customize various security configurations, such as database settings, security levels, and user accounts. This flexibility enables users to tailor the environment to their specific learning needs and experiment with different scenarios.
![image](https://github.com/user-attachments/assets/e97800ae-76cb-494e-bfa0-93f4ab1dd822)

### 5. **Networking and Collaboration**

DVWA can be hosted locally or on a network, allowing multiple users to access the application simultaneously. This feature is particularly useful for group learning sessions or collaborative penetration testing exercises.

---

By working with DVWA, I gained valuable experience in web application security and learned how to identify and exploit various vulnerabilities. This knowledge is crucial for understanding how to secure web applications and prevent common attacks.


### Installing DVWA

The installation was done using the following command:

```
sudo apt install dvwa -y
sudo dvwa-start

