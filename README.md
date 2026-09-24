# Ritesh Paul — Cybersecurity & SOC Analyst

```
❯ whoami
  role      →  SOC Operations · Threat Detection · Incident Response · Malware Analysis
  status    →  ● Final-Year B.Tech Student (Graduating 2027) · Seeking Entry-Level SOC Analyst Roles
  creds     →  ISC2 Candidate · OPSWAT CIP · Cisco CCNA
  location  →  Bangalore, India
```

[![LinkedIn](https://img.shields.io/badge/LinkedIn-riteshpaul262-4fc3c8?style=flat-square&logo=linkedin&logoColor=white&labelColor=161d27)](https://linkedin.com/in/riteshpaul262)
[![Email](https://img.shields.io/badge/Email-riteshpaul262@gmail.com-4fc3c8?style=flat-square&logo=gmail&logoColor=white&labelColor=161d27)](mailto:riteshpaul262@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-RITESH--we-4fc3c8?style=flat-square&logo=github&logoColor=white&labelColor=161d27)](https://github.com/RITESH-we)
![Status](https://img.shields.io/badge/status-available_for_hire-2d8f94?style=flat-square&labelColor=161d27)
![Graduation](https://img.shields.io/badge/grad-Jul_2027-5a7a90?style=flat-square&labelColor=161d27)

---

Final-year Cybersecurity & Cyber Defense undergraduate and **ISC2 Candidate** with hands-on government CSOC experience in a **live Security Operations Center (ArcSight SIEM)**, triaging **50+ live alerts daily**. Actively engineering an automated malware analysis platform for B.Tech Capstone and developing cloud-native detection engines.

---

## 🚀 Featured Engineering & Security Projects

### 1. [Automated Malware Analysis Platform](https://github.com/RITESH-we/Malware-Analysis) `B.Tech Capstone Project` `Ongoing`

> Python · Docker · YARA · Mandiant capa · pefile · ssdeep · Shannon Entropy

An automated, containerized pipeline for safe static and dynamic analysis of Windows PE malware samples without premature sample detonation.

```text
  MALWARE SAMPLE (.EXE / DLL)
               │
               ▼
┌────────────────────────────────────────────────────────┐
│  Phase 1: Containerized Static Analysis Engine         │
│  • PE Header & Section Parser (pefile)                 │
│  • Shannon Entropy Calculation (File & Section Level)  │
│  • Fuzzy Hashing via ssdeep (Sample Similarity)        │
│  • Mandiant capa Integration (Capability Mapping)      │
│  • Multi-Rule YARA Scanner (Signature Matching)        │
│  • IOC Regular Expression Extractor (IPs, URLs, C2)    │
└───────────────────────────┬────────────────────────────┘
                            │
                            ▼
               [ Schema-Validated JSON Report ]
```

* **My Focus:** Author of the Static Analyzer module. Implemented PE structure parsing, per-section entropy detection for packed/encrypted payloads, fuzzy hashing for variant clustering, and unified JSON contract schema validation.

---

### 2. [Location-Based Threat Intelligence Alert System](https://github.com/RITESH-we/LBTI-Location-Based-Threat-Intelligence-Alert-System-) `Major Project` `Sri Sri University`

> Distributed Multi-VM SOC Pipeline · Detection to Dashboard in **3–5 seconds** · Microsoft Azure · Team of 5

```text
┌────────────┐     ┌─────────────────────────────┐     ┌──────────────────────┐
│  VM-7      │────▶│  VM-1  ★ MY LAYER           │────▶│  VM-2                │
│  Attacker  │     │  Suricata IDS + Filebeat     │     │  Redis + TI Fetcher  │
└────────────┘     └─────────────────────────────┘     └──────────┬───────────┘
                                                                   │
                                                     ┌─────────────▼───────────┐
                                                     │  VM-3                   │
                                                     │  Normalizer → Enricher  │
                                                     │  → Correlator           │
                                                     └─────────────┬───────────┘
                                                                   │
                                                     ┌─────────────▼───────────┐
                                                     │  VM-4                   │
                                                     │  PostgreSQL + PostGIS   │
                                                     └─────────────┬───────────┘
                                                                   │
                                                     ┌─────────────▼───────────┐
                                                     │  VM-5                   │
                                                     │  FastAPI + React Dash   │
                                                     └─────────────────────────┘
```

#### My Contribution — VM-1 (Sensor Layer)
```
[✓] Deployed Suricata IDS with AF-PACKET capture and structured EVE JSON logging
[✓] Authored 15+ custom detection rules covering OWASP Top 10 (SQLi, XSS, Directory Traversal, Brute Force)
[✓] Configured Filebeat for resilient log shipping to VM-2 Redis with cursor persistence
[✓] Deployed OWASP Juice Shop as the vulnerable attack target for signature validation
[✓] Achieved 3–5 second end-to-end alert propagation across all 5 Azure VMs
```

---

### 3. [MiniSOC v2.2 Enterprise — Cloud-Native SIEM & UEBA](https://github.com/RITESH-we/mini-soc) `Personal Project` `Ongoing`

> Python 3.11 · Docker · MITRE ATT&CK v14 · OCSF / ECS Schema · UEBA Engine

An open-schema SIEM/XDR platform synthesizing architectural advantages from enterprise platforms (Splunk, Microsoft Sentinel, IBM QRadar) into a lightweight Python detection engine.

* **Log Normalization:** Normalizes raw events to OCSF/ECS compliant schemas with watermark deduplication.
* **Threat Intel Hub:** Automated IOC reputation lookups against VirusTotal, AbuseIPDB, and AlienVault OTX REST APIs.
* **Behavioral UEBA Engine:** Real-time host and user risk scoring with automated 1-click active response playbooks (firewall rule drops, malicious process kill).

---

### 4. [Oil & Gas OT/IT Network Security Architecture](https://github.com/RITESH-we/oil-and-gas-network) `Minor Project` `Sri Sri University`

> Cisco Packet Tracer · Purdue Model (IEC 62443) · Layer 3 Inter-VLAN Routing · Firewall ACLs

Designed a **resilient, five-zone industrial network architecture** in Cisco Packet Tracer based on the **Purdue Model (IEC 62443)** to isolate critical Operational Technology (OT) and SCADA systems from corporate IT.

```text
  [ INTERNET ]
       │
  ┌────▼─────────────────────────────────────────────────────┐
  │  DMZ (VLAN 50)                                           │
  │  Web Server · Email · DNS · FTP · Reverse Proxy          │
  └────┬─────────────────────────────────────────────────────┘
       │  (Firewall ACLs)
  ┌────▼─────────────────────────────────────────────────────┐
  │  ENTERPRISE ZONE (VLAN 30)                               │
  │  Corporate Workstations · Finance · HR · IT Marketing    │
  └────┬─────────────────────────────────────────────────────┘
       │  (Layer 3 Inter-VLAN Routing)
  ┌────▼─────────────────────────────────────────────────────┐
  │  SECURE OPERATIONS CENTER (VLAN 10)                      │
  │  SIEM · SCADA Server · NMS · Jump Host · Data Historian  │
  └────┬─────────────────────────────────────────────────────┘
       │  (Enforced Jump Server Protocol)
  ┌────▼─────────────────────────────────────────────────────┐
  │  CONTROL ZONE (VLAN 20)                                  │
  │  HMIs · Engineering Workstations · Control Servers       │
  └────┬─────────────────────────────────────────────────────┘
       │  (OT Protocols / Modbus)
  ┌────▼─────────────────────────────────────────────────────┐
  │  FIELD ZONE (VLAN 40)                                    │
  │  PLCs · Sensors (Pressure, Temp, Flow, Gas) · Actuators  │
  └──────────────────────────────────────────────────────────┘
```

---

### 5. [Dual-Layer Image Steganography System](https://github.com/RITESH-we/STEGNO) `EDUNET Internship Project`

> Python · AES-256-CBC · OpenCV · Spatial LSB Pixel Embedding · Steganalysis Defense

A two-tier covert communications tool combining **military-grade AES-256-CBC encryption** with **spatial-domain pixel steganography** to hide confidential data inside lossless PNG images without introducing visual distortion.

```
  Plaintext ──▶ [ AES-256-CBC Encryption ] ──▶ [ LSB Pixel Embedding ] ──▶ Stego Image (PNG)
```
* **Security Resilience:** Ciphertext Shannon entropy (~7.99 bits/byte) resists visual inspection and statistical Chi-Square steganalysis tests. Includes standalone CLI (`stego.py`) and research notebook.

---

## 💼 Operational Work Experience

**SOC Analyst Intern** — OCAC Tower CSOC · Government of Odisha · Bhubaneswar  
*Feb 2026 – Mar 2026* · 45-day live government Security Operations Center engagement
```
→ Monitored and triaged 50+ live security alerts daily using ArcSight SIEM
→ Investigated confirmed true-positive brute force attack (MITRE ATT&CK T1110)
    Log analysis · IOC enrichment via VirusTotal & AbuseIPDB · ITSM ticketing
→ Executed operational SOC procedures: shift handoffs, alert prioritization, and escalation runbooks
```

**Cybersecurity Intern** — EDUNET Foundation · Remote  
*May 2025 – Jun 2025*
```
→ Built a dual-layer data confidentiality system combining AES-256 with LSB steganography
→ Evaluated payload detectability and extraction risks against basic steganalysis tools
```

**Cybersecurity Intern** — ACMEGRADE · Remote  
*Jan 2024 – Mar 2024*
```
→ Conducted Nmap network reconnaissance and vulnerability assessments across simulated subnets
→ Documented attack vectors and remediation recommendations in structured reports
```

---

## 🛠️ Core Skills & Technologies

```
SIEM & Detection     →  ArcSight SIEM · Splunk · Suricata IDS · Filebeat · Redis · OCSF/ECS Schema
Threat Intelligence  →  VirusTotal · AbuseIPDB · AlienVault OTX · IOC Analysis · MITRE ATT&CK v14
Incident Response    →  Alert Triage · True-Positive Analysis · Escalation Workflows · ITSM Ticketing
Malware Analysis     →  Static Analysis · PE Parsing (pefile) · YARA Rules · Mandiant capa · ssdeep
Network Security     →  Purdue Model (IEC 62443) · Cisco Packet Tracer · Firewall ACLs · VLANs · Nmap
Cloud & Systems      →  Microsoft Azure (VMs, NSGs) · Docker · Linux (Kali, Ubuntu) · Python 3.11
Cryptography         →  AES-256 (CBC/GCM) · LSB Steganography · SHA-256 · PKCS7 Padding
```

---

## 📜 Verified Credentials & Certifications

| Certification / Credential | Issuing Organization | Status / Date |
|---|---|---|
| **ISC2 Candidate** | **ISC2** | **Active Credential** |
| **CCNA: Introduction to Networks** | Cisco Networking Academy | Jun 2024 |
| **Introduction to ICS/SCADA (CIP)** | OPSWAT Academy | Jan 2026 |
| **Foundations of Cybersecurity** | Google Career Certificates | Nov 2022 |
| **Fundamentals of Red Hat Enterprise Linux** | Red Hat | Dec 2023 |
| **McKinsey Forward Program** | McKinsey & Company | 2026 |
| **Cybersecurity Job Simulations** | Tata & Mastercard (Forage) | 2025 |

---

## 🎓 Education

```
B.Tech — CSE (Cybersecurity & Cyber Defense)
Sri Sri University · Cuttack, Odisha · Expected Jul 2027

Higher Secondary · Class XII — Science (PCMCS)
Kendriya Vidyalaya AFS Yelahanka · Bangalore · 2023
```

---

## 📬 Contact & Connect

```
❯ ssh ritesh@bangalore

  email     →  riteshpaul262@gmail.com
  linkedin  →  linkedin.com/in/riteshpaul262
  github    →  github.com/RITESH-we
  phone     →  +91 95472 44315
  location  →  Bangalore, India
```

*Final-year student actively seeking entry-level SOC Analyst (L1), Incident Response, or Threat Detection opportunities.*
