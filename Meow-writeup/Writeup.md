# 🐱 Meow Machine Write-Up

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

Verify connectivity:
ping <target_ip>
<img width="758" height="307" alt="image" src="https://github.com/user-attachments/assets/95244921-cde6-4b5a-8030-031067ee890e" />


🔍 Enumeration
Run Nmap scan:
nmap -sV <target_ip>
Results:
Port 23 open
Service: Telnet

📸 Screenshot:
<img width="940" height="261" alt="image" src="https://github.com/user-attachments/assets/dd2dae2a-965a-4fa0-a851-066cbe8d1404" />



🚪 Exploitation

Connect using Telnet:

telnet <target_ip> 23

Attempt default credentials:

admin
user
root

Observation: Connection drops after multiple failed attempts
<img width="644" height="731" alt="image" src="https://github.com/user-attachments/assets/c0fbb958-efd8-49a0-b2be-0c9d6be5f67c" />


Successful Login:
Username: root
Password: (empty)

📸 Screenshot:
<img width="843" height="870" alt="image" src="https://github.com/user-attachments/assets/17d5fa5f-4725-4c61-954f-48bea89320cc" />



💻 Post-Exploitation

List files:

ls

Retrieve flag:

cat flag.txt

📸 Screenshot:
<img width="846" height="343" alt="image" src="https://github.com/user-attachments/assets/6d4a0845-43f4-468a-86d5-423ba044ac80" />



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
