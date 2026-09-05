# Shadow of LiteLLM — Malware Analysis

<p align="center">
  <img src="https://img.shields.io/badge/Focus-Malware%20Analysis-red?style=for-the-badge">
  <img src="https://img.shields.io/badge/Analysis-Static-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/Platform-Let's%20Defend-black?style=for-the-badge">
</p>

## 📄 Full Write-up

<p align="center">
  <a href="./Shadow-of-LiteLLM-Malware-Analysis.pdf">
    <img src="https://img.shields.io/badge/READ%20FULL%20WRITE--UP-Click%20Here-blue?style=for-the-badge&logo=adobeacrobatreader">
  </a>
</p>

## 🔍 Overview

Static analysis of the **Shadow of LiteLLM** challenge involving a trojanized LiteLLM package and a multi-stage Python payload.

The investigation focused on decoding the embedded payloads using **CyberChef** and analyzing the malware's execution flow without executing the malicious code.

## ⚔️ Attack Chain

```text
Trojanized LiteLLM Package
          ↓
Python Payload Execution
          ↓
Reconnaissance & Credential Discovery
          ↓
AWS IMDSv2 / Cloud Enumeration
          ↓
AES-256-CBC Encryption & Exfiltration
          ↓
Kubernetes Privileged Pod Abuse
          ↓
Systemd Persistence
          ↓
RAT Loader & C2 Communication
          ↓
Next-Stage Payload


🧪 Key Findings
Trojanized LiteLLM versions: 1.82.7 and 1.82.8
Base64-encoded multi-stage Python payload
Credential and sensitive-file discovery
AWS IMDSv2 IAM credential access
AES-256-CBC data encryption
Data exfiltration to models.litellm.cloud
Kubernetes privileged Pod abuse
Target namespace: kube-system
Malicious Pod prefix: node-setup-
Systemd persistence
Persistent loader: ~/.config/sysmon/sysmon.py
C2 infrastructure: checkmarx.zone
Downloaded payload: /tmp/pglog
State file: /tmp/.pg_state
🛠️ Tools Used
Detect It Easy (DIE)
CyberChef
Python
Static Analysis
MITRE ATT&CK
📌 Analysis Methodology

The challenge file was first examined using Detect It Easy and identified as plain text.

The embedded Base64 content was then decoded in multiple stages using CyberChef:

Initial Python loader
B64_SCRIPT — reconnaissance and credential discovery
PERSIST_B64 — persistent RAT loader

The malware was analyzed statically and was not executed during the investigation.

🎯 Skills Demonstrated

Malware Analysis
Static Analysis
Python
Base64 Decoding
AWS IMDSv2
Cloud Security
Kubernetes Security
Credential Discovery
Persistence
C2 Analysis
MITRE ATT&CK

⚠️ Disclaimer

This repository is intended for educational and defensive cybersecurity research.

The malicious payload was analyzed statically and was not executed.


### Your GitHub repository must have this exact structure

```text
Shadow-of-LiteLLM/
│
├── README.md
│
├── Shadow-of-LiteLLM-Malware-Analysis.pdf
│
└── screenshots/
    ├── figure-1-die.png
    ├── figure-2-cyberchef-stage1.png
    ├── figure-3-b64-script.png
    └── figure-4-persist-b64.png
