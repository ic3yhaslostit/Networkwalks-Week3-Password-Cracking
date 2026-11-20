# NETWORKWALKS-WEEK3-PASSWORD-CRACKING
Password Cracking with John the Ripper (JTR) and Networkwalks Tools, plus an optional AI-assisted lab with Claude Desktop and HexStrike MCP.

## Week 3 — Password Cracking & AI-Assisted Security Lab

### Overview
Week 3 focused on understanding password security and password-cracking techniques within a controlled cybersecurity laboratory environment.

The week included practical exercises involving John the Ripper (JTR), Networkwalks Tools, Kali Linux, and an optional AI-assisted cybersecurity workflow using Claude Desktop and HexStrike MCP.

### Objectives
- Understand the fundamentals of password-cracking in a controlled lab.
- Work with John the Ripper (JTR).
- Explore password-cracking workflows using Networkwalks Tools.
- Work with password-protected files in Kali Linux.
- Explore the use of AI-assisted workflows in cybersecurity.
- Configure an MCP server and connect it to Claude Desktop.
- Use an AI assistant to drive a security tool through natural-language prompts.

### Labs Completed

#### W3-PM1 — Password Cracking with JTR
Worked through the password-cracking laboratory using John the Ripper against the provided hash.

Key learning areas:
- Password-cracking workflow
- Working with password hashes
- Using JTR with a wordlist (`rockyou.txt`) in a controlled environment
- Understanding the importance of strong password policies

**Flag captured:** `nw{networkwalks_persistence_jtr_270521}`
<img width="819" height="607" alt="jtr_270521" src="https://github.com/user-attachments/assets/08de6abc-9bc4-4b13-8718-c00417381549" />


#### W3-PM2 — Password Cracking with Networkwalks Tools
Worked through the password-cracking laboratory using Networkwalks' own tooling.

Key learning areas:
- Password-protected files
- Security testing in a controlled environment
- Comparing different approaches to password-security testing

**Flag captured:** `nw{cybersecurity_flag_captured_2608}`
<img width="420" height="419" alt="cybersecurity_flag" src="https://github.com/user-attachments/assets/167c54e6-dfd7-4dbb-b554-2d062f4cd5ce" />

#### Optional Lab — AI-Assisted JTR with Claude & HexStrike MCP
I also explored the optional AI-assisted cybersecurity lab involving Claude Desktop and HexStrike MCP.

**Environment**
- Kali Linux
- Python 3 / virtual environment
- HexStrike AI (offensive security toolkit, 150+ integrated tools)
- Claude Desktop
- MCP (Model Context Protocol)

**Setup and Troubleshooting**

During setup, I worked through a few configuration issues:

- *MCP server registration* — Claude Desktop's config file (`claude_desktop_config.json`) already contained the app's own settings, so I had to insert the new `mcpServers` block into the existing JSON structure without breaking it, rather than overwriting the file.
- *JSON syntax* — validated the file with `python3 -m json.tool` after editing to catch missing commas/braces before restarting the app.
- *Python interpreter path* — pointed the MCP config at the Python interpreter inside the HexStrike virtual environment (`hexstrike-env/bin/python`) rather than the system Python, so the server's dependencies resolved correctly.
- *Server dependency* — the HexStrike server needs to be actively running on `localhost:8888` for the MCP connection to work; restarting Claude Desktop without the server running first caused the tool to be unavailable.

**Verification**

Confirmed the connection by asking Claude Desktop to check the John the Ripper installation and version through the MCP server, and listed the full HexStrike toolset (reconnaissance, network scanning, web app testing, and more) available via the connection.

**Task:** Crack a password-protected PDF using JTR through the MCP connection.

Prompt used:
> "Please use JTR tool in this hexstrike MCP server to crack the password of this PDF file. Use the rockyou.txt wordlist dictionary."

Claude used the HexStrike MCP connection to extract the PDF's hash and run John the Ripper automatically.

**Result:** Password cracked — `password1` (1 candidate tried, under 1 second of actual crack time, using `rockyou.txt`).
<img width="1365" height="654" alt="rockyou txt" src="https://github.com/user-attachments/assets/460afce5-1a68-4601-88bb-49e768edc7b6" />

### Key Lessons

**1. Tool knowledge is not enough**
Using cybersecurity tools requires understanding the environment in which they operate — dependencies, paths, permissions, configuration files, and networking can all affect whether a tool works.

**2. Troubleshooting is part of cybersecurity**
The configuration issues in this week's optional lab weren't caused by the security tools themselves — they came from JSON syntax, file paths, and environment setup.

**3. AI can complement cybersecurity workflows**
The Claude + HexStrike MCP exercise showed how an AI assistant can drive established security tools through natural language, handling hash extraction and tool invocation from a single prompt.

This provided practical exposure to the intersection of:
**AI + Automation + Cybersecurity**

**4. Controlled environments matter**
All password-cracking and security-testing activities in this project were performed for educational purposes within a controlled laboratory environment.

### Technologies & Tools
- Kali Linux
- John the Ripper (JTR)
- Networkwalks Tools
- Python
- HexStrike AI
- Claude Desktop
- MCP
- Linux CLI
- Git/GitHub

### Week 3 Takeaway
This week helped me move beyond simply learning cybersecurity concepts and into actually configuring and troubleshooting a multi-tool setup. The biggest lesson was that getting a tool to work reliably takes as much attention to environment and configuration as it does to the tool itself.

### Author
Ilyas Adaranijo

LinkedIn:
https://www.linkedin.com/in/ilyas-adaranijo-910a90446
