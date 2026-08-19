
# OctoRAT - Malware Analysis (Let'sDefend)

A reverse-engineering walkthrough of the OctoRAT malware challenge from Let'sDefend.

This analysis focuses on the malware's persistence mechanisms, privilege escalation, C2 communication, information-stealing capabilities, remote desktop functionality, cryptocurrency wallet theft, clipboard monitoring, and other malicious features.

The report was created by tracing code execution in dnSpy and validating every answer through direct code analysis.

---

## PDF Report

[![PDF](https://img.shields.io/badge/PDF-View_OctoRAT_Malware_Analysis_Report-red)](./OctoRAT_Malware_Analysis.pdf)

---

## Quick Access

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Ashvin_Aacharya-blue)](https://www.linkedin.com/in/ashvin-aacharya-a08553308)

[![X](https://img.shields.io/badge/X-0xAshvin-black)](https://x.com/0xAshvin)

[![GitHub](https://img.shields.io/badge/GitHub-0xAshvin-lightgrey)](YOUR_GITHUB_LINK)

---

## About Me

I'm Ashvin, a cybersecurity student focused on SOC operations, malware analysis, incident investigation, and threat detection.

I use platforms such as Let'sDefend to strengthen practical skills through hands-on analysis and real-world scenarios.

---

## Key Topics Covered

- Mutex analysis
- UAC bypass
- Scheduled task persistence
- Configuration extraction
- Self-deletion
- Firewall manipulation
- C2 communication
- Connection health monitoring
- Victim identification
- Remote desktop streaming
- Keylogging
- Cryptocurrency wallet theft
- Browser data extraction
- Clipboard monitoring

---

## Analysis Methodology

The analysis was performed through static reverse engineering.

Tools used:

- dnSpy
- Detect It Easy (DIE)
- PEStudio
- Strings analysis
- Manual code tracing

Instead of searching only for answers, the analysis followed function calls, tracked variable assignments, and identified how different malware components interacted.

---

## Report Highlights

✔ Every screenshot directly corresponds to a Let'sDefend question.

✔ Every answer was validated through source-code analysis.

✔ The report emphasizes understanding malware behavior rather than memorizing outputs.

---

## Motivation

> In cybersecurity, finding an answer is useful.
>
> Understanding why that answer exists is what builds an analyst.

---

*Educational purposes only.*
