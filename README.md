Cybersecurity Home Lab — OWASP A5 Security Misconfiguration

This project demonstrates a simple cybersecurity home lab built using VirtualBox, with the goal of identifying and testing OWASP A5: Security Misconfiguration vulnerabilities.

Lab Setup

Kali Linux – attacker machine

Metasploitable2 – intentionally vulnerable target

Ubuntu – normal host

Network mode: Internal Network (labnet)

Verified connectivity using ping and Nmap host discovery.

What I Tested

Using Kali Linux, I scanned Metasploitable2 and found several misconfigurations, including:

FTP anonymous login enabled

Telnet service active with default credentials

Outdated OpenSSH version

Apache Tomcat default page exposed

SMB information leakage

What I Exploited

I performed three simple offensive tests:

Logged into FTP using anonymous access

Accessed Metasploitable2 over Telnet using default credentials

Viewed Tomcat default management interface leak

These were done to show how misconfigurations allow easy system compromise.

What I Learned

This lab helped me understand:

How misconfigurations open the door for attackers

How to scan systems using Nmap

How basic network services can be exploited

How to safely test vulnerabilities in a controlled environment

The importance of hardening and updating systems

Fix Recommendations

Disable anonymous FTP

Remove Telnet

Update SSH

Restrict SMB

Harden Tomcat

Use strong passwords

Apply updates and patches regularly

Full Report
