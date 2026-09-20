# Blue

## Basic Nmap Scan

Perform a basic Nmap scan against the target.

<img width="515" height="303" alt="image" src="https://github.com/user-attachments/assets/3bc7d6ad-f5be-4833-abd7-8af0c8278109" />


## Comprehensive Nmap Scan

Perform a comprehensive Nmap scan to identify additional information about the services and operating system running on the target.

<img width="869" height="477" alt="image" src="https://github.com/user-attachments/assets/deffbf55-3780-4285-8a49-005d8e2fb292" />


The scan identified the target as running:

**Windows 7 Professional 7601 Service Pack 1**

## Vulnerability Research

The identified operating system and SMB service information was researched for publicly documented vulnerabilities.

The **MS17-010 (EternalBlue)** vulnerability was identified as a relevant vulnerability.
<img width="1211" height="120" alt="image" src="https://github.com/user-attachments/assets/93010590-ad8c-43ea-b832-5c3c6eb6043e" />


## Exploitation

The following Metasploit module was used:
<img width="619" height="60" alt="image" src="https://github.com/user-attachments/assets/6da49362-dbe6-4b1a-b871-ad523ce8b348" />

The required options were configured in msfconsole and the exploit was executed against the target.
<img width="811" height="462" alt="image" src="https://github.com/user-attachments/assets/6b9ad3c2-3c64-4d08-b152-42ab6c0b1bdd" />

<img width="833" height="220" alt="image" src="https://github.com/user-attachments/assets/b0e350c6-5c94-4276-b807-5d6946dc9c34" />

PWNED!
