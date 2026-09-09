# 🦠 Mac Backdoor — Let'sDefend

> A small Mach-O binary, a hidden C2, and enough decompiler soup to keep Ghidra busy.

This write-up documents the static analysis of a macOS backdoor using **DIE + Ghidra**, focusing on how the C2, HTTP communication, payload handling, XOR encryption, command execution, and file operations were identified.

## 📄 Full Write-up

[![Read the Full PDF](https://img.shields.io/badge/📄_Read_Full_Write--up-PDF-red?style=for-the-badge)](./Mac_Backdoor_Writeup.pdf)

---

## 🔍 Investigation

### 01 — Initial Recon
Identified the sample as a **64-bit Mach-O x86_64** executable and found networking-related Objective-C APIs and suspicious C2-related strings.

![Initial Analysis](screenshots/01-die-analysis.png)

### 02 — C2 Discovery
Traced the C2 configuration in `entry()` and reconstructed the hostname and path from little-endian values.

**C2:** `https://rebelthumb.net/index.php`

![C2 Discovery](screenshots/02-c2-entry.png)

### 03 — HTTP Method
`SendPost()` explicitly sets the HTTP method:

```c
[request setHTTPMethod:&cf_POST];
Method: POST

04 — Payload Transmission

SendPayload() processes the data and passes it to SendPost() for transmission.

Function: SendPayload

05 — Command Execution & Output

MsgCmd() uses _popen() to execute commands and _read() to retrieve their output before sending it back.

Function: MsgCmd

06 — XOR Key

CryptPayload() performs a repeating XOR operation using a 32-byte key.

774c71664d5d25775478607e74555462773e525e18237947355228337f433a3b

07 — Base64 + XOR

DecryptPayload() reveals the processing order:

Base64 Decode → XOR → Decrypted Data

Encoding: Base64

08 — Payload Execution

MsgRun() builds the execution command and launches it through _popen().

Function: MsgRun

09 — Payload File Handling

MsgDown() opens the file using:

_fopen(local_140, "rb");

API: fopen

🧩 Answers
#	Answer
1	https://rebelthumb.net/index.php
2	POST
3	SendPayload
4	MsgCmd
5	774c71664d5d25775478607e74555462773e525e18237947355228337f433a3b
6	Base64
7	MsgRun
8	fopen
🧠 Takeaways
Follow data flow, not just suspicious strings.
Use API calls to understand malware behavior.
Distinguish command execution from output retrieval.
Trace encryption/encoding in the correct order.
Ghidra's param_1, uVar1, and local_XXX names are generated labels — focus first on what the code does.

Small binary. Several functions. One C2. A lot of Ghidra.
