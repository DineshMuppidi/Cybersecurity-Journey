# 🚀 Connecting to a Remote Ubuntu Server via SSH

## 📌 Overview
This guide explains how to connect to a **remote Ubuntu server** using **SSH (Secure Shell)**. The connection is established using an **IP address**, along with a **username and password**.

**Note:** This guide is written from a **Parrot OS** environment, so terminal prompts may show `user@parrot`. However, the commands work on any Linux-based system, including Ubuntu, Kali, and Debian.

## **1️⃣ Prerequisites**
Before starting, ensure you have:
- A **remote Ubuntu server** with an assigned **IP address**.
- A **username** and **password** for SSH login.
- A system with **SSH installed** (Parrot OS has SSH pre-installed, as do Mac and Linux; Windows users can use PowerShell or WSL).

## **2️⃣ Connect to Ubuntu Server Using SSH**
### **🔹 Step 1: Open a Terminal**
- **Parrot OS/Linux:** Use the built-in **Terminal**.
- **Windows:** Use **PowerShell**, **Command Prompt**, or **Windows Terminal**.

### **🔹 Step 2: Run the SSH Command**
Replace `<username>` and `<server-ip>` with your actual credentials:
```bash
user@parrot:~$ ssh <username>@<server-ip>
```
For example, if your username is `admin` and the server IP is `192.168.1.100`, the command would be:
```bash
user@parrot:~$ ssh admin@192.168.1.100
```

### **🔹 Step 3: Enter Password**
- After running the command, you will be prompted to enter your **password**.
- Type your password (it won’t be visible) and press **Enter**.

### **🔹 Step 4: Verify Connection**
Once connected, you will see a welcome message and the terminal will change to the remote server's shell:
```bash

┌─[user@parrot]─[~]
└──╼ $ssh admin@10.129.78.180
admin@10.129.78.180's password: 

Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 4.15.0-123-generic x86_64)

admin@nixfund:~$

```
Now, you are **successfully logged in** to the remote Ubuntu server.

## **3️⃣ Basic SSH Commands**
Here are some useful commands to manage the server:
| Command | Description |
|---------|------------|
| `ls` | List files and directories |
| `pwd` | Show current directory |
| `cd /path/to/directory` | Change directory |
| `htop` | Show system resource usage |
| `exit` | Logout from the remote session |

## **4️⃣ Disconnecting from the Server**
To safely exit the SSH session, use one of these commands:
``exit ``
```bash
admin@nixfund:~$ exit
logout
Connection to 10.129.78.180 closed.

┌─[✗]─[user@parrot]─[~]
└──╼ $

```
or
```bash
CTRL + D
```
This will disconnect your session and return you to your local terminal.

## **5️⃣ Troubleshooting SSH Connection Issues**
If you encounter problems, try these fixes:
- **Permission denied (publickey, password)** → Check username/password.
- **Connection refused** → Ensure the SSH service is running on the remote server:
  ```bash
  sudo systemctl status ssh
  ```
- **Timeout or no route to host** → Ensure the server IP is correct and accessible.

## **🚀 Next Steps**
- Set up **SSH key authentication** instead of using a password for better security.
- Use **tmux** or **screen** to keep your session running in case of disconnection.
- Secure your SSH server by changing the **default port** and **disabling root login**.

Now you’re ready to manage your Ubuntu server remotely! 🎉