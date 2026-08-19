# TinyTurla Backdoor – Malware Analysis Challenge

<p align="center">

## Quick Access

[![PDF](https://img.shields.io/badge/PDF-TinyTurla_Backdoor_Malware_Analysis-red)](./letsdefend/TinyTurla%20Backdoor%20-%20Analysis/TinyTurla%20Backdoor%20Malware%20Analysis.pdf)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Ashvin_Aacharya-blue)](https://www.linkedin.com/in/ashvin-aacharya-a08553308)

[![X](https://img.shields.io/badge/X-0xAshvin-black)](https://x.com/0xAshvin)

---

# TinyTurla Backdoor – Malware Analysis

Static analysis of a .NET-based TinyTurla backdoor using **dnSpy** to identify its execution flow, command-and-control communication, command execution, file transfer capabilities, and defense evasion techniques.

```

# TinyTurla Backdoor

Static malware analysis of a .NET-based backdoor designed to communicate with a command-and-control (C2) server, execute remote commands, modify execution intervals, transfer files, and hide its execution from the user.

---

## Challenge Information

| Item | Details |
| --- | --- |
| Platform | Let'sDefend |
| Category | Malware Analysis |
| Malware Family | TinyTurla |
| Analysis Type | Static Analysis |
| Tools Used | dnSpy |
| Language | C# (.NET) |

---

## Objectives

- Identify the malware execution flow.
- Analyze command execution capabilities.
- Examine file transfer mechanisms.
- Investigate network communication.
- Identify the C2 infrastructure.
- Understand persistence and evasion techniques.

---

## Tools

- dnSpy
- Windows VM
- Let'sDefend Lab Environment

---

## Key Findings

| Component | Observation |
| --- | --- |
| Command execution | Uses `cmd.exe` |
| Sleep control | Remote modification supported |
| File transfer | Upload and download capabilities |
| Data encoding | Base64 |
| Data compression | Custom compression routines |
| Network communication | HTTP GET and POST |
| C2 server | Hardcoded |
| Evasion | Hides the `MSBuild.exe` window |

---

## Analysis Workflow

```text
Malware Execution
        │
        ▼
Execute()
        │
        ▼
Hide Console Window
        │
        ▼
Hide MSBuild Window
        │
        ▼
Contact C2 Server
        │
        ▼
Receive Commands
        │
        ▼
Decode + Decompress
        │
        ▼
Execute Instructions
```

---

## Screenshots

| Figure | Description |
| --- | --- |
| Figure 1 | Opening the sample in dnSpy |
| Figure 2 | Execute() method |
| Figure 3 | Imported Windows APIs |
| Figure 4 | Hiding the MSBuild window |
| Figure 5 | HTTP communication workflow |
| Figure 6 | runCommand() method |
| Figure 7 | RunShell() implementation |
| Figure 8 | Output redirection |
| Figure 9 | Sleep command processing |
| Figure 10 | File transfer routine |
| Figure 11 | Encoding and compression workflow |
| Figure 12 | Hardcoded C2 configuration |

---

## Techniques Observed

| MITRE ATT&CK Technique | Description |
| --- | --- |
| Command and Scripting Interpreter | Remote shell execution |
| Application Layer Protocol | HTTP-based communication |
| Data Obfuscation | Base64 encoding |
| Data Compression | Compressed network traffic |
| File Transfer | Upload and download |
| Masquerading | MSBuild abuse |
| Defense Evasion | Window hiding |

---

## Lessons Learned

- Follow the execution flow instead of relying on variable names.
- Trace network communication from method calls to the final destination.
- Analyze behavior before drawing conclusions.
- Decode and decompress routines often reveal hidden commands.
- Always follow the chain:

```text
Method
   ↓
Variable
   ↓
Function Call
   ↓
Behavior
```

---

## Author

**Ash**

> Chasing the horizon, ignoring the whispers. Evolveing.

---

⭐ If you found this analysis useful, consider connecting with me on LinkedIn and following me on X.

