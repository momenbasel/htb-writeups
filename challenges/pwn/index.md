---
layout: default
title: "Pwn"
parent: Challenges
nav_order: 5
permalink: /challenges/pwn/
---

# Pwn (Binary Exploitation) Challenges

Writeups for HTB Binary Exploitation challenges.

## Challenge Index

| Challenge | Difficulty | Techniques | Key Takeaway |
|-----------|-----------|------------|--------------|
| [Getting Started](getting-started/) | Very Easy | Stack Overflow, ret2win | Basic buffer overflow |
| [Initialise Connection](initialise-connection/) | Very Easy | Netcat, Basics | Connecting to remote services |
| [Leet Test](leet-test/) | Easy | Buffer Overflow, NX Bypass | Stack smashing with NX |
| [Space Pirate: Going Deeper](space-pirate/) | Easy | Buffer Overflow, RIP Control | Controlling instruction pointer |
| [Jeeves](jeeves-pwn/) | Easy | Integer Overflow, Format String | Format string read |
| [Labyrinth](labyrinth/) | Easy | Buffer Overflow, ret2win | Return to function |
| [Regularity](regularity/) | Easy | Buffer Overflow, Shellcode | Writing to executable stack |
| [Void](void/) | Easy | Buffer Overflow, ret2libc | Return-to-libc technique |
| [Bat Computer](bat-computer/) | Easy | Stack Overflow, NX Off | Shellcode injection |
| [Pwnshop](pwnshop/) | Easy | Buffer Overflow, GOT Overwrite | Global Offset Table overwrite |
| [Lesson](lesson/) | Medium | Stack Pivot, ROP | Stack pivoting technique |
| [Entity](entity/) | Medium | Type Confusion, Union | C type confusion exploit |
| [Rope](rope-pwn/) | Medium | Heap, Use-After-Free | Heap exploitation basics |
| [Oxidized ROP](oxidized-rop/) | Medium | Rust, ROP Chain | ROP in Rust binaries |
| [Math Door](math-door/) | Medium | Format String Write | Format string write-what-where |
| [HTB Console](htb-console/) | Medium | GOT Overwrite, ROP | Chaining GOT overwrites |
| [Hellhound](hellhound/) | Hard | Heap Exploitation, tcache | tcache poisoning attack |
| [Pandora's Box](pandoras-box/) | Hard | Stack Canary Leak, ROP | Bypassing stack protections |
| [Blacksmith](blacksmith/) | Hard | Heap, House of Force | Advanced heap technique |
| [Sound of Silence](sound-of-silence/) | Hard | ret2dlresolve | Dynamic linker exploitation |

## Exploitation Techniques

| Technique | Difficulty | Challenges |
|-----------|-----------|------------|
| Stack Buffer Overflow | Beginner | Getting Started, Space Pirate, Labyrinth |
| ret2win | Beginner | Getting Started, Labyrinth |
| Shellcode Injection | Beginner | Regularity, Bat Computer |
| ret2libc | Intermediate | Void |
| ROP Chains | Intermediate | Lesson, Oxidized ROP, HTB Console |
| Format String | Intermediate | Jeeves, Math Door |
| GOT Overwrite | Intermediate | Pwnshop, HTB Console |
| Heap - UAF | Advanced | Rope |
| Heap - tcache | Advanced | Hellhound |
| House of Force | Advanced | Blacksmith |
| ret2dlresolve | Advanced | Sound of Silence |

## Binary Protections Reference

| Protection | What It Does | How to Bypass |
|------------|-------------|---------------|
| NX (No-Execute) | Stack not executable | ROP, ret2libc |
| Stack Canary | Detects stack overflow | Leak canary via format string/info leak |
| ASLR | Randomizes addresses | Leak addresses, partial overwrite |
| PIE | Randomizes binary base | Leak binary address |
| RELRO (Full) | GOT read-only | Cannot overwrite GOT |
| RELRO (Partial) | GOT writable | GOT overwrite |

```bash
# Check protections
checksec --file=binary
```

## Essential Tools

| Tool | Purpose |
|------|---------|
| pwntools | Python exploit development framework |
| GDB + GEF/pwndbg | Dynamic debugging |
| ROPgadget | Find ROP gadgets |
| one_gadget | Find one-shot RCE gadgets in libc |
| checksec | Check binary protections |
| ropper | Alternative ROP gadget finder |
| patchelf | Patch ELF binary interpreter/rpath |
| seccomp-tools | Analyze seccomp filters |
| Ghidra | Static analysis/decompilation |
