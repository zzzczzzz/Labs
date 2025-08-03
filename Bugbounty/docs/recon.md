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
