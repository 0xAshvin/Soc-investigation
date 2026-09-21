🔐 Adobe ColdFusion RCE — SOC Investigation

A concise SOC investigation of a compromised Adobe ColdFusion server, covering web-shell deployment, PowerShell execution, reconnaissance, external communication, and reverse-shell activity.

🧩 Key Findings
🔎 nltest.exe /domain_trusts — Domain reconnaissance
🧪 Encoded PowerShell decoded using CyberChef
💻 Malicious ColdFusion .cfm web shell identified
⚙️ cfexecute used for OS command execution
🛠️ certutil.exe used to decode the payload
🌐 webhook.site identified as an external service
🔍 net user /domain — Domain user enumeration
🐚 PowerShell TCP reverse shell identified
🎯 C2 destination: 185.100.233.201:80
🧷 Likely vulnerability: CVE-2023-26360
🔗 Attack Chain
🌐 Adobe ColdFusion
        ↓
💥 RCE
        ↓
📦 Encoded Payload
        ↓
🛠️ certutil.exe
        ↓
📄 ColdFusion Web Shell
        ↓
⚙️ cfexecute
        ↓
💻 cmd.exe / PowerShell
        ↓
🔍 Reconnaissance
        ↓
🌐 External Communication
        ↓
🐚 Reverse Shell
🛠️ Tools

Windows Event Logs · Sysmon · CyberChef · MITRE ATT&CK

📂 Key IOCs
C:\Fusion21\cfusion\wwwroot\cf_scripts\cfclient\huqVgdoFd.cfm

webhook.site
46.4.105.116

185.100.233.201:80

certutil.exe
powershell.exe
net.exe
nltest.exe
📄 Full Investigation Report
<a href="./Adobe-ColdFusion-RCE-SOC-Investigation.pdf"> <img src="https://img.shields.io/badge/📄%20VIEW%20FULL%20REPORT-PDF-blue?style=for-the-badge" alt="View Full PDF Report"> </a>

🛡️ Focus: SOC Investigation · Threat Hunting · Incident Analysis
🧪 Lab: LetsDefend — Adobe ColdFusion RCE
