# Lame

## Overview

Lame is a Hack The Box machine that demonstrates network enumeration, FTP service enumeration, vulnerability research, and exploitation of a vulnerable Samba service.

## Enumeration

### Initial Nmap Scan

A basic Nmap scan was performed to identify the open ports and services running on the target.

The scan identified four open ports.

### Comprehensive Nmap Scan

A more comprehensive Nmap scan was then performed to obtain additional information about the discovered services.

The scan identified an FTP service running on port 21 and indicated that anonymous FTP login was allowed.

##FTP Enumeration

The FTP service was running **VSFTPD 2.3.4**.

The version number was researched to determine whether any known vulnerabilities were associated with this version.

Research identified a known VSFTPD 2.3.4 backdoor vulnerability.

> A backdoor is an unauthorized access mechanism that can allow an attacker to execute commands or gain access to a system.

## Exploitation Attempt

Metasploit was opened using `msfconsole` and the identified VSFTPD exploit was searched for. 

The required options were configured and the exploit was attempted against the target. 

The initial exploitation attempt was unsuccessful, so further enumeration was performed.

## Samba Enumeration

Additional investigation focused on the Samba service running on port 139. 

The Samba version was identified as: 
**Samba 3.0.20-Debian** 

The identified version was researched for known vulnerabilities.

Research revealed a publicly documented exploit affecting this version of Samba.

## Samba Exploitation

The appropriate Metasploit module was selected and the required options were configured. 

The exploit was then executed against the target. 

The exploitation was successful and access to the machine was obtained.

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
