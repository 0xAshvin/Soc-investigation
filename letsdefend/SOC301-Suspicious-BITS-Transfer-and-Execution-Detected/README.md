# SOC301 – Suspicious BITS Transfer and Execution Detected

This repository contains my investigation of the Let's Defend SOC301 alert.

## Summary

The investigation revealed a phishing-driven attack chain involving BITS abuse, payload delivery, and InstallUtil execution.

### Attack Chain

📧 Phishing Email

↓

📦 project2024.zip

↓

📜 project2024.cmd

↓

⚙️ bitsadmin.exe

↓

📦 transfer.zip

↓

🦠 TRANSFER.exe

↓

🔧 InstallUtil.exe

### Key Findings

- Phishing attachment used for initial access
- BITS abused for payload delivery
- Secondary payload successfully executed
- InstallUtil.exe used as a LOLBin
- No evidence of data exfiltration observed

## Full Write-Up

The complete investigation is available in:

**SOC301-Suspicious-BITS-Transfer-and-Execution-Detected.pdf**

## Platform

Let's Defend

## MITRE ATT&CK

- T1566.001 – Spearphishing Attachment
- T1059.003 – Windows Command Shell
- T1197 – BITS Jobs
- T1105 – Ingress Tool Transfer
- T1218.004 – InstallUtil
