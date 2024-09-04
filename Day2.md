# Day 2: Reconnaissance, Information Gathering, and Practical Commands

On the second day of my internship, we explored advanced cyber security concepts, including reconnaissance, information gathering, and practical command-line usage on both Windows and Linux systems. Below is a detailed summary of what was covered:

## Reconnaissance and Information Gathering

Reconnaissance and information gathering are essential steps in cyber security for understanding and evaluating the target environment. These techniques help in identifying potential vulnerabilities and weaknesses.

### Key Techniques

- **Footprinting**: This involves collecting information about an organization’s network. Techniques include gathering domain names, IP addresses, network services, and other relevant data to build a profile of the target.

- **Scanning**: Scanning tools are used to discover open ports, running services, and potential vulnerabilities in the target system. Common tools include Nmap and Nessus.

- **Social Engineering**: This technique involves manipulating individuals to gain confidential information. Methods include phishing emails, pretexting, and baiting.

## Linux Commands and Directories

Linux commands are crucial for managing files, directories, and system services. Here are some essential commands and their explanations:

### Basic Commands

#### `ls`
Lists the contents of a directory.
```bash
$ ls
```
Desktop  Documents  Downloads

```bash 
cd
```
Changes the current directory.

```bash

cd Documents
```

Creates a new directory.
```
mkdir

mkdir Project
```
Removes files or directories. Use -r to remove directories recursively.
```
rm
```


```bash

$ rm file.txt
$ rm -r Project/
```

Copies files or directories from one location to another.

```bash

$ cp file.txt Project/
```

Moves or renames files or directories.

```
$ mv file.txt Project/
$ mv oldname.txt newname.txt
```
Linux Directories
`
    /: The root directory, the starting point of the file system.
    /home: Contains user home directories.
    /etc: Contains system configuration files.
    /var: Contains variable data such as logs and databases.
    /usr: Contains user utilities and applications.

Service Commands

Managing services on Linux involves using commands to control system services:
ssh

Connects to a remote server securely using SSH (Secure Shell).

```bash

$ ssh user@hostname
```
```
systemctl
```
Manages system services and the system state. Examples include starting, stopping, and checking the status of services.

```bash

$ systemctl status ssh
$ systemctl start ssh
$ systemctl stop ssh
```
Connecting to Raspberry Pi and Gaining Shell Access

To connect to a Raspberry Pi and access its shell:
`
    Connect via SSH:
        Ensure the Raspberry Pi is connected to the network.
        Use SSH to connect from a terminal or command line.

 ```   bash

$ ssh pi@<raspberry_pi_ip>
```
Gain Shell Access:
`
    After connecting, you’ll have access to the Raspberry Pi’s shell to execute commands and manage the system.
## Running Linux Commands in Command Prompt Using WSL

Windows Subsystem for Linux (WSL) allows you to run a Linux environment directly on Windows without the need for a virtual machine or dual-boot setup. You can use WSL to execute Linux commands directly from the Windows Command Prompt or PowerShell. Here’s how you can do it:

### Setting Up WSL

Before running Linux commands, make sure you have WSL installed and set up on your Windows machine:

1. **Enable WSL**:
   - Open PowerShell as an administrator and run the following command to enable WSL:

   ```powershell
   dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all
use your linux command and learn.
