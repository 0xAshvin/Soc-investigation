# Compromised AI Cluster - Network Forensics Write-up

Investigation of a compromised **Ray AI Cluster** from the Let'sDefend network forensics lab.

The objective of this investigation was to identify the attacker's activity, reconstruct the attack timeline, analyze command execution, investigate data exfiltration, and assess the impact on the AI cluster.



## Key Findings

| Category | Finding |
| --- | --- |
| AI Framework | Ray 2.8.0 |
| Exposed Service | 3.72.0.226:8265 |
| Vulnerability | CVE-2023-48022 |
| Initial Attacker | 104.28.245.2 |
| Reverse Shell | 52.150.25.174:1337 |
| Exfiltration Server | 104.28.213.2 |
| Network Scan | TCP SYN Scan |

---

## Attack Timeline

```text
Ray API Exposure
        ↓
CVE-2023-48022 Exploitation
        ↓
Remote Command Execution
        ↓
Reverse Shell Establishment
        ↓
Reconnaissance
        ↓
Secret File Collection
        ↓
Data Exfiltration
        ↓
TCP SYN Port Scan
```

---

## Tools Used

- Wireshark
- HTTP Stream Analysis
- TCP Stream Analysis
- Endpoint Statistics
- Let'sDefend Network Forensics Lab

---

## Author

**Ashvin Aacharya**

Cybersecurity learner focused on SOC analysis, malware analysis, threat detection, and blue team operations.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/ashvin-aacharya-a08553308)
[![GitHub](https://img.shields.io/badge/GitHub-0xAshvin-black)](https://github.com/0xAshvin)
[![X](https://img.shields.io/badge/X-@0xAshvin-black)](https://x.com/0xAshvin)
