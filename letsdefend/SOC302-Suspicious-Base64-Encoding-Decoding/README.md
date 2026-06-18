# Suspicious Base64 Encoding/Decoding Commands Detected (SOC302)

## Overview

This investigation analyzes a suspicious Base64 decoding alert that initially appeared to be a simple encoding/decoding event but later revealed a complete attack chain involving SSH brute force, credential harvesting, and sensitive data access.

## Key Findings

- SSH brute-force attack from external IP
- Successful compromise of analyst account
- System reconnaissance activities
- Sensitive file discovery
- Base64 decoding of credential data
- Credential harvesting attempt

## Skills Practiced

- Log Analysis
- Incident Investigation
- Threat Hunting
- MITRE ATT&CK Mapping
- Timeline Analysis
- IOC Analysis

## Report

📄 Full Investigation Report:

[SOC302-Suspicious-Base64.pdf](SOC302-Suspicious-Base64.pdf)
