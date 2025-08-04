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
![WhatWeb HTTP 301 Redirect](./screenshots/recon_whatweb_http_redirect.png)
![WhatWeb HTTPS 403 Forbidden](./screenshots/recon_whatweb_https_forbidden.png)

---

## 3. WHOIS Information Gathering

### Objective
To gather domain registration and ownership information about the main domain unity.com for passive reconnaissance purposes. Although the testing scope is limited to id.unity.com, analyzing the WHOIS data of the parent domain can provide insight into the organization's structure and hosting choices.

### Tool Used
whois: A command-line utility to retrieve WHOIS database information.

### Command Executed
```
whois unity.com
Summary of Results
markdown
Copy
Edit
Domain Name: unity.com
Registrar: MarkMonitor Inc.
Registrant Organization: Unity Technologies SF
Creation Date: 1995-08-07
Expiry Date: 2026-08-06
Domain Status:
  - clientDeleteProhibited
  - clientTransferProhibited
  - clientUpdateProhibited
  - serverDeleteProhibited
  - serverTransferProhibited
  - serverUpdateProhibited
Name Servers:
  - asia3.akam.net
  - eur2.akam.net
  - eur5.akam.net
  - ns1-105.akam.net
  - ns1-8.akam.net
  - usc4.akam.net
  - use4.akam.net
  - usw4.akam.net
DNSSEC: unsigned
```

## Analysis
The domain unity.com is managed by MarkMonitor, a registrar commonly used by large enterprises.

The domain has been registered since 1995, indicating a well-established organization.

Name servers point to Akamai, suggesting use of a Content Delivery Network or Web Application Firewall.

Various domain status flags prevent unauthorized transfers or changes, indicating strong administrative control.
