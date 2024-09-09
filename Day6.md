# Day 6 Learning

## 1. Networking Commands in Linux

### **ping** (Protocol: ICMP)
- **ping** is used to check the connectivity between two devices over a network by sending ICMP (Internet Control Message Protocol) echo request packets and waiting for an echo reply.
- Example:
    ```
    ping google.com
    ```
- Detailed Information:  
  Ping uses the **ICMP protocol** to test the reachability of a host on a network and to measure round-trip time.

### **ifconfig** (Protocol: None)
- **ifconfig** is used to configure, control, and query network interface parameters.
- Example to display network information:
    ```
    ifconfig
    ```
- Detailed Information:  
  Ifconfig shows the IP address, broadcast address, and network mask for each interface on the system.

### **nslookup** (Protocol: DNS)
- **nslookup** is used to query DNS servers and get information about domain names or IP addresses.
- Example:
    ```
    nslookup example.com
    ```
- Detailed Information:  
  Nslookup sends a DNS request to a specified DNS server to resolve an IP address to a domain name or vice versa.

### **traceroute** (Protocol: ICMP/UDP)
- **traceroute** traces the path that a packet takes from your computer to a destination.
- Example:
    ```
    traceroute google.com
    ```
- Detailed Information:  
  Traceroute sends packets using ICMP or UDP and shows the hops that the packet takes through intermediate routers.

### **netstat** (Protocol: TCP/UDP)
- **netstat** displays information about active network connections, routing tables, and interface statistics.
- Example:
    ```
    netstat -tuln
    ```
- Detailed Information:  
  Netstat provides details on open ports, the protocol being used (TCP/UDP), and connection status.

For a full list of networking commands:  
[Linux Networking Commands](https://linux.die.net/man/)

## 2. ARP and ICMP Protocols

### **ARP (Address Resolution Protocol)**
- ARP is used to map IP addresses to MAC (Media Access Control) addresses in a local area network (LAN).
- To view the ARP table:
    ```
    arp -a
    ```
- ARP works at Layer 2 (Data Link) of the OSI model to resolve the Layer 3 (Network) IP address into a MAC address.

### **ICMP (Internet Control Message Protocol)**
- ICMP is used by network devices to send error messages and operational information (e.g., destination unreachable).
- **Ping** and **traceroute** both rely on ICMP for communication.

More on ARP: [ARP Protocol Documentation](https://www.cisco.com/c/en/us/support/docs/ip/address-resolution-protocol-arp/13718-5.html)

## 3. Wireshark Tutorial

### Installation:
1. Install Wireshark:
    ```
    sudo apt-get install wireshark
    ```
2. Start Wireshark:
    ```
    wireshark
    ```
![image](https://github.com/user-attachments/assets/4a3a4975-5975-49aa-b40c-ab858d5ff9e8)

### Capturing Packets:
- Wireshark captures live traffic on a network interface.
- Steps:
    1. Open Wireshark and select the network interface.
    2. Click **Start** to begin packet capture.
    3. To stop, click **Stop**.

### Wireshark Filters:
- Filters help focus on specific types of traffic.
- Common filters:
    - **HTTP** traffic:
      ```
      http
      ```
    - **TCP** traffic:
      ```
      tcp
      ```
    - **ICMP** traffic:
      ```
      icmp
      ```
- Learn more about filters: [Wireshark Filters Documentation](https://wiki.wireshark.org/DisplayFilters)

### Wireshark in Digital Forensics:
- Wireshark is widely used in digital forensics to analyze network traffic, detect anomalies, and identify attacks such as Man-in-the-Middle or DDoS attacks.

### VPN and Wireshark:
- When using a VPN, traffic is encrypted between the client and the VPN server, making it harder to analyze the packet content in Wireshark, but you can still observe encrypted traffic and metadata.

For a full tutorial: [Wireshark User Guide](https://www.wireshark.org/docs/wsug_html_chunked/)

## 4. VPN (Virtual Private Network)

### How VPN Works:
- A VPN creates a secure, encrypted tunnel between your device and a VPN server. All traffic is routed through this tunnel, protecting your data from being intercepted by third parties.
- VPNs use protocols like **OpenVPN**, **L2TP/IPsec**, and **WireGuard**.
  
#### VPN Working Process:
1. **User requests** a connection to a website.
2. The **VPN client encrypts** the data.
3. Data travels to the **VPN server**, which decrypts and sends it to the destination server.
4. The **response is encrypted** by the VPN server and sent back to the user.

For a visual guide on how VPNs work:  
[How VPN Works: Visual Explanation](https://www.cnet.com/how-to/how-vpns-work/)

## 5. Blockchain and Cryptocurrency

### How Blockchain Works:
- Blockchain is a distributed ledger technology used to store data in a series of blocks linked by cryptography. It is decentralized and immutable.
- Blockchain is the backbone of cryptocurrencies like Bitcoin.

### How Hackers Use Blockchain:
- **Anonymity**: Hackers use cryptocurrencies to remain anonymous in their transactions.
- **Ransomware**: Hackers demand ransoms in cryptocurrency because it’s hard to trace.

Learn more about blockchain: [Blockchain Basics](https://blockgeeks.com/guides/what-is-blockchain-technology/)

## 6. Web Browser Communication Process (Step-by-Step)

### Step-by-Step Breakdown:
1. **User enters a URL** in the browser.
2. **DNS lookup**: The browser sends a request to resolve the domain name to an IP address.
3. **TCP handshake**: A connection is established between the user and the server.
4. **SSL/TLS handshake** (if HTTPS): Data is encrypted between the client and server.
5. **HTTP request**: The browser sends an HTTP GET request to retrieve the webpage.
6. **Server response**: The server responds with the requested page.
7. **Rendering**: The browser processes the HTML/CSS/JS and displays the webpage.

### DNS Query Flow:
1. The browser checks its **cache** for DNS records.
2. If not found, it queries the **DNS server**.
3. The DNS server responds with the IP address.

For more information: [How DNS Works](https://www.cloudflare.com/en-gb/learning/dns/what-is-dns/)

## 7. Inspect Accessibility Properties

- **Inspect Accessibility** in browsers allows developers to review and modify accessibility features such as alt text, labels, and roles for elements.
- It helps ensure that web content is usable by assistive technologies like screen readers.
- In Chrome, right-click on a webpage and select **Inspect**. Navigate to the **Accessibility** tab to view properties.

### Inspecting Cookies:
- **Cookies** are small pieces of data stored by the browser to track user sessions.
- In the Inspect tool, go to **Application** → **Cookies** to view cookies set by the website.

Learn more: [Chrome DevTools Accessibility]((https://developer.chrome.com/docs/devtools/accessibility/reference))

