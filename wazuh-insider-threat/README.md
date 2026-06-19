# Wazuh Insider Threat Detection Lab

## Overview
This lab demonstrates how to detect insider threats using **Wazuh SIEM** with **File Integrity Monitoring (FIM)**. The scenario is based on a resigning employee attempting to exfiltrate proprietary CAD design files from Bluesify Manufacturing.

## Scenario — Incident 5
A resigning engineer at Bluesify Manufacturing accessed unusually large volumes of proprietary CAD design files during their notice period. This lab demonstrates how Wazuh detects and alerts on this behavior in real-time.

## Lab Environment

| Component | OS | IP Address | Role |
|-----------|-----|------------|------|
| Kali Linux 2026.1 | Kali Linux | [MANAGER_IP] | Wazuh Manager + Dashboard |
| Windows 10 | Windows 10 Pro | [AGENT_IP] | Wazuh Agent + Sysmon |

**Network:** NAT Network (ClientServerNet) — Oracle VirtualBox

## Tools Used
- **Wazuh v4.11.0** — SIEM, FIM, UBA
- **Sysmon** — Enhanced Windows event logging
- **Oracle VirtualBox** — Virtualization

## What Was Configured

### File Integrity Monitoring (FIM)
Added to `ossec.conf` on Windows 10:
```xml
<directories realtime="yes" report_changes="yes" check_all="yes">
  C:\Users\Rayan\Desktop\CAD_Designs
</directories>
```

### Custom Detection Rule
Added to `/var/ossec/etc/rules/local_rules.xml` on Kali:
```xml
<rule id="100002" level="12">
  <if_sid>554</if_sid>
  <description>Bluesify Insider Threat: CAD file added - possible data exfiltration by resigned employee</description>
  <group>insider_threat,data_exfiltration,</group>
</rule>
```

## Results

### BEFORE
- No FIM events detected
- Insider could freely copy/delete files without any alerts

### AFTER
- **File added** — Rule 554 (Level 5) triggered when files copied to TO_SEND folder
- **File deleted** — Rule 553 (Level 7) triggered when files removed
- Full forensic metadata recorded: path, timestamp, MD5/SHA1, user

## MITRE ATT&CK Mapping
| Technique | ID | Description |
|-----------|-----|-------------|
| Data from Local System | T1005 | Employee accessed CAD files locally |
| Data Staged | T1074 | Files moved to TO_SEND staging folder |

## Key Findings
- Wazuh FIM detected unauthorized file operations within seconds
- User attribution confirmed: `c:\users\rayan\desktop\cad_designs\`
- 3 FIM events recorded: 2x File added, 1x File deleted
- Real-time alerting enabled SOC team to respond immediately

## Author
**Rian Khaled Ahmed Bin Salman** | TP085645  
BSc Cybersecurity — Asia Pacific University (APU)  
Module: CT128-3-2 Implementation of Secure System (ISC)
