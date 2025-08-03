# Vulnerability Assessment – Nessus Scan on 192.168.7.0/24  

This project presents a vulnerability assessment conducted using **Nessus Essentials** on a subnet environment containing a **Windows machine**, **Linux web server**, and **Raspberry Pi**. The objective was to identify, analyze, and recommend remediation for discovered vulnerabilities.

---

## Key Takeaways

- Identified critical vulnerabilities like **outdated Apache**, **unsupported Windows OS**, and **OpenSSL/OpenSSH flaws**.
- Demonstrated how simple updates or secure configurations could mitigate major threats.
- Emphasized the importance of **regular patching**, **protocol hardening**, and **disabling insecure methods** (e.g., HTTP TRACE).

---

## Scan Environment

- **Scanner**: Nessus Essentials  
- **Subnet Scanned**: 192.168.7.0/24  
- **Target Hosts**:  
  - `192.168.7.6` – Raspberry Pi  
  - `192.168.7.7` – Linux Web Server  
  - `192.168.7.8` – Windows 7 Host  
  - `192.168.7.9` – Apache Web Server

---

## Highlighted Findings

### 192.168.7.6 – Raspberry Pi

- No critical vulnerabilities.
- Minor issues: Exposed **NTP service**, **ICMP timestamp leak** (may support time-based attacks).

### 192.168.7.7 – Linux Web Server

- **Missing security headers** (e.g., `X-Frame-Options`).
- **HTTP/2 in cleartext** – susceptible to packet sniffing.

### 192.168.7.8 – Windows 7

- **Unsupported OS** – critical vulnerability due to lack of vendor support.
- **SMB signing not enforced** – may allow **man-in-the-middle** (MITM) attacks.

### 192.168.7.9 – Apache Server

- **Critical outdated versions** of Apache (`1.3.x`), vulnerable to:
  - **Chunked encoding overflow**
  - **Request smuggling**
  - **Remote Code Execution**
- **Outdated OpenSSH & OpenSSL** – known exploits exist.
- **Insecure SSL protocols (SSLv2/v3)** supported.
- Allows **TRACE/OPTIONS methods** and contains **browsable directories**.

---

## Recommendations

- Patch and upgrade **Apache**, **OpenSSL**, **OpenSSH** to supported versions.
- Enforce **SMB signing**, disable insecure protocols (SSLv2/3, TRACE).
- Implement secure headers (`X-Frame-Options`, `Content-Security-Policy`).
- Replace **Windows 7** with a currently supported OS.
- Follow structured patching lifecycle (e.g., staging, testing, monitoring).

---

## Report

[Nessus_Assessment.pdf](./nessus_assessment.pdf)

