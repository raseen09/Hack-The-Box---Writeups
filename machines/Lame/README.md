# Lame

## Overview

Lame is a Hack The Box machine that demonstrates network enumeration, FTP service enumeration, vulnerability research, and exploitation of a vulnerable Samba service.

## Enumeration

### Initial Nmap Scan

A basic Nmap scan was performed to identify the open ports and services running on the target.

<img width="639" height="280" alt="image" src="https://github.com/user-attachments/assets/1cedcce1-785b-4775-a51b-f79b056464e6" />

The scan identified four open ports.

### Comprehensive Nmap Scan

A more comprehensive Nmap scan was then performed to obtain additional information about the discovered services.

<img width="576" height="409" alt="image" src="https://github.com/user-attachments/assets/c8c2ee31-10b0-4a71-ba0b-c80091474089" />

The scan identified an FTP service running on port 21 and indicated that anonymous FTP login was allowed.

##FTP Enumeration

The FTP service was running **VSFTPD 2.3.4**.
<img width="829" height="87" alt="image" src="https://github.com/user-attachments/assets/1066510a-652f-457c-b223-76b8fa719791" />

The version number was researched to determine whether any known vulnerabilities were associated with this version.

Research identified a known VSFTPD 2.3.4 backdoor vulnerability.

> A backdoor is an unauthorized access mechanism that can allow an attacker to execute commands or gain access to a system.
<img width="582" height="439" alt="image" src="https://github.com/user-attachments/assets/2360c7cb-ca70-4bf1-b34f-90ac3acf74da" />
<img width="635" height="517" alt="image" src="https://github.com/user-attachments/assets/65ae7a2f-cec7-4b05-aa98-e48d38335196" />


## Exploitation Attempt

Metasploit was opened using `msfconsole` and the identified VSFTPD exploit was searched for. 

<img width="423" height="35" alt="image" src="https://github.com/user-attachments/assets/fb0fce58-7f94-4454-ac52-65838705cf4a" />
<img width="967" height="162" alt="image" src="https://github.com/user-attachments/assets/845a961c-0d89-4abd-b8e3-50248d6540ba" />

The required options were configured and the exploit was attempted against the target. 

<img width="559" height="243" alt="image" src="https://github.com/user-attachments/assets/d08a0594-bcea-4514-aa6e-2d930e265e0c" />
<img width="555" height="108" alt="image" src="https://github.com/user-attachments/assets/ede912c3-fb1c-46a5-ad94-b95216a4a413" />

The initial exploitation attempt was unsuccessful, so further enumeration was performed.

## Samba Enumeration

Additional investigation focused on the Samba service running on port 139. 
<img width="639" height="27" alt="image" src="https://github.com/user-attachments/assets/a7ca4043-70d4-46bb-9a88-3c9448db6a32" />

The Samba version was identified as: 
**Samba 3.0.20-Debian** 
<img width="869" height="230" alt="image" src="https://github.com/user-attachments/assets/6c996d50-8540-4909-9532-51f592ff937c" />
<img width="701" height="134" alt="image" src="https://github.com/user-attachments/assets/fa58fe80-99a5-45dd-bb5d-8d6732232b24" />

The identified version was researched for known vulnerabilities.

<img width="926" height="98" alt="image" src="https://github.com/user-attachments/assets/b69e997b-e61d-48c6-b05a-f8e27ad7fef8" />


Research revealed a publicly documented exploit affecting this version of Samba.
<img width="396" height="33" alt="image" src="https://github.com/user-attachments/assets/4b8b904c-3ec4-479d-9b30-4854be53a01f" />


## Samba Exploitation

The appropriate Metasploit module was selected and the required options were configured. 
<img width="987" height="252" alt="image" src="https://github.com/user-attachments/assets/24bf4108-cbc2-4e29-9c27-279cb0dcc9ff" />


The exploit was then executed against the target. 

The exploitation was successful and access to the machine was obtained.
<img width="857" height="305" alt="image" src="https://github.com/user-attachments/assets/d15ae501-12a9-4e0e-9af4-90f5fd7563a2" />


## Tools Used

- Nmap
- Metasploit Framework
- msfconsole
- FTP
- Opensource / vulnerability research

## Key Takeaways

- Service enumeration is an important first step when assessing a target.
- Service versions can provide valuable information for vulnerability research.
- Anonymous FTP access should be investigated when it is identified.
- Failed exploitation attempts can provide useful direction for further enumeration.
- Identifying the exact Samba version helped narrow down the relevant vulnerability research.
