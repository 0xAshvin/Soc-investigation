# StageComp - Malware Analysis Write-up

Reverse engineering and behavioral analysis of the **StageComp** malware sample from the Let'sDefend malware analysis lab.

The objective of this investigation was to:

- Identify the command-and-control (C2) infrastructure.
- Extract actionable IOCs.
- Reconstruct the malware execution chain.
- Understand payload delivery, execution, and cleanup mechanisms.

---

## Quick Access

[![PDF](https://img.shields.io/badge/Read-PDF-blue)](./STAGECOMP.pdf)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Ashvin_Aacharya-blue)](https://www.linkedin.com/in/ashvin-aacharya-a08553308)
[![X](https://img.shields.io/badge/X-@0xAshvin-black)](https://x.com/0xAshvin)

---

## Key Findings

| Category | Finding |
| --- | --- |
| C2 Server | `moonzonet.com` |
| Communication | HTTPS |
| User-Agent | `StageClient/2.0` |
| Registration | JSON-based client registration |
| Payload | `Game.exe` |
| Working Directory | `GameFiles` |
| Execution | `CreateProcessA()` |
| Timeout | `5000 ms` |
| Cleanup | Self-deletion using `cmd.exe` |

---

## Execution Chain

```text
WinHttpOpen
        ↓
WinHttpConnect
        ↓
POST /register
        ↓
POST /check
        ↓
Download Game.exe
        ↓
Create GameFiles directory
        ↓
Launch payload
        ↓
Wait for execution
        ↓
Self-delete
```

---

## Screenshots Included

- Main execution flow
- C2 communication
- Registration request
- HTTP request creation
- HTTP headers
- Payload staging
- Payload download
- Process creation
- Process timeout
- Self-deletion mechanism

---

## Tools Used

- Ghidra
- Detect It Easy (DIE)
- Let'sDefend Malware Analysis Lab

---

## Author

**Ashvin Aacharya**

Cybersecurity learner focused on:

- SOC Analysis
- Malware Analysis
- Threat Detection
- Blue Team Operations

If you're learning SOC or malware analysis too, let's learn, share, and grow together.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/ashvin-aacharya-a08553308)

[![GitHub](https://img.shields.io/badge/GitHub-0xAshvin-black)](https://github.com/0xAshvin)

[![X](https://img.shields.io/badge/X-@0xAshvin-black)](https://x.com/0xAshvin)
