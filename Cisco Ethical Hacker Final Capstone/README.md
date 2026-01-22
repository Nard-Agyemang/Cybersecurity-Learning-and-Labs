# Ethical Hacker Final Capstone Activity

## 🛡️ Project Overview

This repository documents the **Final Capstone Activity** for the Cisco Ethical Hacker course. The objective was to conduct a complete penetration test, starting with reconnaissance, launching exploits against discovered vulnerabilities, and proposing remediation strategies.

The assessment was structured as a **Capture the Flag (CTF)** exercise, where ethical hacking skills were used to locate "flag" files containing specific codes.

## 🎯 Challenges & Objectives

The capstone consisted of four main challenges, each focusing on a specific attack vector:

### 1. SQL Injection 💉

**Objective**: Discover user account information, crack a password, and find a hidden flag.

* **Techniques**: SQL Injection (SQLi), Password Cracking.
* **Outcome**: Successfully retrieved Bob Smith's credentials (`admin` / `password`), cracked his hash (`***password`), and retrieved the flag from `my_passwords.txt`.
* **Key Remediation**: Use prepared statements (parameterized queries) and implement strict input validation.

### 2. Web Server Vulnerabilities 🌐

**Objective**: Investigate directory listing vulnerabilities to find a hidden flag.

* **Techniques**: Directory Traversal, Web Reconnaissance.
* **Outcome**: Identified accessible directories (`/config/`, `/docs/`, `/external/`) and located the flag in `db_form.html`.
* **Key Remediation**: Disable directory listing on the web server and avoid storing sensitive backup files in public directories.

### 3. SMB Exploitation 📂

**Objective**: Exploit open Samba shares to access a restricted file.

* **Techniques**: SMB Enumeration, Anonymous Access.
* **Outcome**: Discovered open shares (`IPC$`, `print$`, `workfiles`) on `10.5.5.14` and retrieved the flag `sxij42.txt`.
* **Key Remediation**: Disable anonymous access, update to secure SMB versions (SMBv2/v3), and enforce strong password policies.

### 4. Traffic Analysis (Wireshark) 🦈

**Objective**: Analyze a Packet Capture (`.pcap`) file to find hidden information and credentials.

* **Techniques**: Network Traffic Analysis, Protocol Analysis.
* **Outcome**: Analyzed `SA.pcap`, identified the target IP (`10.5.5.11`), and extracted sensitive employee data sent in clear text.
* **Key Remediation**: Use encryption (TLS/SSL) for all sensitive data transmission and perform regular network audits.

## 🛠️ Tools Used

* **Operating System**: Kali Linux
* **Network Scanning**: Nmap (implied), `gobuster`, `dirb` (alternative directory listing enumeration tool)
* **Web Analysis**: Web Browser (Developer Tools), DVWA (Damn Vulnerable Web App)
* **Packet Analysis**: Wireshark
* **SMB Tools**: `smbclient`
* **Password Cracking**: Crack Station website (e.g., John the Ripper / Hashcat - alternative password cracking tools)

## 📂 Repository Structure

```text
.
├── docs/
│   ├── ethical_hacker_final_capstone_activity.md   # Converted report text
│   └── media/                                      # Images from the report
└── README.md                                       # Project documentation
```

## ⚠️ Disclaimer

This project was conducted in a controlled, educational environment (Cisco NetAcad Lab). All activities were performed on authorized target systems for learning purposes. Ethical hacking content should only be used for educational and defensive purposes.
