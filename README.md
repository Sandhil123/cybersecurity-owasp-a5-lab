🌐 Cybersecurity Home Lab
OWASP A5 Security Misconfiguration Assessment

This project shows how I built a cybersecurity home lab using VirtualBox to identify and test OWASP A5 Security Misconfiguration vulnerabilities on Metasploitable2.

Lab Setup

Virtual Machines

Kali Linux (attacker)

Metasploitable2 (vulnerable machine)

Ubuntu (normal host)

Network

Internal Network: labnet

Verified using ping tests and Nmap host discovery

What I Tested

Using Kali Linux, I scanned Metasploitable2 and found several misconfigurations:

FTP anonymous login allowed

Telnet active with default credentials

Outdated OpenSSH version

Apache Tomcat default page exposed

SMB information leakage

What I Exploited
1. FTP Anonymous Login

Logged into the FTP service using the anonymous account.

2. Telnet Default Credentials

Logged in using the default credentials msfadmin/msfadmin and gained shell access.

3. Tomcat Default Interface Exposure

Viewed the Tomcat default page which exposed version and admin path information.

What I Learned

This lab helped me understand:

How attackers exploit misconfigurations

How to use Nmap for scanning and enumeration

How weak or outdated services can be compromised

How to safely perform exploitation in a controlled environment

Why system hardening and patching are important

Recommendations

Disable anonymous FTP

Remove Telnet and use SSH

Update OpenSSH

Disable or restrict SMB

Remove Tomcat default applications

Use strong passwords and keep services updated
