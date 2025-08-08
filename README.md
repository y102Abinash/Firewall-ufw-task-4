# Firewall-ufw-task-4
Internship Task: Configuring and Testing Firewall Rules with UFW on Linux
# 🔒 Task 4: Setup and Use a Firewall on Linux (UFW)

## 📌 Overview
This repository contains my **internship Task 4 report** for configuring and testing firewall rules using **UFW (Uncomplicated Firewall)** on Kali Linux.  
The task involved enabling the firewall, creating rules to block and allow specific ports, testing these rules, and documenting the process with screenshots.

---

## 🎯 Objective
To configure and test basic firewall rules to:
- Block insecure services (Telnet - port 23)
- Allow secure remote access (SSH - port 22)
- Understand how a firewall filters network traffic

---
## 📂 Repository Contents
| File                            | Description                                                              |
|---------------------------------|--------------------------------------------------------------------------|
| `Task4_UFW_Firewall_Report.pdf` | Full internship task report with commands, screenshots, and explanations |
| `README.md`                     | This file – explains the task, steps, and how to view the report         |


## 🛠 Tools Used
- **Operating System:** Kali Linux (Debian-based)
- **Firewall Tool:** UFW (Uncomplicated Firewall)
- **Testing Tool:** Telnet client
- **Documentation:** PDF report with step-by-step commands and screenshots

---

## 🖥 Full Bash Command Sequence

```bash
# 1️⃣ Update system packages
sudo apt update

# 2️⃣ Install UFW if not installed
sudo apt install ufw -y

# 3️⃣ Enable UFW service on startup
sudo systemctl enable ufw
sudo systemctl start ufw

# 4️⃣ Turn on UFW
sudo ufw enable

# 5️⃣ View current firewall rules
sudo ufw status numbered

# 6️⃣ Block insecure Telnet service (Port 23, TCP)
sudo ufw deny 23/tcp

# 7️⃣ Verify that the block rule is applied
sudo ufw status numbered

# 8️⃣ Install Telnet client for testing
sudo apt install telnet -y

# 9️⃣ Test Telnet connection to port 23 (should be blocked)
telnet localhost 23

# 1️⃣0️⃣ Allow SSH service (Port 22, TCP)
sudo ufw allow 22/tcp

# 1️⃣1️⃣ Remove the Telnet block rule
sudo ufw delete deny 23/tcp

# 1️⃣2️⃣ Final check of firewall rules
sudo ufw status numbered


