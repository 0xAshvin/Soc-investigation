# Linux Downloader — Let’sDefend Challenge

> **A tiny ELF with a simple job: connect, download, XOR, execute.**

[![View PDF Report](https://img.shields.io/badge/View%20PDF-Analysis%20Report-red?style=for-the-badge&logo=adobeacrobatreader)](./Linux_Downloader_Analysis.pdf)

## 🔎 Investigation

Analyzed a suspicious Linux downloader using:

- **Detect It Easy (DIE)** — file identification
- **Ghidra** — static analysis and code-flow analysis

The binary was identified as an **ELF64 AMD64 Linux executable**.

## ⚙️ Execution Flow

```text
File Check
    ↓
Create Socket
    ↓
Connect to Remote IP
    ↓
Send Initial Message
    ↓
Receive Payload
    ↓
XOR Each Byte
    ↓
Write Payload
    ↓
Set Environment Variable
    ↓
fexecve()
    ↓
Execute Payload


🧩 Key Findings
Finding	Value
Remote IP	65.2.144.170
File checked	/tmp/log_de.log
System call number	319
First socket string	l64
XOR key	0x99
Environment variable	CWD
argv[0]	[kworker/0:2]
Connection retry delay	10 seconds
🔬 Analysis Highlights
File Existence Check

The downloader first checks:

/tmp/log_de.log

If the file already exists, the program exits.

Network Communication

The malware creates a socket and attempts to connect to:

65.2.144.170

After a successful connection, it sends:

l64   

The string contains three spaces after l64.

Payload Processing

The program receives data from the remote server and applies:

byte XOR 0x99

to each received byte before writing the processed data.

Payload Execution

Before execution, the malware sets:

CWD = realpath(argv[0])

It then executes the downloaded payload using fexecve() with:

argv[0] = [kworker/0:2]

The name resembles a legitimate Linux kernel-worker process, making this behavior particularly interesting from a detection perspective.

🎯 Takeaway

The sample follows a compact downloader/loader workflow:

Check → Connect → Communicate → Receive → Decode → Write → Execute

Small binary. Straightforward logic. Unwanted guest.

🛠️ Tools

Detect It Easy · Ghidra

🧠 Focus

Linux Malware Analysis · Reverse Engineering · Static Analysis · SOC Investigation


### Important

For the button to work on GitHub, your repository should contain the files **at the same level**:

```text
📁 Repository
├── README.md
└── Linux_Downloader_Analysis.pdf
