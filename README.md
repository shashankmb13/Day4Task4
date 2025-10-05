# Day4Task4
Firewall Configuration and Traffic Filtering using UFW / Windows Firewall

# Firewall Configuration and Traffic Filtering using UFW / Windows Firewall

## 📋 Overview
This project demonstrates the setup, configuration, and testing of basic firewall rules on both Windows and Linux systems. The objective is to understand how a firewall filters network traffic and how rules can be applied to allow or block specific ports.

---

## 🎯 Objective
To configure and test basic firewall rules for controlling inbound and outbound network traffic using:
- **Windows Firewall** (for Windows users)
- **UFW (Uncomplicated Firewall)** (for Linux users)

---

## 🧰 Tools Used
- **UFW (Uncomplicated Firewall)** – Linux  
- **Windows Defender Firewall** – Windows  

---

## ⚙️ Steps Performed
1. Checked current firewall status  
2. Enabled the firewall  
3. Listed existing rules  
4. Added a rule to **block inbound traffic on port 23 (Telnet)**  
5. Tested the Telnet block rule  
6. Added a rule to **allow SSH (port 22)**  
7. Verified the configuration  
8. Removed the test block rule to restore original state  

---

## 💾 Deliverable – Firewall Configuration File
**Path (Linux):** `/etc/ufw/user.rules`

### Sample Configuration:
```bash
# UFW user rules file
*filter
:ufw-user-input - [0:0]
:ufw-user-output - [0:0]
:ufw-user-forward - [0:0]

# Allow SSH
-A ufw-user-input -p tcp --dport 22 -j ACCEPT

# Block Telnet
-A ufw-user-input -p tcp --dport 23 -j DROP

COMMIT
