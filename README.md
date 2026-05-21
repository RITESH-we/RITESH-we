# Ritesh Paul — Cybersecurity Analyst

```
❯ whoami
  role      →  SOC Operations · Incident Response · Threat Intelligence · SIEM
  status    →  ● available for internships & SOC roles
  location  →  Bangalore, India
```

[![LinkedIn](https://img.shields.io/badge/LinkedIn-riteshpaul262-4fc3c8?style=flat-square&logo=linkedin&logoColor=white&labelColor=161d27)](https://linkedin.com/in/riteshpaul262)
[![Email](https://img.shields.io/badge/Email-riteshpaul262@gmail.com-4fc3c8?style=flat-square&logo=gmail&logoColor=white&labelColor=161d27)](mailto:riteshpaul262@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-RITESH--we-4fc3c8?style=flat-square&logo=github&logoColor=white&labelColor=161d27)](https://github.com/RITESH-we)
![Status](https://img.shields.io/badge/status-available-2d8f94?style=flat-square&labelColor=161d27)
![Grad](https://img.shields.io/badge/grad-Jul_2027-5a7a90?style=flat-square&labelColor=161d27)

---

B.Tech Cybersecurity student (graduating 2027) with hands-on SOC internship experience in a **live government Security Operations Center**, triaging **50+ alerts daily** using ArcSight SIEM. I build systems, not just learn tools.

---

## // Major Project — Location-Based Threat Intelligence Alert System

> Distributed, multi-VM SOC pipeline · Detection to dashboard in **3–5 seconds** · 5 Azure VMs · Team of 5

### Pipeline Architecture

```
┌────────────┐     ┌─────────────────────────────┐     ┌──────────────────────┐
│  VM-7      │────▶│  VM-1  ★ MY LAYER           │────▶│  VM-2                │
│  Attacker  │     │  Suricata IDS + Filebeat     │     │  Redis + TI Fetcher  │
└────────────┘     └─────────────────────────────┘     └──────────┬───────────┘
                                                                   │
                                                     ┌─────────────▼───────────┐
                                                     │  VM-3                   │
                                                     │  Normaliser → Enricher  │
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

### My Contribution — VM-1 (Sensor Layer)

```
[✓]  Deployed Suricata IDS with AF-PACKET capture and EVE JSON logging
[✓]  Wrote all 15 custom detection rules covering OWASP Top 10
       SQLi · XSS · Directory Traversal · Brute Force · Port Scan
       Signature-based + threshold-based detection logic
[✓]  Configured Filebeat for resilient log shipping to VM-2 Redis
       Cursor persistence → zero event loss on restart
       Sensor metadata enrichment → sensor_id, sensor_location
[✓]  Deployed OWASP Juice Shop as attack target
[✓]  Validated all 15 rules across 13 real attack scenarios
```

### Key Technical Decisions

| Decision | Implementation | Why It Matters |
|---|---|---|
| **Event-driven microservices** | Redis Streams + Consumer Groups; 5 Python services | At-least-once delivery; services fail independently |
| **3-source TI correlation** | Cache-first batch — VirusTotal, AbuseIPDB, AlienVault OTX | Stays within free API rate limits; O(1) enrichment |
| **Geospatial storage** | PostGIS `GEOGRAPHY(Point, 4326)` + GIST index | Real spherical-earth queries; spatial analytics without a commercial SIEM |
| **Custom IDS ruleset** | 15 Suricata rules — signature + threshold — OWASP Top 10 | Brute force & port scan need threshold rules; signatures alone miss them |
| **Alert lifecycle mgmt** | Acknowledge / Resolve + full `audit_log` table | PCI-DSS / ISO 27001 compliant; mirrors real SOC workflows |

### Risk Scoring Algorithm — 0 to 100 composite

```
  Suricata severity × 10          →  +10 to +30   baseline
  AbuseIPDB confidence ÷ 10       →  +0  to +10
  Destination IP in TI feeds      →  +20
  Persistent attacker (5-min win) →  +5  per event
  External source (not in CMDB)   →  +15
  Target is datacenter infra      →  +20
                                     ──────────────
                                     max  ≈  100
```

### Validated Attack Scenarios

`SQL Injection` `XSS` `Directory Traversal` `PHP Webshell Upload` `HTTP Brute Force` `Port Scan` `Connection Flood`  
All traversing the full 5-VM pipeline → correct severity + risk scores in analyst dashboard.

### Stack

`Suricata 7.0` `Filebeat 8.11` `Redis 7 Streams` `Python 3.11` `PostgreSQL 16` `PostGIS 3.4` `FastAPI` `React 18` `Leaflet.js` `Microsoft Azure` `MITRE ATT&CK` `OWASP Top 10`

---

## // Experience

**SOC Analyst Intern** — OCAC Tower CSOC · Government of Odisha · Bhubaneswar
`Feb 2026 – Mar 2026` · 45-day live government SOC engagement

```
→  Monitored and triaged 50+ live security alerts daily using ArcSight SIEM
→  Investigated confirmed brute force attack (MITRE ATT&CK T1110)
     Log analysis · IOC enrichment via VirusTotal & AbuseIPDB
     ITMS ticketing · escalation under senior analyst guidance
→  Hands-on exposure to real SOC workflows, alert prioritisation,
   and TTP-based escalation in a high-stakes government environment
```

---

**Cybersecurity Intern** — EDUNET Foundation · Remote
`May 2025 – Jun 2025`

```
→  Built a steganography-based data-hiding system
     AES-256 encryption + LSB steganography → covert embed in PNG/JPG
→  Analysed detectability and extraction risks
     Explored covert channel gaps and forensic countermeasures
```

---

**Cybersecurity Intern** — ACMEGRADE · Remote
`Jan 2024 – Mar 2024`

```
→  Nmap-based network reconnaissance and vulnerability assessment
→  Documented findings in structured vulnerability reports
```

---

## // Other Projects

---

### Project 2 — Oil & Gas Network Security Architecture

> Sri Sri University · Team of 5 · Guided by Dr. Tishya Manna & Ms. Ishita Kosambia (Cyber Dojo) · Cisco Packet Tracer

Designed a **resilient, five-zone network architecture** for a simulated oil and gas company connecting headquarters, refineries, and remote exploration sites — prioritising layered OT/IT segmentation and protection of critical industrial control systems from cyber threats.

### Network Zone Architecture

```
  INTERNET
      │
  ┌───▼──────────────────────────────────────────────────────┐
  │  DMZ ZONE                                                │
  │  Web Server · Email · DNS · FTP                          │
  │  WAF → IDPS → Dual Firewalls                             │
  └───┬──────────────────────────────────────────────────────┘
      │  (zone firewall)
  ┌───▼──────────────────────────────────────────────────────┐
  │  ENTERPRISE ZONE                                         │
  │  Finance VLAN · HR VLAN · IT VLAN · Marketing VLAN       │
  │  ACLs + RBAC per department segment                      │
  └───┬──────────────────────────────────────────────────────┘
      │  (highly secure link)
  ┌───▼──────────────────────────────────────────────────────┐
  │  CONTROL ZONE  ← ICS Environment                        │
  │  SCADA Server · HMI Server · Historian DB                │
  │  Industrial Control Server                               │
  └───┬──────────────────────────────────────────────────────┘
      │  (sub-segmented OT links)
  ┌───▼──────────────────────────────────────────────────────┐
  │  FIELD ZONE  ← Remote OT Devices                        │
  │  PLCs · Pressure/Temp/Flow/Gas Sensors · Actuators       │
  │  VSAT links for offshore/remote sites                    │
  └──────────────────────────────────────────────────────────┘

  ┌──────────────────────────────────────────────────────────┐
  │  SECURE OPS ZONE  ← Central SOC                         │
  │  SIEM · SCADA Server · NMS · Jump Server                 │
  │  Data Historian · Backup & Recovery                      │
  └──────────────────────────────────────────────────────────┘
```

### Key Design Decisions

| Decision | What Was Built | Why It Matters |
|---|---|---|
| **Distributed firewalls** | Firewall at every zone boundary | Eliminates single point of failure vs centralised appliances |
| **VLAN + ACL + RBAC** | OT device isolation — PLCs, SCADA segmented by role | Prevents lateral movement from IT compromise into OT |
| **Dual-path failover** | Fiber-optic backbone + OSPF/BGP dynamic routing | Zero-downtime resilience; auto-reroute on link failure |
| **VSAT connectivity** | Satellite links for remote & offshore field sites | Continued comms even when terrestrial links go down |
| **IPSec VPNs** | Encrypted tunnels for all inter-site communication | Secure channel over untrusted WAN/internet segments |
| **Edge computing** | Local processing at remote sites | Continued operation during HQ disconnection |
| **Standards alignment** | IEC 62443 + NIST Cybersecurity Framework throughout | Industry-compliant OT security posture from design stage |

### What Was Validated

```
[✓]  Intra-zone connectivity — all VLANs communicating correctly within zones
[✓]  VLAN segmentation — Finance / HR / IT / Marketing isolated as designed
[✗]  Inter-zone ACL complexity — documented as known challenge for future refinement
       (full cross-zone rule enforcement exceeded Packet Tracer simulation scope)
```

### Stack

`Cisco Packet Tracer` `VLAN / OSPF / BGP` `SCADA / HMI` `IDS / IPS` `IPSec VPN` `VSAT` `IEC 62443` `NIST CSF`

---

### Project 3 — Covert Data Hiding System (AES + Steganography)

> EDUNET Foundation Internship · May–Jun 2025 · Remote

Built a **steganography-based data-hiding system** that combines AES-256 encryption with LSB (Least Significant Bit) steganography to covertly embed secret data inside ordinary PNG/JPG image files — making the payload invisible to the naked eye and undetectable without the key.

### How It Works

```
  SENDER SIDE
  ┌──────────────┐     ┌───────────────────┐     ┌──────────────────────┐
  │  Plaintext   │────▶│  AES-256          │────▶│  LSB Steganography   │
  │  Secret Data │     │  Encryption Layer │     │  Embed into PNG/JPG  │
  └──────────────┘     └───────────────────┘     └──────────┬───────────┘
                                                             │
                                                   ┌─────────▼──────────┐
                                                   │  Carrier Image     │
                                                   │  (looks normal)    │
                                                   └─────────┬──────────┘
  RECEIVER SIDE                                              │
  ┌──────────────┐     ┌───────────────────┐                │
  │  Recovered   │◀────│  AES-256          │◀───────────────┘
  │  Plaintext   │     │  Decryption Layer │  LSB extraction
  └──────────────┘     └───────────────────┘
```

### Key Technical Decisions

| Decision | What Was Built | Why It Matters |
|---|---|---|
| **AES-256 first, then embed** | Encrypt plaintext → embed ciphertext into image pixels | Even if stego is detected, data is still encrypted — two layers of protection |
| **LSB steganography** | Overwrite least significant bits of RGB pixel channels | Pixel value change is ±1 — visually imperceptible to human eye |
| **PNG preferred over JPG** | Lossless PNG retains exact pixel values | JPG compression destroys LSB bits and corrupts hidden data |
| **Capacity analysis** | Calculated max payload per image resolution | Prevents overflow; ensures embedding doesn't introduce visible artifacts |

### Security Analysis Performed

```
[✓]  Detectability testing — visual inspection passes; histogram analysis documented
[✓]  Extraction risk analysis — what an attacker needs to recover data (key + algorithm)
[✓]  Covert channel threat model — how this technique is used in real-world attacks
[✓]  Forensic countermeasures — steganalysis tools that can statistically detect LSB embedding
[✓]  Format constraints — why lossy formats (JPG) break LSB and lossless (PNG) is required
```

### Stack

`Python 3` `AES-256 (PyCryptodome)` `LSB Steganography` `Pillow (PIL)` `Cryptography` `PNG / JPG`

---

### Project 4 — AI-Driven Firewall (Concept)

> Proposed Architecture · Security Engineering

```
  NETWORK TRAFFIC
        │
  ┌─────▼──────────────────────────────────┐
  │  ML Behavioural Anomaly Detection      │
  │  Baseline normal traffic → flag deltas │
  └─────┬──────────────────────────────────┘
        │
  ┌─────▼──────────────────────────────────┐
  │  Real-Time Threat Classification       │
  │  Known signatures + zero-day heuristics│
  └─────┬──────────────────────────────────┘
        │
  ┌─────▼──────────────────────────────────┐
  │  Automated Response Engine             │
  │  Block · Throttle · Alert · Quarantine │
  └─────┬──────────────────────────────────┘
        │
  ┌─────▼──────────────────────────────────┐
  │  CVE Feed Integration                  │
  │  Auto-update firewall rules on new CVEs│
  └────────────────────────────────────────┘
```

Proposed an AI-integrated firewall using ML-based behavioural anomaly detection for real-time traffic analysis, automated threat response, and CVE-based rule auto-updates — moving firewall management from reactive signature matching to proactive behavioural defence.

---

## // Skills

```
SIEM & Detection     →  ArcSight · Splunk (familiar) · Suricata IDS · Filebeat · Redis
Threat Intelligence  →  VirusTotal · AbuseIPDB · AlienVault OTX · IOC Analysis · MITRE ATT&CK
Incident Response    →  Alert Triage · Log Analysis · Escalation Workflows · ITMS Ticketing
Network Security     →  Firewall Design · VLAN · DMZ · Nmap · Cisco Packet Tracer
Cloud & Infra        →  Microsoft Azure · AWS EC2/S3 (learning) · Python 3.11
Security Concepts    →  AES-256 · LSB Steganography · Vulnerability Analysis · OWASP Top 10
Operating Systems    →  Kali Linux · Ubuntu
```

---

## // Credentials

| Certification | Issuer | Date |
|---|---|---|
| CCNA: Introduction to Networks | Cisco | Jun 2024 |
| Introduction to CIP | OPSWAT Academy | Jan 2026 |
| Tata Cybersecurity Analyst Simulation | Forage | Jul 2025 |
| Mastercard Cybersecurity Simulation | Forage | Jan 2025 |
| Foundations of Cybersecurity | Google | Nov 2023 |
| Fundamentals of Red Hat Enterprise Linux | Red Hat | Dec 2023 |

---

## // Education

```
B.Tech — CSE (Cybersecurity & Cyber Defense)
Sri Sri University · Cuttack, Odisha · Expected Jul 2027

Higher Secondary · Class XII — Science
Kendriya Vidyalaya AFS Yelahanka · Bangalore · 2023
```

---

## // Contact

```
❯ ssh ritesh@bangalore

  email     →  riteshpaul262@gmail.com
  linkedin  →  linkedin.com/in/riteshpaul262
  github    →  github.com/RITESH-we
  phone     →  +91 95472 44315
  location  →  Bangalore, India
```

*Open to SOC Analyst internships and entry-level cybersecurity roles.*
