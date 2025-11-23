# Cybersecurity Home Lab  
## OWASP A5 Security Misconfiguration Assessment

This project shows how I built a small cybersecurity home lab using VirtualBox. I used Kali Linux to scan and test Metasploitable2 for OWASP A5 Security Misconfigurations. Ubuntu was used as a normal machine for network testing.

# Lab Setup

## Virtual Machines
- Kali Linux (attacker machine)
- Metasploitable2 (vulnerable machine)
- Ubuntu (normal host)

## Network
- Network type: Internal Network  
- Network name: labnet  
- Basic connectivity test:
```
ping 192.168.100.x
```

- Host discovery:
```
sudo nmap -sn 192.168.100.0/24
```

# Misconfigurations Found (OWASP A5)

## 1. FTP Anonymous Login
The FTP service allowed anonymous login without a password.
```
ftp 192.168.100.20
Username: anonymous
Password: (press Enter)
```

## 2. Telnet Enabled with Default Credentials
Telnet is insecure and uses plain text login. The default credentials worked.
```
telnet 192.168.100.20
msfadmin
msfadmin
```

## 3. Outdated OpenSSH Version
An old version of OpenSSH was running on the target.
```
nmap -A 192.168.100.20
```

## 4. Apache Tomcat Default Page Exposed
The Tomcat service on port 8180 exposed its default page.
```
http://192.168.100.20:8180
```

## 5. Samba Misconfigurations
SMB services were running with possible vulnerabilities.
```
sudo nmap --script smb-vuln* -p 139,445 192.168.100.20
```

# Exploitation Steps

## FTP Anonymous Login
```
ftp 192.168.100.20
ls
```

## Telnet Access
```
telnet 192.168.100.20
msfadmin / msfadmin
```

## Service Enumeration
```
sudo nmap -A -T4 192.168.100.20
```

# What I Learned

- How to set up an isolated lab in VirtualBox  
- How to scan a machine using Nmap  
- How to identify misconfigurations  
- How insecure services like Telnet and anonymous FTP can be abused  
- The importance of system patching and disabling unused services  



Check out my portfolio website: [www.sandhildesilva.com](https://www.sandhildesilva.com)

