# Network Scan Results Summary

## Project: Task 1 — Scan Your Local Network for Open Ports (Nmap)

### Network Scanned
- Subnet: `192.168.1.0/24`  
- Date of Scan: [2025-09-22]  
- Tool: Nmap (with root privileges for SYN/OS detection scans)  

---

### Hosts Discovered
- 192.168.1.10 — Printer  
- 192.168.1.14 — Mobile Device  
- 192.168.1.23 — Workstation / Server  



### Detailed Findings (Example Host)

**Target:** `192.168.1.23`  
- **Open Ports & Services**  
  - `22/tcp` — SSH (OpenSSH 7.6p1)  
  - `80/tcp` — HTTP (Apache httpd 2.4.29)  
  - `445/tcp` — Microsoft-DS (SMB file sharing)  

- **OS Detection:** Linux (likely Ubuntu)   


### Potential Security Risks
- **SSH (22):** If password login is enabled, risk of brute-force attack.  
- **HTTP (80):** Outdated Apache version could be vulnerable.  
- **SMB (445):** Exposing SMB service may allow unauthorized file access or exploitation.  

---

### Recommendations
- Disable password-based SSH; use key-based authentication.  
- Keep web server updated with security patches.  
- Restrict or disable SMB access unless required.  
- Apply firewall rules to limit exposure of sensitive services.  
