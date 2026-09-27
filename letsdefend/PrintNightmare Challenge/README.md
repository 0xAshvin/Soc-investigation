# PrintNightmare — LetsDefend Investigation

> A concise SOC investigation of a Windows compromise through **PrintNightmare (CVE-2021-34527)**, combining network and endpoint evidence to reconstruct the attack chain.

## Investigation

This project analyzes the PrintNightmare attack using:

- **Zui / Zeek** — network traffic and protocol analysis
- **Redline** — Windows endpoint and event analysis
- **Wireshark** — supporting packet analysis
- **VirusTotal** — malware and hash verification

The investigation covers attacker identification, SMB payload delivery, malicious DLL activity, certificate analysis, NTLM authentication, persistence, process execution, Meterpreter activity, and post-exploitation artifacts.

## Key Findings

- **Attacker:** `10.10.10.2`
- **Vulnerability:** `CVE-2021-34527`
- **Malicious DLL:** `notsostealthy.dll`
- **Domain User:** `BELLYBEAR\Jesse.Harmon`
- **Persistence Account:** `hacker`
- **Exploit Server:** `WIN-FLO4EU2VMSM`
- **Shell Process:** `rundll32.exe`
- **Attacker Port:** `443`
- **Payload:** `Meterpreter / reverse_https`
- **Windows Event:** `4720`
- **Final Artifact:** `This-Is-Really-A-Nightmare.txt`

## Evidence

The investigation correlates network and endpoint telemetry to document:

1. PrintNightmare exploitation
2. SMB-based payload delivery
3. Malicious DLL execution
4. Attacker authentication
5. Persistence through account creation
6. Reverse HTTPS communication
7. Post-exploitation activity
8. Final filesystem artifact

## Report

📄 **[View / Download the Full PDF Report](./PrintNightmare_Analysis.pdf)**

The PDF contains the detailed findings, evidence references, IOC list, attack-chain analysis, final answers, and investigation conclusion.

## Skills Demonstrated

`SOC Investigation` · `PCAP Analysis` · `Zeek` · `Zui` · `Redline` · `Windows Events` · `IOC Analysis` · `MITRE ATT&CK` · `Incident Response`

## Acknowledgement

Investigation lab provided by **LetsDefend**.
