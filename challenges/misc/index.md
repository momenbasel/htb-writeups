---
layout: default
title: "Misc"
parent: Challenges
nav_order: 9
permalink: /challenges/misc/
---

# Misc Challenges

Writeups for HTB Miscellaneous challenges.

## Challenge Index

| Challenge | Difficulty | Techniques | Key Takeaway |
|-----------|-----------|------------|--------------|
| [Compressor](compressor/) | Very Easy | Command Injection | Exploiting system() calls |
| [Eternal Loop](eternal-loop/) | Very Easy | Zip Extraction, Scripting | Automated nested archive extraction |
| [Persistence](persistence/) | Easy | Registry, Windows Forensics | Windows persistence mechanisms |
| [MineCraft](minecraft/) | Easy | Programming, Game Logic | Automating game-based challenges |
| [Deterministic](deterministic/) | Easy | Python Sandbox Escape | Breaking out of restricted Python |
| [misDIRection](misdirection/) | Easy | Filesystem Tricks | Hidden data in directory names |
| [Blackhole](blackhole/) | Medium | Pyjail Escape | Advanced Python sandbox bypass |
| [Janken](janken/) | Medium | PRNG Prediction | Predicting random number generators |
| [Cat](misc-cat/) | Medium | Polyglot File | Creating files valid in multiple formats |
| [Quantum Entanglement](quantum/) | Hard | Quantum Computing, Qiskit | Quantum circuit exploitation |

## Key Skills

### Scripting
Many misc challenges require writing quick scripts to automate solutions:
```python
from pwn import *

r = remote('challenge.htb', 1337)
# Interact with the challenge
```

### Python Sandbox Escape
Common pyjail bypass techniques:
```python
# Builtins access
__builtins__.__import__('os').system('id')

# Class hierarchy traversal
''.__class__.__mro__[1].__subclasses__()

# Attribute access tricks
getattr(__builtins__, '__imp' + 'ort__')('os')
```

### Archive/Encoding Puzzles
```bash
# Nested zip extraction
while file output | grep -q 'Zip'; do unzip -o output -d temp && mv temp/* output; done

# Base encoding chains
echo "data" | base64 -d | base32 -d | xxd -r -p
```
