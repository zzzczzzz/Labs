# Cloud and Data Centre Security

## Key Lab Summary: WordPress Deployment Security and Azure Audit

---

## Key Activities Performed

### WordPress Security Hardening (K3s Cluster)
- Deployed WordPress in a Kubernetes environment using K3s.
- Performed dynamic security testing to identify:
  - TLS version and certificate issues.
  - Missing ECC usage (replaced RSA with ECDSA, 2048 → 256-bit).
  - Insecure HTTP (resolved via HTTP→HTTPS redirect with middlewares).
  - Use of default Traefik certificate (patched with custom cert).
- Conducted vulnerability testing via **WPScan**:
  - Detected 13 CVEs in default WordPress version.
  - Downgraded to 6.5.4 to reduce CVEs to 3.

### Web Application Firewall (WAF)
- Attempted WAF integration into the deployment YAML.
- Understood ModSecurity and Nginx-based WAFs for blocking SQLi and path traversal.
- Despite unsuccessful WAF implementation, clearly documented limitations and concepts.

---

## Azure Cloud Audit & Recommendations

### Compute Resources
- Assessed virtual machines (GitLab & K3S) for:
  - Use of RSA SSH keys (recommended ECC).
  - Lack of Azure Policy, auto-shutdown, backup configs.

### Network & Storage
- Identified:
  - Public IPs without DNS labels.
  - No DDoS protection or private endpoints.
  - OS Disks using AllowAll firewall rules.
- Proposed:
  - DDoS protection, VNet peering, Azure Firewall.
  - RBAC enforcement and encryption via CMK (Customer-Managed Keys).

### Security Components
- Reviewed NSGs:
  - Open SSH (22), HTTP (80), HTTPS (443) to all.
  - Recommended least-privilege configuration and alert rule enablement.
- Emphasized:
  - WAF implementation for web protection.
  - Real-time IT alerts for threat response.

---

## Tools Used
- **WPScan** (vulnerability scanning)
- **Traefik** (Ingress controller for TLS/HTTPS management)
- **Azure Portal** (monitoring network, compute, NSGs)
- **Kubernetes (K3s)** for container orchestration
- **YAML configuration** for Kubernetes/Ingress

---

## PDF Evidence
- [wordpress_cloud_security](./files/wordpress_cloud_security.pdf) for full details and screenshots.

## Cloud Package
- [Deployment ZIP file](./files/cloud_deployment.zip)


