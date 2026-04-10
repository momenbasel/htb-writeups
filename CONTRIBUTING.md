# Contributing to HTB Writeups

Thank you for your interest in contributing! This repository thrives on community contributions.

## Rules

1. **Retired content only** - Never submit writeups for active machines or challenges
2. **Original work** - Submit your own writeups, not copies of others' work
3. **Quality over quantity** - Well-documented writeups with clear steps and explanations
4. **No spoilers** - Do not include flags, passwords, or solutions for active content

## Writeup Guidelines

### Machines

- Place writeups in the correct difficulty folder: `machines/{easy,medium,hard,insane}/MachineName/`
- Use the [machine template](templates/machine-template.md)
- Include: enumeration, foothold, user flag, root flag sections
- Add screenshots or command output for critical steps
- Tag with techniques used (see tag list below)

### Challenges

- Place writeups in the correct category: `challenges/{category}/ChallengeName/`
- Use the [challenge template](templates/challenge-template.md)
- Include: challenge description, approach, solution, key takeaway

### Sherlocks

- Place writeups in the correct difficulty: `sherlocks/{easy,medium,hard}/SherlockName/`
- Use the [sherlock template](templates/sherlock-template.md)
- Include: scenario, investigation steps, answers, tools used

### CTF Events

- Place writeups in: `ctf-events/{event-name}/category/ChallengeName/`
- Include event name and year in the writeup

## File Structure

Each writeup should be in its own directory:

```
machines/easy/MachineName/
|-- README.md          # The writeup
|-- images/            # Screenshots (optional)
|-- scripts/           # Custom scripts used (optional)
```

## Submission Process

1. Fork this repository
2. Create a branch: `git checkout -b writeup/machine-name`
3. Write your content using the appropriate template
4. Ensure your writeup follows the guidelines
5. Submit a Pull Request with:
   - Title: `[Machine/Challenge] Name - Difficulty`
   - Description: Brief summary of what the writeup covers

## Technique Tags

Use these tags in your writeup metadata:

**Exploitation:**
`sql-injection`, `xss`, `ssrf`, `ssti`, `lfi`, `rfi`, `rce`, `deserialization`, `file-upload`, `xxe`, `command-injection`, `prototype-pollution`, `race-condition`, `idor`, `jwt-abuse`, `graphql`

**Active Directory:**
`kerberoasting`, `as-rep-roasting`, `dcsync`, `pass-the-hash`, `golden-ticket`, `silver-ticket`, `constrained-delegation`, `unconstrained-delegation`, `rbcd`, `adcs`, `shadow-credentials`, `gpo-abuse`, `bloodhound`, `dpapi`

**Privilege Escalation:**
`suid`, `sudo-abuse`, `cron-abuse`, `kernel-exploit`, `docker-escape`, `path-hijack`, `wildcard-injection`, `capability-abuse`, `token-impersonation`, `seimpersonate`, `potato-attack`, `uac-bypass`, `dll-hijack`, `service-exploit`

**Binary Exploitation:**
`buffer-overflow`, `rop`, `heap-exploit`, `format-string`, `use-after-free`, `integer-overflow`, `ret2libc`, `shellcode`

**Crypto:**
`rsa`, `aes`, `ecc`, `padding-oracle`, `hash-cracking`, `custom-cipher`, `weak-rng`

**Forensics:**
`memory-forensics`, `disk-forensics`, `network-forensics`, `log-analysis`, `malware-analysis`, `steganography`

**Other:**
`pivoting`, `tunneling`, `phishing`, `social-engineering`, `cloud`, `docker`, `kubernetes`, `ci-cd`

## Code of Conduct

- Be respectful and constructive
- Help others learn - explain the "why" not just the "how"
- Credit tools and techniques appropriately
- Do not submit malicious content

## Questions?

Open an issue with the `question` label.
