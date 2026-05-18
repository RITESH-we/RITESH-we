<div align="center">
  <h1 style="font-family: monospace;">❯ RITESH_PAUL<span style="color: gray;">.exe</span></h1>
  <p><code>SOC Operations</code> · <code>Threat Intelligence</code> · <code>Incident Response</code></p>
  
  <a href="mailto:riteshpaul262@gmail.com"><img src="https://img.shields.io/badge/contact-riteshpaul262%40gmail.com-4fc3c8?style=for-the-badge&labelColor=1c2531&color=4fc3c8" alt="Email"></a>
  <a href="https://linkedin.com/in/riteshpaul262"><img src="https://img.shields.io/badge/network-LinkedIn-4fc3c8?style=for-the-badge&labelColor=1c2531&color=4fc3c8" alt="LinkedIn"></a>
  <a href="https://github.com/RITESH-we"><img src="https://img.shields.io/badge/repo-GitHub-4fc3c8?style=for-the-badge&labelColor=1c2531&color=4fc3c8" alt="GitHub"></a>
  <br><br>
</div>

> **`sys_status:`** 🟢 `analyst online` · `bangalore, in`
> B.Tech Cybersecurity student (graduating 2027) with hands-on SOC experience in a live government Security Operations Center — triaging **50+ alerts daily** using ArcSight SIEM. I build systems, not just learn tools.

---

### `// identity_matrix`
```yaml
ARCSIGHT:       PROFICIENT       DEGREE:   B.TECH CSE
SURICATA IDS:   PROFICIENT       STREAM:   CYBERSECURITY
MITRE ATT&CK:   PROFICIENT       GRAD:     JUL 2027
PYTHON 3.11:    PROFICIENT       BASE:     BANGALORE
SPLUNK:         FAMILIAR         
REDIS STREAMS:  FAMILIAR

```

---

### `// major_project`

## Location-Based Threat Intel Alert System

**Distributed SOC Pipeline — *Detection to Dashboard***

A fully distributed, multi-VM security monitoring system replicating a production Security Operations Center. Detection-to-dashboard across 5 Azure VMs with 3–5 second end-to-end latency.

#### `>_ pipeline_architecture`

```text
[VM-7: Attacker]
       │
       ▼
[VM-1: Suricata IDS + Filebeat] 💻 <-- MY LAYER (Front-Line Sensor)
       │
       ▼
[VM-2: Redis + TI Fetcher]
       │
       ▼
[VM-3: Normaliser ──► Enricher ──► Correlator]
       │
       ▼
[VM-4: PostgreSQL + PostGIS]
       │
       ▼
[VM-5: FastAPI + React Dashboard]

```

#### `>_ vm1_contribution`

* Deployed **Suricata IDS** with AF-PACKET capture and EVE JSON logging.
* Wrote all **15 custom detection rules** covering OWASP Top 10 (signature & threshold-based).
* Configured **Filebeat** for resilient log shipping to VM-2 Redis with cursor persistence.
* Validated against **13 real attack scenarios** (SQLi, XSS, Port Scans, Brute Force) on OWASP Juice Shop.

#### `>_ threat_scoring_model (0-100 composite)`

```text
├── Suricata rule severity × 10 ........................ [+10–30]
├── AbuseIPDB confidence ÷ 10 .......................... [+0–10]
├── Destination IP in TI feeds ......................... [+20]
├── Persistent attacker (5-min window) ................. [+5/evt]
├── External source (not in CMDB) ...................... [+15]
└── Target is datacenter infrastructure ................ [+20]

```

**`sys_stack:`**
   
 
  

---

### `// work_experience`

## In the Field

### 🛡️ SOC Analyst Intern

**OCAC Tower — CSOC · Government of Odisha** | `FEB 2026 – MAR 2026`

> *45-day live engagement*

* Monitored and triaged **50+ live security alerts daily** using ArcSight SIEM in a live government Security Operations Center.
* Investigated a confirmed **brute force attack (MITRE ATT&CK T1110)** — log analysis, IOC enrichment via VirusTotal & AbuseIPDB, managed ITMS tickets, escalated under senior analyst guidance.
* Gained hands-on exposure to real SOC workflows, alert prioritisation, and TTP-based escalation.

### 🔐 Cybersecurity Intern

**EDUNET Foundation** | `MAY 2025 – JUN 2025`

* Built a steganography-based data-hiding system combining AES-256 encryption with LSB steganography to covertly embed data inside PNG/JPG images.

### 🔍 Cybersecurity Intern

**ACMEGRADE** | `JAN 2024 – MAR 2024`

* Performed Nmap-based network reconnaissance and vulnerability assessment in a simulated lab environment.

---

### `// technical_skills`

## Capabilities

| Category | Technologies / Concepts |
| --- | --- |
| **`>_ SIEM & Detection`** | ArcSight SIEM, Splunk, Suricata IDS, Filebeat, Redis Streams |
| **`>_ Threat Intel`** | VirusTotal, AbuseIPDB, AlienVault OTX, IOC Analysis, MITRE ATT&CK |
| **`>_ Incident Response`** | Alert Triage, Log Analysis, Escalation Workflows, ITMS Ticketing |
| **`>_ Network Security`** | Firewall Design, VLAN / DMZ Architecture, Nmap, Cisco Packet Tracer |
| **`>_ Cloud & Infra`** | Microsoft Azure (VMs), AWS EC2/S3 (learning), Python 3.11, Kali Linux |

---

### `// certifications`

## Credentials

* `[Jun 2024]` **CCNA: Introduction to Networks** — *Cisco*
* `[Jan 2026]` **Introduction to CIP** — *OPSWAT Academy*
* `[Jul 2025]` **Tata Cybersecurity Analyst Simulation** — *Forage*
* `[Jan 2025]` **Mastercard Cybersecurity Simulation** — *Forage*
* `[Nov 2023]` **Foundations of Cybersecurity** — *Google*
* `[Dec 2023]` **Fundamentals of Red Hat Enterprise Linux** — *Red Hat*

---
