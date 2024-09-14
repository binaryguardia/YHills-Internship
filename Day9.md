# Day 9 Learning

## 1. Task 2 of "h4cked" Room on TryHackMe

Today, I completed **Task 2** of the "h4cked" room on TryHackMe, which involved analyzing a **.pcap** file using **Wireshark** and solving the challenge of recovering the flag located in `/root/Reptile`.

- **Analyzing .pcap file**: I analyzed the attacker's steps through the **.pcap** file, where they exploited the machine, changed the user's password, and used a **backdoor** to gain access.
  
- **Tools Used**:
    - **Wireshark**: To analyze network traffic and identify malicious activity. This allowed me to trace the attacker’s actions, including their exploitation techniques and use of **reverse shells**.

**TryHackMe Link to the "h4cked" Room**:  
[TryHackMe h4cked Room](https://tryhackme.com/r/room/h4cked)

## 2. Communicating and Exploiting Machines on TryHackMe using Local Machine

While working on TryHackMe, I learned how to **communicate and exploit machines** on the platform by connecting from my local machine through VPN. TryHackMe provides an **.ovpn file** to establish a secure connection with their network.

### Steps to Connect to TryHackMe Machine:
1. **Download the .ovpn file**:
    - When working on TryHackMe, each user needs to download the **OpenVPN configuration file** specific to their session. This file establishes a secure tunnel to the target machine.

2. **Run OpenVPN**:
    - On your local machine, use the following command to start the VPN connection:
        ```
        sudo openvpn <your-ovpn-file-name>.ovpn
        ```
    - Example:
        ```
        sudo openvpn tryhackme.ovpn
        ```
    - This will establish a connection between your local machine and the TryHackMe network.

3. **Verify Connection**:
    - Once connected, your terminal will show messages indicating a successful connection, including lines like:
        ```
        Initialization Sequence Completed
        ```
    - Your machine now has access to TryHackMe's internal network, and you can interact with the machine provided in the TryHackMe room.

4. **Exploiting the Machine**:
    - With the connection established, you can communicate with the target machine over the network using your local terminal. For example, to run reconnaissance or exploitation tools, you would use their local IP address, such as:
        ```
        ssh user@machine-ip
        ```
    - From this point, I used different exploitation tools to continue with my tasks, such as **Hydra** for brute-force attacks or **Metasploit** for running payloads.

### Key Points:
- Using **OpenVPN**, I was able to securely connect my local machine to the TryHackMe environment, enabling direct communication with vulnerable machines.
- This setup is crucial for learning practical hacking skills as it replicates real-world scenarios where remote machines need to be exploited via VPN-secured connections.

**VPN Connection and Communication**:
- This method of connecting ensures a **secure, encrypted tunnel** between my local machine and the TryHackMe network, allowing me to execute commands, exploit vulnerabilities, and gather information.

**TryHackMe OpenVPN Documentation**:  
[TryHackMe VPN Guide](https://tryhackme.com/faq/vpn)

## 3. Alternatives to Wireshark: Tshark & Arkime

My mentor introduced me to **Tshark** and **Arkime** as alternatives to Wireshark for analyzing network traffic.

### Tshark:
- **Tshark** is the command-line version of Wireshark. It provides the same functionality as Wireshark but operates in a terminal environment, making it useful for automation and remote analysis.
  
    **Key Features**:
    - Ability to analyze **.pcap** files directly from the terminal.
    - Supports a wide range of protocols for network packet analysis.
    - Can be used for **scripting** and batch processing of packet capture files.
  
    **Tshark Documentation**:  
    [Tshark Documentation](https://www.wireshark.org/docs/man-pages/tshark.html)

### Arkime:
- **Arkime** is a full-packet capture and indexing system that enables security professionals to capture, index, and search network traffic. It scales well for larger networks and provides a **web-based interface** for querying captured traffic.

    **Key Features**:
    - **Scalable**: Ideal for analyzing large volumes of network traffic.
    - **Web Interface**: Allows for easy search and navigation of network captures.
    - **Integration**: Can integrate with other security tools for enhanced network security analysis.
  
    **Arkime Official Website**:  
    [Arkime](https://arkime.com/)

## 4. VPN Setup and Configuration

I also learned about **VPN (Virtual Private Network)** setup and how it can be used to connect local machines securely over the internet.

### VPN Configuration:
- **Configuring a VPN file**:
    - To establish a secure connection, a VPN configuration file is used that includes details such as:
        - **Server IP**.
        - **Encryption keys**.
        - **Authentication methods**.
  
    **Example VPN Configuration**:
    ```
    client
    dev tun
    proto udp
    remote vpn-server-ip 1194
    ca ca.crt
    cert client.crt
    key client.key
    ```

- **Netmask & Subnet**: During the VPN setup, I learned about configuring **netmask** and **subnet** to allow proper routing and secure communication between machines.

    **Netmask** helps in determining which part of the IP address is the network and which part is the host. The **subnet** allows dividing large networks into smaller, manageable segments.
    ![image](https://github.com/user-attachments/assets/21163807-f6b7-4238-bd11-1182e094291d)

    - **Example Netmask**:
        ```
        255.255.255.0
        ```

**Useful Links**:
- [Arkime Documentation](https://arkime.com/)
- [Tshark Documentation](https://www.wireshark.org/docs/man-pages/tshark.html)
- [VPN Setup Guide](https://openvpn.net/vpn-server-resources/setting-up-your-own-vpn-server-with-openvpn/)

This report covers all aspects of the topics learned in Day 9, including how to connect to TryHackMe machines using OpenVPN, network traffic analysis with Wireshark alternatives, and VPN configuration.
