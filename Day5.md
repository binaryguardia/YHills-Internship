# Day 5 Learning

## 1. Virtual Machine IP Configuration

### Explanation of IP Configuration in VMware:

- **VMware IP setup**:  
  A virtual machine in VMware can be assigned an IP address automatically using DHCP or manually via static IP assignment.
  - **Check IP address**:  
    To find the IP address of a VM, run the following command inside the VM:
    ```
    ip addr show
    ```
    or
    ```
    ifconfig
    ```
  - **Bridge Network**: This setting allows the VM to share the same network as the host.
  - **NAT (Network Address Translation)**: Here, the VM will be on a private network, with the host acting as a gateway.

## 2. Ngrok Installation and Configuration

### Steps to Install Ngrok:

1. **Download ngrok** from its official website:
    [Download Ngrok](https://ngrok.com/download)
    ```
    wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-amd64.zip
    ```
2. **Unzip the file**:
    ```
    unzip ngrok-stable-linux-amd64.zip
    ```
3. **Move ngrok to /usr/local/bin**:
    ```
    sudo mv ngrok /usr/local/bin/ngrok
    ```

### Configuring Ngrok:

- **Sign up for an Ngrok account** to get your authentication token:  
  [Sign Up for Ngrok](https://dashboard.ngrok.com/signup)
- Run the following command to set your authentication token:
    ```
    ngrok authtoken YOUR_AUTH_TOKEN
    ```
- Start a tunnel on a specific port (e.g., 80 for HTTP):
    ```
    ngrok http 80
    ```

### Using Ngrok for TCP, SSH, HTTP, and RDP:

- **For TCP**:
    ```
    ngrok tcp 22
    ```
- **For SSH**:
    ```
    ngrok tcp 22
    ```
- **For HTTP (Port 80)**:
    ```
    ngrok http 80
    ```
- **For RDP (Remote Desktop Protocol)**:
    ```
    ngrok tcp 3389
    ```

For more details, check out [Ngrok's Documentation](https://ngrok.com/docs).

## 3. Filtering Commands

### Useful Linux Commands for Filtering:

- **grep**: Used for searching text in files.
    ```
   ls | grep "search_term" file_name
    ```
  Learn more about `grep`: [GNU grep manual](https://www.gnu.org/software/grep/manual/grep.html)

- **ls -lh**: Lists files with human-readable sizes.
    ```
    ls -lh
    ```
  Learn more about `ls`: [Linux ls command](https://man7.org/linux/man-pages/man1/ls.1.html)

- **cat**: Used for viewing the contents of a file.
    ```
    cat file_name
    ```

- **less**: View the contents of a file one page at a time.
    ```
    less file_name
    ```
  Learn more about `less`: [Linux less command](https://man7.org/linux/man-pages/man1/less.1.html)

## 4. File Permissions

### Explanation of File Permissions in Linux:

- **File permissions** in Linux are represented by three groups:
  - **User (owner)**, **Group**, and **Others**.
  - Each group can have:
    - `r` = Read
    - `w` = Write
    - `x` = Execute

### Numeric Representation (e.g., `777`):

- **rwx (777)** means:
    - **rwx** for user = 4 + 2 + 1 = 7
    - **rwx** for group = 4 + 2 + 1 = 7
    - **rwx** for others = 4 + 2 + 1 = 7

### Changing Permissions:

- Use the `chmod` command to change file permissions. Example:
    ```
    chmod 777 file_name
    ```

### Detailed Permissions:

- `r` (Read) = 4
- `w` (Write) = 2
- `x` (Execute) = 1

For example, `755` permissions mean:
- **User**: `rwx` (7)
- **Group**: `rx` (5)
- **Others**: `rx` (5)

For more details on Linux file permissions: [Linux File Permissions Guide](https://www.linux.com/training-tutorials/understanding-linux-file-permissions/)

## Conclusion:

In this session, I learned how to configure VMware IP, install and use Ngrok for exposing services via various ports, filter files using commands like `grep`, `ls -lh`, `cat`, and `less`, and manage file permissions using both symbolic and numeric representations like `chmod 777`.

