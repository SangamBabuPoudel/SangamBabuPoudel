<div align="center">

![Sangam Babu Poudel — Cybersecurity Portfolio](assets/cyber-banner.svg)

### Cybersecurity Student · Security Operations · Detection Engineering · Network & Cloud Security

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=19&duration=2600&pause=700&color=38BDF8&center=true&vCenter=true&repeat=true&width=850&lines=Monitoring+telemetry+%E2%86%92+Engineering+detections+%E2%86%92+Investigating+alerts;Building+MediShield+SOC+%7C+TrustTrace+AI+%7C+Security+Labs;Learning+AWS+Cloud+Security+and+CompTIA+Security%2B" alt="Animated cybersecurity focus" />

University of South Florida cybersecurity student building defensive security projects around SIEM monitoring, endpoint telemetry, network analysis, phishing detection, and incident investigation. I connect security-relevant activity to auditable events, tested detections, analyst decisions, and documented outcomes.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/sangambabupoudel)
[![Portfolio](https://img.shields.io/badge/Portfolio-View-111827?style=flat-square&logo=vercel&logoColor=white)](https://sangam-dev.vercel.app)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:sangampoudel642@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-SangamBabuPoudel-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/SangamBabuPoudel)

📫 **sangampoudel642@gmail.com**

</div>

---

<div align="center">

### Security Operations → Detection Engineering → Network Security → Cloud Security

</div>

| Current focus | Evidence |
|:---|:---|
| **Build secure, observable systems** | Flask application controls, structured audit telemetry, browser-local analysis |
| **Write and validate detections** | Custom Wazuh rules, regression fixtures, live lab alert validation |
| **Investigate before concluding** | Incident disposition, evidence references, privacy review, documented limitations |

---

## Flagship security work

<p align="center">
  <img src="assets/security-operations.svg" alt="Animated security operations pipeline" width="100%" />
</p>

### MediShield SOC — Healthcare Security Operations & Detection Engineering Lab

<p align="center">
  <img src="https://raw.githubusercontent.com/SangamBabuPoudel/MediShield-SOC/main/docs/public-evidence/screenshots/soc-dashboard.png" alt="MediShield SOC dashboard" width="72%" />
</p>

**Problem:** A valid employee login does not automatically authorize access to every patient record, and denied or abnormal access must become useful security evidence.

I built an isolated educational healthcare application using entirely synthetic data, then connected its security-relevant activity to tamper-evident audit records, custom Wazuh detections, analyst investigation, and an independent privacy-review workflow.

- **Security controls:** five role-specific workspaces, server-side RBAC and patient-level authorization, Argon2 password hashing, CSRF protection, and HMAC-chained, pseudonymized audit events
- **Detection engineering:** four custom Wazuh rules for denied patient access, canary-record access, disabled-account login, and application-calculated bulk access
- **Investigation evidence:** one documented true-positive detection of authorized testing, resolved as Incident #001 with a linked privacy review
- **Verification:** 52 tests reported passing in the documented Python 3.12 release run; Wazuh fixtures, `wazuh-logtest` workflow, live alert evidence, and sanitized screenshots are included
- **Stack:** Python, Flask, SQLAlchemy, SQLite, Windows, Ubuntu, Wazuh, PowerShell

[Repository](https://github.com/SangamBabuPoudel/MediShield-SOC) · [Architecture](https://github.com/SangamBabuPoudel/MediShield-SOC/blob/main/docs/architecture.md) · [Detection engineering](https://github.com/SangamBabuPoudel/MediShield-SOC/blob/main/docs/detection-engineering.md) · [Incident #001](https://github.com/SangamBabuPoudel/MediShield-SOC/blob/main/docs/incident-001.md)

```mermaid
flowchart LR
    A[Application activity] --> B[HMAC-chained audit telemetry]
    B --> C[Wazuh agent<br/>Windows]
    C --> D[Wazuh manager<br/>Ubuntu]
    D --> E[Custom rules<br/>110101–110104]
    E --> F[Alert]
    F -->|Validated snapshot import| G[Analyst investigation]
    G --> H[Incident documentation]
    H --> I[Independent privacy review]
```

> Architectural boundary: MediShield uses a human-initiated, validated alert-snapshot import; it does not claim a live Wazuh API integration or a production healthcare deployment.

### TrustTrace AI — Privacy-First Browser Phishing Detection

<table>
  <tr>
    <td width="50%"><img src="https://raw.githubusercontent.com/SangamBabuPoudel/TrustTraceAI/main/docs/screenshots/popup-dashboard.png" alt="TrustTrace popup dashboard" /></td>
    <td width="50%"><img src="https://raw.githubusercontent.com/SangamBabuPoudel/TrustTraceAI/main/docs/screenshots/high-risk-warning.png" alt="TrustTrace high-risk warning" /></td>
  </tr>
  <tr>
    <td align="center"><sub>Explainable browser-local risk summary</sub></td>
    <td align="center"><sub>Pre-visit high-risk warning</sub></td>
  </tr>
</table>

**Problem:** Phishing defenses need to identify deceptive URLs without treating every login page or brand mention as malicious—or unnecessarily transmitting browsing data.

I built a Chrome Manifest V3 extension with explainable, deterministic risk scoring for lookalike domains, punycode and homoglyph abuse, deceptive authentication URLs, suspicious redirects, fake login patterns, and clipboard risks.

- The published v1.0.0 branch performs core URL analysis locally in the browser and does not require the development FastAPI backend
- Domain-boundary validation prevents a trusted brand name in an attacker-controlled hostname, path, or query from receiving official-domain trust
- Warning pages, caution banners, search-result badges, Clipboard Guardian, and a local Security Report Card make findings actionable
- The release branch includes legitimate and adversarial regression fixtures covering major identity providers and deceptive lookalikes; its seven Node test groups pass across more than 50 URL cases
- **Stack:** JavaScript, Chrome Extension APIs, Manifest V3, HTML/CSS; Python/FastAPI remains in the development branch for local experimentation

[Repository](https://github.com/SangamBabuPoudel/TrustTraceAI) · [Chrome Web Store](https://chromewebstore.google.com/detail/trusttrace-ai/icodclconianombigcapccpilpnngjbg) · [Privacy design](https://github.com/SangamBabuPoudel/TrustTraceAI/blob/main/docs/privacy_design.md) · [Threat model](https://github.com/SangamBabuPoudel/TrustTraceAI/blob/main/docs/threat_model.md)

### Security Operations Home Lab — Endpoint Telemetry to Investigation

I use an isolated VMware lab to practice the full monitoring path rather than treating tools as standalone installations. Documented work includes Windows and Ubuntu systems, Sysmon and Windows Event Logs, a Wazuh agent/server pipeline, Event ID 7040 investigation, Nmap discovery, Wireshark packet analysis, and troubleshooting telemetry gaps.

```mermaid
flowchart LR
    A[Windows activity] --> B[Sysmon / Windows Event Logs]
    B --> C[Wazuh agent]
    C --> D[Wazuh manager]
    D --> E[Indexer]
    E --> F[Dashboard]
    F --> G[Analyst investigation]
```

> The home lab is currently documented in my [portfolio](https://sangam-dev.vercel.app); a dedicated public evidence repository is the next documentation step.

---

## Additional hands-on security work

| Area | Evidence and tools |
|---|---|
| **Security monitoring & detection** | Elastic Stack, Kibana/KQL, authentication-failure and brute-force detections, SIEM dashboards, MITRE ATT&CK mapping |
| **Network security monitoring** | Wireshark, Nmap/Zenmap, Snort, TCP/IP, DNS and HTTP packet analysis |
| **Digital forensics** | Volatility-based process, network-connection, persistence, and memory-image analysis |
| **Authorized security labs** | Hack The Box and TryHackMe exercises using Nmap/NSE, Burp Suite, Metasploit, Hashcat, John the Ripper, SMB/DNS enumeration, and injection concepts |

All offensive-security work is performed in authorized lab or course environments.

## Security stack

<p align="center">
  <img src="https://img.shields.io/badge/Wazuh-005571?style=for-the-badge&logo=wazuh&logoColor=white" alt="Wazuh" />
  <img src="https://img.shields.io/badge/Sysmon-0078D4?style=for-the-badge&logo=windows&logoColor=white" alt="Sysmon" />
  <img src="https://img.shields.io/badge/Elastic-005571?style=for-the-badge&logo=elastic&logoColor=white" alt="Elastic" />
  <img src="https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white" alt="Wireshark" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=111827" alt="Linux" />
</p>

| Focus | Tools and technologies |
|---|---|
| **Security operations** | Wazuh, Sysmon, Elastic Stack, KQL, Windows Event Logs, MITRE ATT&CK |
| **Network security** | Wireshark, Nmap, Snort, TCP/IP, DNS, HTTP |
| **Security testing** | Burp Suite, Metasploit, Hashcat, John the Ripper |
| **Systems** | Windows, Linux/Ubuntu, VMware |
| **Development & automation** | Python, PowerShell, JavaScript, Flask, FastAPI, SQL, Git/GitHub |
| **Cloud — currently learning** | AWS IAM, least privilege, EC2, S3, CloudTrail, shared responsibility, cloud logging |

## Currently building

- Preparing for **CompTIA Security+ SY0-701** — in progress, expected Spring 2027
- Expanding detection engineering, incident investigation, and network engineering skills
- Developing AWS cloud security fundamentals with a long-term goal of adding evidence-backed cloud monitoring to MediShield
- Studying research fundamentals and literature related to uncertainty-aware LLMs and cybersecurity incident investigation

## Contribution activity

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/SangamBabuPoudel/SangamBabuPoudel/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/SangamBabuPoudel/SangamBabuPoudel/output/github-contribution-grid-snake.svg" />
  <img alt="Animated GitHub contribution snake" src="https://raw.githubusercontent.com/SangamBabuPoudel/SangamBabuPoudel/output/github-contribution-grid-snake.svg" />
</picture>

## Education

**University of South Florida**  
**B.S. Computer & Information Systems Security (Cybersecurity)** · Expected May 2028 · GPA: 3.77

- Green & Gold Presidential Scholar
- Dean's List
- Coursework includes Network Security, Intrusion Detection Systems, Malware Analysis, Digital Forensics, Penetration Testing, and Data Structures & Algorithms

---

<div align="center">

Seeking cybersecurity, SOC, security analysis, detection engineering, network security, and cloud security internship opportunities.

[![Email Me](https://img.shields.io/badge/Email_Me-sangampoudel642%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sangampoudel642@gmail.com)

</div>
