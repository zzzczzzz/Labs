## Recon Summary – id.unity.com

### Target
- **Scope**: `id.unity.com`
- **Type**: Web Application Bug Bounty

### Tools Used
- Amass, WhatWeb, whois, dig, curl, waybackurls, dirsearch

### Key Recon Steps & Results

| Step                   | Description                                | Outcome                                                    |
|------------------------|--------------------------------------------|-------------------------------------------------------------|
| Subdomain Enumeration  | Searched for subdomains using Amass        | No assets discovered (target is a subdomain itself)         |
| Web Fingerprinting     | Probed server behavior via WhatWeb         | HTTPS enforced, 403 Forbidden response on direct access      |
| WHOIS & DNS Info       | Used whois and dig                         | Unity uses Akamai CDN and MarkMonitor as registrar          |
| HTTP Header Analysis   | Analyzed headers with curl                 | Security headers present, session cookies issued            |
| Historical URL Search  | Queried Wayback Machine with waybackurls  | 379 filtered paths found (`/api`, `/admin`, `/debug`, etc.) |
| JavaScript Recon       | Collected JS URLs for LinkFinder           | Abandoned due to non-usable HTML/404 responses              |
| CORS Policy Testing    | Origin injection via curl                  | CORS securely configured, no reflection of origin headers   |
| Authentication Flow    | Simulated login attempts                   | Lockout message observed, redirect chains mapped            |
| Directory Bruteforce   | Scanned with dirsearch                     | No sensitive paths found, 429 rate-limiting triggered       |


