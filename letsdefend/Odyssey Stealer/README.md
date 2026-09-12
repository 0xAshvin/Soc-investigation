# 🦠 Odyssey Stealer — macOS Malware Analysis

> Static analysis of an obfuscated AppleScript-based macOS information stealer.

## 🔍 Overview

This investigation focused on a heavily obfuscated AppleScript payload and its second-stage functionality.

Rather than executing the sample, I analyzed the script statically and traced its functions, variables, encoded payloads, persistence logic, credential harvesting, Telegram data collection, C2 communication, and exfiltration workflow.

## 🧪 Analysis Highlights

- 🔎 Identified heavily obfuscated AppleScript handlers
- 🌐 Traced hardcoded C2 infrastructure
- 🪪 Extracted the `buildid`
- 🎭 Analyzed the fake macOS password prompt
- 🔐 Identified local password verification using `dscl`
- ⚙️ Analyzed LaunchDaemon persistence
- 🧩 Decoded the embedded Base64 second stage using CyberChef
- 📱 Identified Telegram `tdata` collection
- 🤖 Discovered the second-stage bot C2 endpoint
- 📦 Identified ZIP-based data staging and exfiltration

## 🎯 Key Findings

| Category | Finding |
|---|---|
| C2 | `http://something0x.at` |
| Build ID | `c71d76b983a140529cca8a9bc87dfdcd` |
| Fake Prompt | `Application wants to install Riverside` |
| Password Validation | `dscl . authonly` |
| Persistence | `/Library/LaunchDaemons/` |
| Telegram Target | `key_datas` |
| Bot Endpoint | `/api/v1/bot/actions/` |
| Archive | `/tmp/out.zip` |

## 🧠 Takeaway

The interesting part wasn't simply decoding the script.

The real challenge was turning a wall of randomized AppleScript into a behavioral map:

`Obfuscation → Functions → Variables → Second Stage → C2 → Collection → Exfiltration`

A good reminder that even ugly scripts leave useful breadcrumbs. 🕵️

## 📄 Full Analysis

[![Read Full Report](https://img.shields.io/badge/📄%20Read%20Full%20Analysis-PDF-blue?style=for-the-badge)](./Odyssey_Stealer_Malware_Analysis.pdf)

---

### 🛠️ Tools

`Linux CLI` · `Python` · `CyberChef` · `Static Analysis`

### ⚠️ Disclaimer

This analysis was performed for educational and defensive cybersecurity research purposes in an isolated lab environment.
