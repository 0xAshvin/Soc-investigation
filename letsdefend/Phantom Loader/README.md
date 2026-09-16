# Phantom Loader — Malware Analysis

> **Platform:** LetsDefend  
> **Analysis Tool:** Ghidra  
> **File Type:** 64-bit Windows PE  
> **Focus:** Static Malware Analysis, Reverse Engineering, Anti-Analysis, C2 Analysis

## 📄 Full Write-Up

**[➡️ Open Phantom Loader Malware Analysis Write-Up (PDF)](./Phantom_Loader_Writeup.pdf)**

---

## Overview

This write-up documents the static analysis of **Phantom Loader**, a 64-bit Windows PE malware sample.

The analysis covers:

- PE structure and embedded payload analysis
- Dynamic API resolution
- C2 communication
- HTTP request analysis
- PE relocation handling
- Debugger and sandbox detection
- Process and security-tool enumeration
- USB history checks
- Command-line argument checks
- Encrypted C2 hostname analysis
- Client fingerprint generation

The main objective was to trace the relevant functions in **Ghidra**, decode embedded strings and constants, and identify the values used by the malware.

---

## Scenario

Phantom Loader uses several techniques to make analysis harder and to collect information about the victim environment.

The challenge requires identifying specific values from the malware's decompiled code.

The general workflow used was:

1. Load the PE sample into Ghidra.
2. Locate the function or API mentioned in each question.
3. Follow references to constants and global variables.
4. Decode hexadecimal values when they represent strings.
5. Trace the relevant condition or API call.
6. Record the exact value used by the malware.

---

## Challenge Answers

| # | Question | Answer |
|---|---|---|
| 01 | DOS header magic decimal value | `23117` |
| 02 | URL path used by WinHTTP requests | `/api/debut` |
| 03 | Relocation entry type processed | `3` |
| 04 | HTTP verb used for C2 data | `POST` |
| 05 | PEB byte checked for debugger detection | `0x70` |
| 06 | ProcessInformationClass for debug object query | `0x1E` |
| 07 | ContextFlags before GetThreadContext | `0x100010` |
| 08 | CreateProcess decoy command line | `explorer.exe shell:RecycleBinFolder` |
| 09 | Minimum physical RAM | `0x80000000` |
| 10 | USBSTOR registry path | `SYSTEM\ControlSet001\Enum\USBSTOR` |
| 11 | Minimum process count for extended scan | `50` |
| 12 | Reverse-engineering tool process name | `cheat-engine-x86_64.exe` |
| 13 | Required `argv[1]` value | `static` |
| 14 | Plaintext C2 hostname | `promoverse.org` |
| 15 | Registry value used for Machine ID | `MachineGuid` |
