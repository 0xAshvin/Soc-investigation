# SOC308 – Suspicious Rundll32 Execution Detected

## Investigation Report

A practical SOC investigation into a suspicious `rundll32.exe` execution that revealed a phishing-driven malware infection chain.

The investigation correlated email activity, endpoint telemetry, process creation, file creation, payload delivery, IOC reputation, defense evasion, and persistence to reconstruct the complete attack flow.

### Attack Chain

Phishing Email → User Execution → BITSAdmin → Payload Download → Rundll32 → Malware Execution → Defender Evasion → Scheduled Task Persistence

### Key Techniques

- T1566.001 – Spearphishing Attachment
- T1204.002 – User Execution: Malicious File
- T1197 – BITS Jobs
- T1218.011 – System Binary Proxy Execution: Rundll32
- T1562.001 – Impair Defenses
- T1053.005 – Scheduled Task/Job

## 📄 Investigation Report

[![View Investigation Report](https://img.shields.io/badge/📄%20View%20Investigation%20Report-4285F4?style=for-the-badge)](./SOC308-Suspicious-Rundll32-Execution.pdf)

> **Verdict:** True Positive  
> **Focus:** Phishing, LOLBin Abuse, Payload Delivery, Defense Evasion & Persistence

## Key Findings

- Malicious phishing email impersonating a CrowdStrike patch notification
- User execution of a malicious `.cmd` file
- BITSAdmin used to retrieve a second-stage payload
- `rundll32.exe` abused to execute `PO789.exe`
- PowerShell used to add a Windows Defender exclusion
- Scheduled Task created for persistence
- Malicious URLs and file hashes identified as IOCs

---

**Author:** Ash  
**Focus:** SOC Analysis | Threat Detection | DFIR
