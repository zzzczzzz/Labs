# Ethical Hacking – Manual Techniques and Offensive Labs

This project showcases hands-on ethical hacking techniques performed in a controlled lab environment. The labs simulate real-world attack scenarios across web applications, services, networks, and mobile platforms.

## Key pointed out Labs

These are the most impactful and technically relevant labs in this project:

1. **Stored XSS & SQL Injection**
   - Demonstrated successful exploitation of common web application vulnerabilities.
   - Performed union-based SQL injection to extract system information and files.
   - Injected persistent JavaScript to simulate cookie theft and UI manipulation.

2. **Web Vulnerability Scanning (Skipfish & Uniscan)**
   - Automated scanning to uncover issues like XSS vectors, hidden directories, no CSRF protection.
   - Analyzed real HTTP responses and server configurations.
   - Emphasized importance of patch management and secure design.

3. **DNS Enumeration & Passive Recon**
   - Compared `theHarvester` and `Sublist3r` for domain discovery.
   - Identified VM's DNS records, subdomains, and email servers using DNSDumpster.
   - Highlighted attacker reconnaissance techniques.

4. **Exploiting Outdated Apache & Samba Services**
   - Identified vulnerable Apache version (1.3.20) and mapped CVEs.
   - Used ExploitDB to find relevant public exploits.
   - Delivered payload via web service and gained access to Windows lab machine.
   - Demonstrated post-exploitation with commands like `shutdown` and `zombies 0`.
   - Emphasized importance of patch management and exploit-based attack vectors.


---

## 🔍 Full Lab List

| Lab No. | Topic | Key Focus |
|--------|-------|-----------|
| 1 | Passive Recon | `Harvester`, `Sublist3r` |
| 2 | Google Dorking | Domain reconnaissance |
| 3 | DNS Enumeration | `DNSDumpster`, record mapping |
| 4–5 | Port Scanning & Service Discovery | `nmap`, Apache/SSH outdated services |
| 6 | Network Enumeration | User info, weak password policy |
| 8–10 | Brute Force & Service Exploits | `Hydra`, `VNC`, `Postgres`, `MySQL` |
| 11 | Web App Scanning | `Skipfish`, `Uniscan` |
| 12–13 | Web Exploits | Stored XSS, SQL Injection |
| 14 | Privilege Escalation | `uname`, `netstat`, reverse shell |
| 15 | APK Permissions Audit | Static Android app inspection |
| 16 | Wi-Fi Recon | Spectrum & encryption audit |
| 17 | Android Backdoor | Malicious APK generation using `msfvenom` |

---

## 🛠 Tools Used
- `theHarvester`, `Sublist3r`, `DNSDumpster`
- `nmap`, `Hydra`, `Metasploit`, `Skipfish`, `Uniscan`
- SQL injection payloads, XSS vectors
- Reverse engineering tools: `apktool`, `msfvenom`, `Meterpreter`
- `Wireshark`, `netcat`

---

##  Key Learnings
- Reconnaissance using passive and active techniques
- Exploiting insecure configurations (XSS, SQLi, weak passwords)
- Enumeration of networked systems and services
- Privilege escalation and reverse shell techniques
- Android APK exploitation and Wi-Fi security analysis

---

## PDF files
See the [`pdf_files`](./pdf_files) folder for selected evidence of attack success, tool output, and payload injection.

---

## Reference
Full detailed lab report available in [`cp3414_ethical_hacking_lab.pdf`](./full_reports/cp3414_ethical_hacking_lab.pdf)


