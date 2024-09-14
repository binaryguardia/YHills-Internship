# Day 6 Learning

## 1. Ngrok Port Forwarding Techniques

Today, I learned about **Ngrok port forwarding** and its various uses in both **cybersecurity** and potentially malicious activities. Here’s a detailed explanation of what I learned:

### What is Ngrok?

**Ngrok** is a tool that allows you to expose a local server to the internet using a secure tunnel. It essentially provides a public URL (a tunnel) to your local server. This is especially useful when you need to share your locally hosted web page with others without configuring your network.

Ngrok can be used in multiple scenarios:
- **Developers** use it for testing webhooks and sharing development servers.
- **Hackers** or attackers may use it to deliver **malware** or launch attacks by creating phishing pages through the forwarded ports.
- **Cybersecurity professionals** use it for testing exploits, bypassing firewalls, and setting up reverse shells.

**Ngrok official website**:  
[Ngrok Documentation](https://ngrok.com/docs)

### Port Forwarding with Ngrok

- **Step-by-Step Usage**:
    1. Download and install Ngrok.
    2. Use the following command to forward a local web page:
        ```
        ./ngrok http 80
        ```
    3. Ngrok generates a public URL that forwards traffic to your local web server.
    4. Share the URL with external users for testing or access.

### How Attackers Use Ngrok for Phishing

- **Social Engineering**: Attackers use Ngrok to host phishing pages on their local machines, forwarding them to victims using a public Ngrok URL. This allows them to perform phishing attacks while keeping their IP hidden.

- **Malware Delivery**: Ngrok is also used to serve malware through forwarded ports. Attackers can trick users into downloading malicious files by clicking on links hosted through Ngrok tunnels.

### SSH Access Using Ngrok Port Forwarding

Ngrok can also forward SSH ports, enabling remote access to other devices.

**Example: My SSH Connection to a Mentor's  (GitHub: [KeralaHacker](https://github.com/keralahacker)) Machine**
- I used Ngrok to create an SSH tunnel, connecting to my mentor’s machine with his permission.
- **Steps**:
    1. On the mentor's side, he used the following command to forward the SSH port:
        ```
        ./ngrok tcp 22
        ```
    2. I received a forwarded public IP and connected via SSH:
        ```
        ssh user@ngrok-forwarded-address -p <port-number>
        ```
    3. I was able to securely connect and make changes to the remote machine.

This demonstrates the power of **port forwarding** using Ngrok to access systems securely over the internet.

## 2. Reconnaissance Using ReconDog

I also learned about **ReconDog**, a tool used for reconnaissance in cybersecurity. It provides a user-friendly interface to gather information about a target, useful in both offensive and defensive security practices.
![image](https://github.com/user-attachments/assets/0c4cc69a-e633-4ec7-a6f9-2817eb879373)

### ReconDog Features:
- **Gather domain information**.
- **Find subdomains**.
- **Check DNS records**.
- **Perform WHOIS lookups**.

ReconDog allows you to collect vast amounts of data quickly and easily. I used the tool to perform recon on various domains, identifying their IP addresses and subdomains.

**ReconDog GitHub Link**:  
[ReconDog](https://github.com/UltimateHackers/ReconDog)

## 3. Task Assignment: Port Forwarding & Reconnaissance

- **Task 1**: I was assigned the task of forwarding a local host web page using Ngrok. I successfully completed this by using Ngrok's **HTTP tunnel** and sharing the link with my team for testing.
- **Task 2**: For reconnaissance, I used **ReconDog** to perform detailed analysis and map the external assets of a target domain.

These experiences helped me understand the practical use of port forwarding and how tools like Ngrok and ReconDog are applied in both offensive and defensive cybersecurity.

