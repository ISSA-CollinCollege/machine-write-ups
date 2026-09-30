# Hack The Box — [Machine Name]

- Platform: Hack The Box
- Lab Type: Starting Point / Easy / Medium / Hard
- Operating System: Linux / Windows
- Difficulty: [Difficulty]
- Date Completed: [MM/DD/YYYY]
- Author: [Your Name or Alias]

## Objective

Briefly describe the purpose of the lab and your goals.

Example:
The objective of this lab was to identify vulnerabilities within the target machine, gain initial access, perform privilege escalation, and document the methodology used throughout the engagement.

## Skills Demonstrated

- Network Enumeration
- Service Enumeration
- Web Application Testing
- Credential Discovery
- Exploitation
- Privilege Escalation
- Linux/Windows Post-Exploitation
- Basic Scripting

## Lab Information

| Category | Details |
|---|---|
| Target IP | [IP Address] |
| Machine Name | [Machine Name] |
| OS | [Linux/Windows] |
| Difficulty | [Easy/Medium/etc.] |
| Tools Used | Nmap, Gobuster, Burp Suite, Netcat, etc. |

## Enumeration

### Nmap Scan

Command Used:

```bash
nmap -sC -sV -oN nmap.txt [TARGET IP]

[Paste important results]


---

# Service Enumeration

Break down each discovered service.

```markdown
## Service Enumeration

### HTTP Enumeration

- Visited web page
- Reviewed source code
- Identified login portal
- Discovered hidden directories using Gobuster

Command:

```bash
gobuster dir -u http://[TARGET IP] -w /usr/share/wordlists/dirb/common.txt

Findings:

/admin
/uploads
/backup


---

# Exploitation

```markdown
## Exploitation

### Initial Access

Describe:
- Vulnerability identified
- Exploitation process
- Payload used
- Reverse shell obtained

Example:

A file upload vulnerability allowed arbitrary PHP file uploads. A malicious PHP reverse shell was uploaded and executed to gain remote access.

Listener:

```bash
nc -lvnp 4444


---

# Privilege Escalation

```markdown
## Privilege Escalation

### Enumeration

Commands Used:

```bash
sudo -l
find / -perm -4000 2>/dev/null

Escalation Vector

Describe:

Misconfiguration discovered
Exploit used
Why it worked

Example:

The user had passwordless sudo permissions for vim, allowing shell escape execution.

Command:
sudo vim -c ':!/bin/bash'


---

# Flags Captured

```markdown
## Flags Captured

| Flag Type | Status |
|---|---|
| User Flag | Captured |
| Root/Admin Flag | Captured |

## Lessons Learned

- Importance of thorough enumeration
- Misconfigured file upload protections can lead to RCE
- Sudo misconfigurations are common privilege escalation vectors
- Enumeration often reveals the attack path

## Mitigation Recommendations

- Disable anonymous FTP access
- Implement strict file upload validation
- Apply least privilege principles
- Regularly audit sudo permissions
- Patch outdated services

## References

- GTFOBins
- HackTricks
- Nmap Documentation
- OWASP Testing Guide

Optional Additions (Highly Recommended)
Screenshots Section

Add screenshots for:

Nmap results
Exploitation steps
Reverse shell
Privilege escalation
Flag capture
Attack Path Summary

A quick high-level summary:

## Attack Path Summary

1. Enumerated open ports
2. Identified vulnerable web application
3. Exploited file upload vulnerability
4. Obtained reverse shell
5. Escalated privileges through sudo misconfiguration
6. Captured root flag

Professional Tips:
Keep commands in code blocks
Explain why you ran commands, not just what they output
Focus on methodology over tool dumping
Avoid massive screenshots unless necessary
Keep formatting consistent
Write as if another analyst may need to reproduce your work

Long-Term Portfolio Strategy

As you progress:

Starting Point → concise write-ups
Easy/Medium → more detailed methodology
Hard/Insane → focus heavily on thought process and failed paths explored

Over time you'll naturally build:

A pentesting portfolio
Documentation habits
Technical communication skills
Resume/project material for cybersecurity roles

