🌐 Cybersecurity Home Lab
OWASP A5 — Security Misconfiguration Assessment

This project demonstrates a simple cybersecurity home lab built using VirtualBox, focusing on identifying and testing OWASP A5: Security Misconfiguration vulnerabilities on Metasploitable2.

🛠 Lab Setup

Virtual Machines Used

Kali Linux — attacker

Metasploitable2 — vulnerable machine

Ubuntu — normal host

Network

Internal Network: labnet

Verified using ping and Nmap host discovery

🔍 What I Tested

Using Kali Linux, I scanned Metasploitable2 and discovered several misconfigurations:

FTP anonymous login enabled

Telnet service active with default credentials

Outdated OpenSSH version

Apache Tomcat default page exposed

SMB information leakage

These represent common weaknesses under OWASP A5: Security Misconfiguration.

⚔️ What I Exploited

I performed three offensive tests to demonstrate real-world impact:

✔ 1. FTP Anonymous Login

Gained directory access using the anonymous account.

✔ 2. Telnet Default Credentials

Logged in using default credentials (msfadmin/msfadmin) and obtained a shell.

✔ 3. Tomcat Default Interface Exposure

Viewed Tomcat’s default management page leaking version and admin paths.

📘 What I Learned

This home lab helped me understand:

How attackers exploit misconfigurations

How to use Nmap for scanning and service enumeration

How outdated or improperly configured services become attack vectors

How to safely perform exploitation in a controlled environment

Why proper system hardening is essential in real deployments
