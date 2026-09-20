# Legacy

## Overview

Legacy is a Hack The Box machine demonstrating Windows service enumeration and exploitation of vulnerabilities affecting Windows XP.

## Enumeration

### Nmap Scan

A basic Nmap scan was performed to identify open ports and available services on the target.
<img width="644" height="211" alt="image" src="https://github.com/user-attachments/assets/2809f01d-425d-435e-a2ff-c368586207d3" />


A comprehensive Nmap scan was then performed to gather additional information about the discovered services.
<img width="898" height="270" alt="image" src="https://github.com/user-attachments/assets/fd45c9e4-874e-4072-b53f-c8e523b5f059" />


### SMB Enumeration

The comprehensive scan identified a Windows service exposed on port 445.

Further enumeration identified the operating system as **Windows XP**, and additional investigation identified the system as **Windows XP SP3**.
<img width="775" height="342" alt="image" src="https://github.com/user-attachments/assets/a5a18f72-f95f-48be-bb6b-559c26d00cc1" />


## Vulnerability Research

Windows XP SP3 is an unsupported operating system with numerous publicly documented vulnerabilities.

The identified operating system and service information was researched for known vulnerabilities.

One relevant vulnerability identified during the research was **MS08-067**, a vulnerability affecting the Windows Server service.
<img width="1201" height="90" alt="image" src="https://github.com/user-attachments/assets/e413d2e0-c1e8-46d5-8a47-5c4d5f101d02" />
<img width="405" height="35" alt="image" src="https://github.com/user-attachments/assets/9418406d-5bf1-4435-a001-48e5061eb301" />


## Exploitation

The Metasploit Framework was used to investigate the identified vulnerability.

The following Metasploit module was selected:
<img width="589" height="45" alt="image" src="https://github.com/user-attachments/assets/a5ef7641-cb86-46f2-81ea-91115fa5056a" />

The exploitation was successful and shell access to the machine was obtained.

<img width="650" height="413" alt="image" src="https://github.com/user-attachments/assets/6a2f14f8-2060-43de-8b99-326ef478433a" />

