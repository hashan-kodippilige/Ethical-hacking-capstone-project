# Ethical Hacking Capstone — Full Penetration Testing Engagement

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Hack%20The%20Box-9FEF00?style=for-the-badge&logo=hackthebox&logoColor=black" />
  <img src="https://img.shields.io/badge/Type-Capstone%20Project-E22C2C?style=for-the-badge&logo=target&logoColor=white" />
  <img src="https://img.shields.io/badge/Targets-Linux%20%7C%20Windows-4B4B4B?style=for-the-badge&logo=linux&logoColor=white" />
  <img src="https://img.shields.io/badge/Tools-Nmap%20%7C%20Metasploit%20%7C%20LinPEAS-557C94?style=for-the-badge&logo=kalilinux&logoColor=white" />
</p>

> End-to-end penetration testing engagement conducted in a controlled Hack The Box environment — covering information gathering, vulnerability assessment, exploitation, privilege escalation, lateral movement, post-exploitation, and professional security reporting with remediation planning.

---

## Overview

This capstone project simulates a **real-world black-box penetration test** against a multi-target environment including both Linux and Windows systems. The engagement follows industry-standard penetration testing methodology and produces professional-grade deliverables including a full findings report with risk ratings and remediation recommendations.

**Course:** Pentest in a Nutshell — Hack The Box Academy  
**Certification:** Hack The Box Academy — Dec 2025  
**Environment:** Controlled HTB lab | Kali Linux attacker machine

---

## Scope & Targets

| Target | OS | Role |
|--------|-----|------|
| Target 1 | Ubuntu Linux Server | Primary target — web & file services |
| Target 2 | Windows Server 2019 | Secondary target — enterprise services |

**Assessment Areas:**
- Network services and open ports
- Authentication mechanisms
- Web application security
- System configurations and misconfigurations
- User privileges and escalation paths
- Sensitive data exposure

---

## Penetration Testing Methodology

```
Phase 1: Information Gathering
    └── Host discovery, port scanning, service/version enumeration (Nmap, WPScan)

Phase 2: Vulnerability Identification
    └── FTP misconfigs, exposed credentials, web vulns, weak access controls

Phase 3: Exploitation
    └── Initial access, authentication bypass, credential reuse, RCE

Phase 4: Privilege Escalation
    └── LinPEAS enumeration, misconfigured sudo, writable script exploitation

Phase 5: Post-Exploitation
    └── Sensitive data discovery, config review, lateral movement

Phase 6: Reporting
    └── Findings documentation, risk ratings, remediation recommendations
```

---

## Tools Used

| Phase | Tool | Purpose |
|-------|------|---------|
| Reconnaissance | Nmap | Port scanning and service enumeration |
| Web Recon | WPScan | WordPress vulnerability scanning |
| Exploitation | Metasploit Framework | Vulnerability exploitation |
| Exploitation | SSH / FTP | Service-based access |
| Post-Exploit Enum | LinPEAS | Linux privilege escalation enumeration |
| Post-Exploitation | SCP / SSH | File transfer and remote access |
| Reporting | Manual | Risk assessment and remediation planning |

---

## Findings Summary

### High Severity

| Finding | Description | Impact |
|---------|-------------|--------|
| Anonymous FTP Access | FTP service allows unauthenticated file access | Data exposure, credential theft |
| Exposed SSH Private Keys | Private key files accessible via FTP | Full system compromise |
| Credential Reuse | Credentials valid across multiple services | Lateral movement |
| Privilege Escalation — Sudo Misconfiguration | Writable scripts executed as root via sudo | Root access achieved |
| Remote Code Execution | Exploitable service version identified | Full system control |

### Medium Severity

| Finding | Description | Impact |
|---------|-------------|--------|
| Excessive Service Exposure | Unnecessary services open on external interface | Increased attack surface |
| Directory Listing Enabled | Web server exposes directory contents | Information disclosure |
| Internal Documentation Disclosure | Sensitive internal files publicly accessible | Reconnaissance aid |

### Low Severity

| Finding | Description | Impact |
|---------|-------------|--------|
| Command History Exposure | Shell history files contain sensitive commands | Credential leakage risk |

---

## Attack Chain

```
Nmap Scan
    │
    ├── FTP (Port 21) ──→ Anonymous Login ──→ SSH Private Key Found
    │                                               │
    │                                               ▼
    │                                         SSH Access (User)
    │                                               │
    │                                               ▼
    ├── Web (Port 80) ──→ WPScan ──→ Vulns Found   LinPEAS Enumeration
    │                                               │
    │                                               ▼
    └──────────────────────────────────────→ Sudo Misconfiguration
                                                    │
                                                    ▼
                                              Root Access ✅
```

---

## Remediation Recommendations

| Finding | Recommended Fix |
|---------|----------------|
| Anonymous FTP | Disable anonymous access; enforce authentication |
| Exposed SSH Keys | Remove private keys from shared directories; rotate credentials |
| Credential Reuse | Enforce unique credentials per service; use a secrets manager |
| Sudo Misconfiguration | Audit sudoers file; restrict writable scripts from sudo execution |
| Directory Listing | Disable directory listing in web server configuration |
| Excessive Services | Apply principle of least exposure; close unneeded ports |

---

## Repository Contents

```
Ethical-hacking-capstone-project
├── 📄 README.md
└── 📋 Hack the Box-Project-Hashan Kodippilige.pdf   ← Full pentest report
```

---

## Skills Demonstrated

`Penetration Testing` `Network Reconnaissance` `Nmap` `WPScan` `Metasploit` `FTP Exploitation` `SSH` `LinPEAS` `Linux Privilege Escalation` `Sudo Misconfiguration` `Credential Reuse` `Post-Exploitation` `Risk Assessment` `Security Reporting` `Remediation Planning` `Kali Linux` `Hack The Box`

---

## Real-World Relevance

This capstone simulates the full lifecycle of a professional penetration testing engagement — the type of work performed by:
- **Penetration Testers** — structured engagement methodology, professional reporting
- **Red Team Operators** — multi-target exploitation, lateral movement, privilege escalation
- **Security Consultants** — risk-rated findings with actionable remediation
- **PhD Researchers** — empirical offensive security methodology and defense-in-depth analysis

---

## Disclaimer

This engagement was conducted exclusively within an **authorized, controlled Hack The Box educational environment** for academic and cybersecurity training purposes. No real-world systems were targeted.

---

## Author

**Hashan Kodippilige**  
M.S. Cybersecurity — Minnesota State University Moorhead  
📧 hashansharindu@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/hashankodippilige/)  
🐙 [GitHub](https://github.com/hashan-kodippilige)
