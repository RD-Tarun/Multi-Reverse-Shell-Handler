# Multi Reverse Shell Handler

## Introduction

Welcome to this new article! Today, I'm going to show you a tool that I think is very useful for hackers, especially for **pentesters**. This tool is essentially a terminal-based manager for handling **multiple reverse shells simultaneously**.

You can find this tool for free on GitHub. It is developed in Python. Originally built for Python 2, a Python 3 version has also been published, although it may throw some errors.

🔗 **GitHub Repository:**  
[WangYihang/Reverse-Shell-Manager](https://github.com/WangYihang/Reverse-Shell-Manager)

---

## Installation

Installing this tool is very straightforward. Just run the following commands:

```bash
git clone https://github.com/WangYihang/Reverse-Shell-Manager
cd Reverse-Shell-Manager
```

## Description (From Repository)

> A multiple reverse shell session/client manager via terminal

This tool allows an attacker or pentester to manage **multiple reverse shell connections** within a single terminal interface. It's ideal for handling sessions from multiple targets concurrently and efficiently.

---

## Proof of Concept (PoC)
Let’s see how to use this tool. It’s a **very simple** yet **very powerful** utility.

### Step 1: Run the Server
Run the following command to start the server:

```bash
python2 Reverse-Shell-Manager.py 0.0.0.0 1212 2>/dev/null
```

> The 2>/dev/null blocks prompt errors while using Python2, if you don’t put this during execution, this happens:
> 
> ![image](https://github.com/user-attachments/assets/fb44362c-7083-400c-98ce-a72a63b61359)

### Step 2: Connect Clients
Now that the server is up and running, you can begin connecting reverse shell clients.

![image](https://github.com/user-attachments/assets/4e06a92e-e4ef-4f77-aa05-93a92a202b94)

For example:
- A **Windows client** with IP `192.168.0.113` can be configured to initiate a reverse shell back to your attacker's IP (`your-ip`) on port `1212`.
  
![image](https://github.com/user-attachments/assets/60677d63-341b-4100-8ece-014515e524be)


Once a client connects successfully, you'll see the session appear in the terminal interface. You can then interact with it, and even manage **multiple concurrent sessions** from different machines—whether they're Linux, Windows, or others.

No additional configuration is required to accept more connections. As new clients connect, they’ll be listed and can be controlled individually.

---

## Features & Options

After clients are connected, the tool provides a menu of options. Some of the most useful ones include:

- **[3] Interactive Shell**  
  Opens a fully interactive command shell with the target system.

- **[8] Add Crontab**  
  Sets up a cron job on Unix-like systems for scheduled or persistent tasks.

- **[14] Auto Connection (Persistence)**  
  Automatically re-establishes a connection when the client reboots—ideal for long-term access.
![image](https://github.com/user-attachments/assets/656942ce-9998-44fc-b386-16be26ca7c37)


> **Recommended:** Option 14 is especially useful for creating **persistence**, allowing the reverse shell to reconnect even after a restart.

---

## Conclusion

This wraps up our exploration of the Reverse Shell Manager! We’ve covered:

- Setting up the server
- Connecting multiple clients
- Using critical features for interaction and persistence

The real strength of this tool lies in its **simplicity** and ability to **manage multiple shells simultaneously** from a single terminal session.

Thanks for checking this out! 😊  
— **Malforge Group**
