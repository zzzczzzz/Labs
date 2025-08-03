# Reconnaissance Report: id.unity.com

## Target
**Domain:** `id.unity.com`  
**Engagement Type:** Web Application Testing (Bug Bounty)

---

## 1. Subdomain Enumeration Attempt

### Objective
To perform reconnaissance by discovering subdomains associated with the target domain `id.unity.com` in order to identify potential attack surfaces.

### Tools Used
- **Amass**: A reconnaissance tool for subdomain discovery

### Command Executed and Outcome
```bash
amass enum -d id.unity.com -o unity_amass.txt
```
Amass reported:
```
No assets were discovered
```
![Amass result](./screenshots/recon_amass_no_asset_discovered.png)


### Analysis
- The target domain `id.unity.com` appears to be a subdomain itself.
- This reduces the likelihood of discovering further subdomains using standard enumeration tools like Amass.
- As a result, it was determined that subdomain enumeration may not be the most effective strategy in this case.

### Strategy Revision
The focus will shift from subdomain discovery to direct web application analysis and security testing of the main subdomain (`id.unity.com`).

---

## 2. Web Fingerprinting using WhatWeb

### Objective
To identify technologies and server configurations used by the target id.unity.com by performing web fingerprinting. This helps gather preliminary information before deeper analysis.

### Tools Used
WhatWeb: A web scanner that detects technologies used by websites via HTTP responses.

### Command Executed
```bash
whatweb -v id.unity.com
```

### Findings
```
HTTP (http://id.unity.com)

Status: 301 Moved Permanently

Redirected to: https://id.unity.com:443/

HTTPS (https://id.unity.com)

Status: 403 Forbidden

Detected Plugins:

HTML5: Detected via doctype declaration

UncommonHeaders: Header alt-svc was present

Response Headers (HTTPS):
HTTP/1.1 403 Forbidden  
Content-Length: 134  
Content-Type: text/html; charset=UTF-8  
Date: Sun, 03 Aug 2025 16:11:08 GMT  
Alt-Svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000  
Connection: close
```  
### Analysis
The target redirects from HTTP to HTTPS, enforcing secure access.

The server blocks direct access with a 403 Forbidden response, possibly due to IP geofiltering, rate limiting, or user-agent filtering.

No server technology (e.g., Apache, Nginx) was exposed in the headers, which may indicate hardened configurations or use of CDN/WAF

### screenshots

---
