# SOC312 – Unauthorized Template Modification Detected

## Brief

A SOC investigation of an unauthorized Microsoft Word template modification involving `Normal.dotm`.

The investigation traces the activity from **RDP brute-force attempts and valid account compromise** through **host discovery, malicious VBA execution, C2 communication, and remote command execution**.

The case study documents the investigation timeline, supporting evidence, MITRE ATT&CK mapping, IOCs, attack chain, and containment recommendations.

## Investigation Flow

**Brute Force → Valid Account → Discovery → Normal.dotm Modification → VBA → C2 → Command Execution**

## Report

<a href="./SOC312_Unauthorized_Template_Modification_Investigation.pdf">
  <img src="https://img.shields.io/badge/READ%20FULL%20REPORT-000000?style=for-the-badge&logo=adobeacrobatreader&logoColor=white" alt="Read Full Report">
</a>

## Key Areas

- Windows Event & Sysmon Analysis
- RDP Brute-Force Investigation
- Valid Account Compromise
- Host & Network Discovery
- Microsoft Word `Normal.dotm` Analysis
- VBA Macro Analysis
- C2 Communication Analysis
- MITRE ATT&CK Mapping
- IOC Identification
- Incident Containment

## Conclusion

The investigation confirmed unauthorized access followed by modification of the Word `Normal.dotm` template containing malicious VBA capable of communicating with a C2 server and executing attacker-controlled commands.

**Classification: True Positive**
