# Ritesh Paul — Cybersecurity Analyst

> *SOC Operations · Incident Response · Threat Intelligence · SIEM*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-riteshpaul262-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/riteshpaul262)
[![Email](https://img.shields.io/badge/Email-riteshpaul262%40gmail.com-EA4335?style=flat-square&logo=gmail)](mailto:riteshpaul262@gmail.com)
[![Location](https://img.shields.io/badge/Location-Bangalore%2C%20India-34A853?style=flat-square&logo=googlemaps)]()

---

## About Me

I'm a B.Tech Cybersecurity student (graduating 2027) with hands-on SOC internship experience in a government Security Operations Center, where I triaged 50+ live alerts daily using ArcSight SIEM. My work sits at the intersection of **threat detection**, **incident response**, and **security engineering** — I don't just learn tools, I build systems with them.

My major project is a production-grade, distributed SOC pipeline deployed across 5 Azure VMs — not a lab toy, but a full detection-to-dashboard architecture replicating what enterprise SOC teams use in industry.

---

## 🏗️ Major Project — Location-Based Threat Intelligence Alert System

> *A distributed, multi-VM SOC pipeline that replicates a production Security Operations Center — detection, enrichment, correlation, storage, and analyst dashboard.*

### What It Does
A team of 5 built a distributed SOC pipeline that detects real attacks on a vulnerable web app (OWASP Juice Shop), enriches every alert with threat intelligence from 3 sources, geo-locates attack origins, scores risk, stores results spatially, and serves everything through an interactive analyst dashboard — **end-to-end in 3–5 seconds**.

### My Contribution — VM-1 (Sensor Layer)
I owned the front-line detection layer of the pipeline:

- **Deployed and configured Suricata IDS** with AF-PACKET capture and EVE JSON logging on VM-1
- **Wrote all 15 custom detection rules** covering OWASP Top 10 categories — SQLi, XSS, directory traversal, brute force, and port scan — using both signature-based and threshold-based detection logic
- **Configured Filebeat** for resilient log shipping to VM-2 Redis with cursor persistence (zero event loss on restart) and sensor metadata enrichment (`sensor_id`, `sensor_location`)
- **Set up OWASP Juice Shop** as the attack target and validated all 15 rules fired correctly against 13 attack scenarios

### Architecture (5 Azure VMs)

```
[VM-7: Attacker] ──► [VM-1: Suricata IDS + Filebeat] ──► [VM-2: Redis + TI Fetcher]
                                                                      │
                                                          [VM-3: Normaliser → Enricher → Correlator]
                                                                      │
                                                             [VM-4: PostgreSQL + PostGIS]
                                                                      │
                                                         [VM-5: FastAPI + React Dashboard]
```

### Key Technical Decisions

| Decision | What I Built | Why It Matters |
|---|---|---|
| **Event-driven microservices** | 5 Python services communicating via Redis Streams with Consumer Groups | At-least-once delivery; services fail independently without data loss |
| **3-source TI correlation** | Cache-first batch from VirusTotal, AbuseIPDB, AlienVault OTX | Stays within free API rate limits; O(1) enrichment at pipeline speed |
| **Geospatial storage** | PostGIS `GEOGRAPHY(Point, 4326)` with GIST index | Real spherical-earth distance queries; enables spatial analytics commercial SIEMs charge for |
| **Custom IDS ruleset** | 15 Suricata rules covering OWASP Top 10 (signature + threshold-based) | Brute force and port scan detection require threshold rules; signature alone isn't enough |
| **Alert lifecycle management** | Acknowledge / Resolve with full audit_log (PCI-DSS, ISO 27001 compliant design) | Compliance traceability; mirrors real SOC analyst workflows |

### Risk Scoring Algorithm

Each alert gets a composite 0–100 risk score from 6 weighted factors:

- Suricata rule severity × 10 (baseline)
- AbuseIPDB confidence score ÷ 10
- +20 if destination IP appears in TI feeds
- +5 per event from same source IP in 5-min window (persistent attacker penalty)
- +15 if source is external (not in CMDB)
- +20 if target is classified as datacenter infrastructure

### Validated Against 13 Attack Scenarios

SQL Injection · XSS · Directory Traversal · PHP Webshell Upload · HTTP Brute Force · Port Scan · Connection Flood — all traversing the full 5-VM pipeline and appearing in the analyst dashboard with correct severity and risk scores.

### Stack
`Suricata 7.0` · `Filebeat 8.11` · `Redis 7 (Streams + Consumer Groups)` · `Python 3.11` · `PostgreSQL 16` · `PostGIS 3.4` · `FastAPI` · `React 18` · `Leaflet.js` · `Nginx` · `Microsoft Azure`

---

## 💼 Experience

### SOC Analyst Intern — OCAC Tower CSOC (Government) · Feb–Mar 2026
*45-day engagement in a live government Security Operations Center, Bhubaneswar*

- Monitored and triaged **50+ live security alerts daily** using ArcSight SIEM
- Investigated a confirmed **brute force attack (MITRE ATT&CK T1110)** — performed log analysis, enriched IOCs via VirusTotal & AbuseIPDB, managed ITMS tickets, escalated under senior analyst guidance
- Gained exposure to real SOC workflows, alert prioritisation, and TTP-based escalation in a high-stakes government environment

### Cybersecurity Intern — EDUNET Foundation · May–Jun 2025 · Remote

- Built a **steganography-based data-hiding system** combining AES-256 encryption with LSB steganography to covertly embed data inside PNG/JPG images
- Analysed the system for detectability and extraction risks

### Cybersecurity Intern — ACMEGRADE · Jan–Mar 2024 · Remote

- Performed **Nmap-based network reconnaissance** and vulnerability assessment in a simulated lab
- Documented findings in structured vulnerability reports

---

## 🛠️ Other Projects

### Oil & Gas Network Security Architecture
*Sri Sri University · Team of 5 · Guided by Dr. Tishya Manna & Ms. Ishita Kosambia (Cyber Dojo)*

Designed a **resilient, five-zone network architecture** for a simulated oil and gas company connecting headquarters, refineries, and remote exploration sites. The architecture prioritises layered OT/IT segmentation and protection of critical industrial control systems from cyber threats.

**Five Security Zones Designed:**

| Zone | Purpose |
|---|---|
| DMZ | Public-facing services (Web, Email, DNS, FTP) with WAF, IDPS, and dual firewalls |
| Enterprise Zone | Corporate IT (Finance, HR, IT, Marketing) segmented by VLAN; protected by zone firewall |
| Field Zone | Remote OT devices — PLCs, sensors (pressure/temp/flow/gas), actuators — in sub-segmented architecture |
| Control Zone | ICS environment — SCADA, HMI Server, Historian DB, Industrial Control Server — via Highly Secure Link |
| Secure Ops | Central SOC with SIEM, SCADA Server, NMS, Jump Server, Data Historian, Backup & Recovery |

**Key Design Decisions:**
- Distributed firewall at every zone boundary — eliminates single point of failure vs centralised appliances
- VLAN segmentation with ACLs and RBAC for OT device isolation (PLCs, SCADA)
- Fiber-optic backbone with dual-path failover and OSPF/BGP dynamic routing for zero-downtime resilience
- VSAT satellite links for remote and offshore field site connectivity
- IPSec VPNs and IDS/IPS for secure inter-site communication
- Edge computing at remote sites for continued operation during HQ disconnection
- IEC 62443 and NIST Cybersecurity Framework alignment throughout

**Implemented & Tested in Cisco Packet Tracer** — intra-zone connectivity and VLAN segmentation validated; inter-zone ACL complexity documented as a known challenge for future refinement.

**Stack:** `Cisco Packet Tracer` · `VLAN / OSPF / BGP` · `SCADA / HMI` · `IDS/IPS` · `IPSec VPN` · `VSAT` · `IEC 62443`

### AI-Driven Firewall (Concept)
Proposed an AI-integrated firewall using ML-based behavioural anomaly detection for real-time traffic analysis, automated threat response, and CVE-based rule updates.

---

## 🧰 Skills

**SIEM & Detection** — ArcSight, Splunk (familiar), Suricata IDS, Filebeat, Redis  
**Threat Intelligence** — VirusTotal, AbuseIPDB, AlienVault OTX, IOC analysis, MITRE ATT&CK, TTP mapping  
**Incident Response** — Alert triage, log analysis, escalation workflows, ITMS ticketing  
**Network Security** — Firewall design, VLAN, DMZ, Nmap, Cisco Packet Tracer  
**Cloud & Infra** — Microsoft Azure (VM provisioning), AWS EC2/S3 (learning), Python  
**Security Concepts** — AES encryption, LSB steganography, vulnerability analysis, OWASP  
**Operating Systems** — Kali Linux, Ubuntu  

---

## 📜 Certifications

| Certification | Issuer | Date |
|---|---|---|
| CCNA: Introduction to Networks | Cisco | Jun 2024 |
| Introduction to CIP | OPSWAT Academy | Jan 2026 |
| Tata Cybersecurity Analyst Simulation | Forage | Jul 2025 |
| Mastercard Cybersecurity Simulation | Forage | Jan 2025 |
| Foundations of Cybersecurity | Google | Nov 2023 |
| Fundamentals of Red Hat Enterprise Linux | Red Hat | Dec 2023 |

---

## 🎓 Education

**B.Tech — CSE (Cybersecurity & Cyber Defense)** · Expected Jul 2027  
Sri Sri University, Cuttack, Odisha

**Higher Secondary (Class XII — Science)** · 2023  
Kendriya Vidyalaya AFS Yelahanka, Bangalore

---

*Open to SOC Analyst internships and entry-level cybersecurity roles. Let's connect.*
