# 🐱 Meow Machine Write-Up
<img width="452" height="239" alt="image" src="https://github.com/user-attachments/assets/983b5755-5b7c-4f48-b11b-259d1f3b3beb" />

## 📌 Overview
This write-up documents the exploitation of the **Meow** machine on Hack The Box.

---

## 🎯 Objective
- Enumerate the target
- Identify vulnerabilities
- Gain access
- Retrieve the flag

---

## 🌐 Initial Setup

Connect to VPN:
```bash
sudo openvpn <vpn_file.ovpn>
```
Verify connectivity:
```bash
ping <target_ip>
```
📸 Screenshot:
<img width="758" height="307" alt="image" src="https://github.com/user-attachments/assets/c65ea67b-3884-49d1-a9b9-c91dd68ea7c2" />

🔍 Enumeration
Run Nmap scan:
```bash
nmap -sV <target_ip>
```
Results:
Port 23 open
Service: Telnet

📸 Screenshot:
<img width="940" height="261" alt="image" src="https://github.com/user-attachments/assets/9ddc7a6e-62c0-4f26-9fce-f87caaf07fe0" />


🚪 Exploitation

Connect using Telnet:
```bash
telnet <target_ip> 23
```
📸 Screenshot:
<img width="627" height="323" alt="image" src="https://github.com/user-attachments/assets/aee0b74f-c15d-4aee-b9e0-4516f4a6232b" />

Attempt default credentials:

- admin
- user
- root

Observation: Connection drops after multiple failed attempts

📸 Screenshot:
<img width="644" height="731" alt="image" src="https://github.com/user-attachments/assets/e932c2f7-1c17-440f-86e3-f706cb53559c" />



Successful Login:
Username: root
Password: (empty)

📸 Screenshot:
<img width="843" height="870" alt="image" src="https://github.com/user-attachments/assets/32745658-c880-480f-bd5b-1b63547461d1" />



💻 Post-Exploitation

List files: ls

Retrieve flag: cat flag.txt

📸 Screenshot:
<img width="846" height="343" alt="image" src="https://github.com/user-attachments/assets/06d69bfc-b11e-46aa-abd8-13cef0604d19" />



🧠 Key Takeaways
Telnet is insecure (plaintext communication)
Default credentials are a major risk
Basic enumeration can reveal critical vulnerabilities

🚀 Conclusion
This machine highlights poor security practices: 
Use of insecure services
Lack of authentication controls

🛠️ Tools Used
Nmap
Telnet
OpenVPN
