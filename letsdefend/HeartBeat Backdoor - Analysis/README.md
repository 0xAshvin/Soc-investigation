# HeartBeat Backdoor — Malware Analysis (README.md)

```markdown
# HeartBeat Backdoor - Malware Analysis

> Malware Analysis Challenge from Let'sDefend

[![PDF](https://img.shields.io/badge/PDF-View_Report-red)](./HeartBeat_Backdoor.pdf)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/ashvin-aacharya-a08553308)
[![X](https://img.shields.io/badge/X-Follow-black)](https://x.com/0xAshvin)

---

## Overview

This repository contains my analysis of the **HeartBeat Backdoor** malware challenge from **Let'sDefend**.

The objective of this investigation was to identify the malware's communication method, file-transfer mechanism, command-handling logic, registry modifications, and system-control capabilities through static analysis.

---

## Challenge Information

- **Platform:** Let'sDefend
- **Challenge:** HeartBeat Backdoor
- **Author:** Mateo Pappa
- **Analysis Type:** Static Analysis
- **Tool Used:** Ghidra

---

## Key Findings

| Artifact | Result |
| --- | --- |
| C2 Port | 80 |
| Protocol | SOCK_STREAM |
| Process Termination Case | 2 |
| XOR Key | 2 |
| Registry Key Deleted | HKLM\\SYSTEM\\CurrentControlSet\\Services\\6to4 |
| XOR Function | 0x10001000 |
| First Moved File | hyper.dll |
| Restart Function | 0x10001A90 |

---

## Malware Capabilities

- C2 communication over TCP.
- XOR-based file transfer.
- Remote command execution.
- Process termination.
- Registry modification.
- File removal.
- Immediate system restart.

---

## Analysis Highlights

- Port identification through `_wtoi()` and `htons()`.
- Socket analysis through `socket(2,1,6)`.
- Command analysis using the malware's switch statement.
- XOR buffer analysis before network transmission.
- Registry investigation through `reg delete`.
- File operation analysis through `MoveFileExA()`.
- Restart behavior identified through `shutdown -r -t 0`.

---

## Screenshots Included in the Report

- Port identification.
- Protocol identification.
- Process termination.
- XOR encryption.
- Registry deletion.
- Network transmission.
- File movement.
- System restart.

---

## Motivation

> Don't just learn how attacks work. Learn how to recognize them before they become incidents.

---

## Credits

- Challenge: HeartBeat Backdoor
- Platform: Let'sDefend
- Author: Mateo Pappa

Special thanks to **Let'sDefend** for providing the challenge environment and hands-on malware analysis experience.

---
```



