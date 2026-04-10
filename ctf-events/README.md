---
layout: default
title: CTF Events
nav_order: 6
description: "Official HTB CTF event writeups from 2023-2026"
permalink: /ctf-events/
---

# HTB CTF Events - Comprehensive Index (2023-2026)

Writeups and challenge indexes from all official Hack The Box competitive CTF events.

Data sourced from official HTB GitHub repos, CTFtime.org, and community writeups.

---

## Events Master Timeline

| Event | Year | Theme | Date | Teams/Players | Challenges | Official Repo |
|-------|------|-------|------|--------------|------------|---------------|
| [Cyber Apocalypse](#cyber-apocalypse-2025---tales-from-eldoria) | 2025 | Tales from Eldoria | Mar 21-26, 2025 | 5,000+ teams | 77 | [hackthebox/cyber-apocalypse-2025](https://github.com/hackthebox/cyber-apocalypse-2025) |
| [Business CTF](#business-ctf-2025---operation-blackout) | 2025 | Operation Blackout | 2025 | 1,000+ teams | 66 | [hackthebox/business-ctf-2025](https://github.com/hackthebox/business-ctf-2025) |
| [University CTF](#university-ctf-2025---tinsel-trouble) | 2025 | Tinsel Trouble | Dec 2025 | 2,000+ teams | 21 | [hackthebox/university-ctf-2025](https://github.com/hackthebox/university-ctf-2025) |
| [StackSmash CTF](#stacksmash-ctf-2025) | 2025 | Binary Exploitation | 2025 | - | 5 | [hackthebox/stack-smash-2025](https://github.com/hackthebox/stack-smash-2025) |
| [Bug Bounty CTF](#bug-bounty-ctf-2025) | 2025 | Web Security | 2025 | - | 7 | [hackthebox/bug-bounty-ctf](https://github.com/hackthebox/bug-bounty-ctf) |
| [Holmes](#holmes-2025) | 2025 | Cyber Investigation | 2025 | - | 5 | [hackthebox/holmes-2025](https://github.com/hackthebox/holmes-2025) |
| [Cyber Apocalypse](#cyber-apocalypse-2024---hacker-royale) | 2024 | Hacker Royale | Mar 2024 | 5,730 teams | 67 | [hackthebox/cyber-apocalypse-2024](https://github.com/hackthebox/cyber-apocalypse-2024) |
| [Business CTF](#business-ctf-2024---the-vault-of-hope) | 2024 | The Vault of Hope | May 2024 | 1,000+ teams | 66 | [hackthebox/business-ctf-2024](https://github.com/hackthebox/business-ctf-2024) |
| [University CTF](#university-ctf-2024---binary-badlands) | 2024 | Binary Badlands | Dec 13-15, 2024 | 2,000+ teams | 39 | [hackthebox/university-ctf-2024](https://github.com/hackthebox/university-ctf-2024) |
| [Hack The Boo](#hack-the-boo-2024) | 2024 | Halloween Theme | Oct 2024 | - | 30 | [hackthebox/hacktheboo-2024](https://github.com/hackthebox/hacktheboo-2024) |
| [HHV CTF (DEFCON)](#hhv-ctf-2024) | 2024 | Hardware Hacking Village | Aug 2024 | - | 4 | [hackthebox/hhv-ctf-2024](https://github.com/hackthebox/hhv-ctf-2024) |
| [Cyber Apocalypse](#cyber-apocalypse-2023---the-cursed-mission) | 2023 | The Cursed Mission | Mar 19-23, 2023 | 12,000+ players | 68+ | No official repo |
| [Business CTF](#business-ctf-2023---the-great-escape) | 2023 | The Great Escape | Jul 14-16, 2023 | 982 teams / 5,117 players | 30+ | No official repo |
| [University CTF](#university-ctf-2023---brains--bytes) | 2023 | Brains & Bytes | Dec 2023 | - | 18 | [hackthebox/uni-ctf-2023](https://github.com/hackthebox/uni-ctf-2023) |
| [Hack The Boo](#hack-the-boo-2023) | 2023 | Halloween Theme | Oct 2023 | - | 26 | [hackthebox/htboo-ctf-2023](https://github.com/hackthebox/htboo-ctf-2023) |

---

## 2025 Events

---

### Cyber Apocalypse 2025 - Tales from Eldoria

**Date:** March 21-26, 2025 | **Participants:** 5,000+ teams | **Total Challenges:** 77

Official Repo: [hackthebox/cyber-apocalypse-2025](https://github.com/hackthebox/cyber-apocalypse-2025)

#### Crypto (7 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Kewiri | - | Elliptic curve discrete log (Smart's attack) |
| Traces | - | AES CTR stream cipher key/nonce reuse |
| Hourcle | - | AES CBC decryption oracle |
| Prelim | - | Permutation group decryption (RSA-like) |
| Verilicious | - | Hidden Number Problem via PKCSv1 padding |
| Copperbox | - | Coppersmith attack on LCG-based cryptosystem |
| Twin Oracles | - | RSA LSB oracle obfuscated by LCG |

#### Reversing (7 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| SealedRune | Very Easy | - |
| EncryptedScroll | Very Easy | - |
| Impossimaze | Easy | - |
| EndlessCycle | Easy | - |
| Singlestep | Medium | - |
| Gateway | Hard | - |
| Heart Protector | Hard | - |

#### Pwn (7 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Blessing | Very Easy | - |
| Quack Quack | Very Easy | - |
| Laconic | Easy | - |
| Crossbow | Easy | - |
| Strategist | Medium | - |
| Contractor | Medium | - |
| Vault | Hard | - |

#### Forensics (7 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| A New Hire | - | - |
| Thorins Amulet | - | - |
| Stealth Invasion | - | - |
| Silent Trap | - | - |
| ToolPie | - | - |
| Cave Expedition | - | - |
| Tales for the Brave | - | Malware behavioral analysis |

#### Web (6 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Whispers of the Moonbeam | - | - |
| Trial by Fire | - | - |
| Cyber Attack | - | - |
| Eldoria Panel | Medium | - |
| Eldoria Realms | - | - |
| Aurors Archive | Hard | - |

#### Prompt Injection (5 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Cursed GateKeeper | - | AI prompt injection |
| Elixir Emporium | - | AI prompt injection |
| Embassy | - | AI prompt injection |
| Mirror Witch | - | AI prompt injection |
| Lunar Orb | - | AI prompt injection |

#### Coding (5 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| ClockWork Guardian | - | Programming challenge |
| Dragon Flight | - | Programming challenge |
| Dragon Fury | - | Programming challenge |
| Enchanted Cipher | - | Programming challenge |
| Summoners Incantation | - | Programming challenge |

#### Secure Coding (3 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Lyra's Tavern | Easy | Secure development |
| Stoneforge's Domain | - | Secure development |
| Arcane Auctions | - | Secure development |

#### OSINT (7 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| The Stone That Whispers | - | Geolocation |
| Echoes in Stone | - | Geolocation |
| The Mechanical Bird's Nest | Medium | - |
| The Hillside Haven | - | - |
| The Ancient Citadel | - | - |
| The Shadowed Sigil | - | - |
| The Poisoned Scroll | - | - |

#### Blockchain (3 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Eldorion | Very Easy | - |
| HeliosDEX | Easy | - |
| EldoriaGate | Medium | - |

#### Machine Learning (5 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Enchanted Weights | - | ML exploitation |
| Wasteland | - | ML exploitation |
| Crystal Corruption | - | ML exploitation |
| Reverse Prompt | - | Prompt reversal |
| Malakar's Deception | - | ML exploitation |

---

### Business CTF 2025 - Operation Blackout

**Date:** 2025 | **Participants:** 1,000+ teams | **Total Challenges:** 66

Official Repo: [hackthebox/business-ctf-2025](https://github.com/hackthebox/business-ctf-2025)

#### Pwn (5 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Power Greed | - |
| LiteServe | - |
| Null Assembler | - |
| Cyber Bankrupt | - |
| NeonCGI | - |

#### Reversing (5 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Industry Secret | - |
| Scrambled Payload | - |
| TinyPlatformer | - |
| EvilBox | VM reverse engineering |
| ShadowLabyrinth | - |

#### Web (4 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Blackout Ops | Blind web vulns + XSS |
| Volnaya Forums | - |
| QuickBlog | - |
| novacore | - |

#### Crypto (5 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Transcoded | - |
| Hidden Handshake | - |
| Phoenix Zero Trust | - |
| Early Bird | - |
| Curveware | - |

#### Forensics (5 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Phantom Check | - |
| Smoke & Mirrors | - |
| Ghost Thread | - |
| The Nexus Breach | - |
| Driver's Shadow | - |

#### Hardware (5 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Echoes Of Authority | - |
| Volnayan Whisper | - |
| Sky Recon | - |
| Volnatek Motors | - |
| PhantomGate | Firmware deobfuscation |

#### Blockchain (3 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Enlistment | - |
| Spectral | - |
| Blockout | - |

#### ICS/SCADA (4 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Whispers | - |
| Floody | - |
| Heat Plan | - |
| Gridcryp | - |

#### AI/ML (5 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| External Affairs | - |
| Loyalty Survey | - |
| TrynaSob Ransomware | - |
| Doctrine Studio | - |
| Power Supply | - |

#### Cloud (5 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Dashboarded | AWS misconfig |
| Vault | AWS misconfig |
| TowerDump | AWS misconfig |
| EBS | AWS misconfig |
| PipeDream | AWS misconfig |

#### Coding (5 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Threat Index | - |
| Honeypot | - |
| Triple Knock | - |
| Blackwire | - |
| Ghost Path | - |

#### Secure Coding (3 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Phoenix Sentinel | - |
| DarkWire | - |
| Atomic Protocol | - |

#### Machine Learning (3 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Decision Gate | - |
| Neural Detonator | - |
| Uplink Artifact | - |

#### Mobile (1 challenge)

| Challenge | Key Technique |
|-----------|---------------|
| Terminal | - |

---

### University CTF 2025 - Tinsel Trouble

**Date:** December 2025 | **Total Challenges:** 21

Official Repo: [hackthebox/university-ctf-2025](https://github.com/hackthebox/university-ctf-2025)

#### Pwn (3 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| SHL337 | - |
| Feel My Terror | - |
| Starshard Core | - |

#### Reversing (3 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Clock Work Memory | - |
| Starshard Reassembly | - |
| CloudyCore | - |

#### Web (3 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| SilentSnow | - |
| DeadRoute | - |
| PeppermintRoute | Race condition + path traversal |

#### Crypto (3 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Optimistic | - |
| One Trick Pony | - |
| Disguised | - |

#### Forensics (3 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Snowy Extension | - |
| A Trail of Snow and Deception | - |
| SantaGiveaway | - |

#### Coding (3 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Flickering Snowglobe | - |
| Bauble Sort | - |
| Cellcode | - |

#### OSINT (3 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Tinselwick | - |
| SleighComms | Audio signal analysis, cipher decoding |
| FrostFleet | Maritime OSINT, coordinate analysis |

---

### StackSmash CTF 2025

**Focus:** Pure binary exploitation (Pwn only)

Official Repo: [hackthebox/stack-smash-2025](https://github.com/hackthebox/stack-smash-2025)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| It's a me, Jumpio! | 1/5 | Logical bug in strcmp bypass with negative value |
| Super Jumpio Kart | 2/5 | Format string vuln - libc/canary leak + ret2libc |
| Jumpio's Love Letter | 3/5 | File Struct exploit with vtables |
| Refreshments | 4/5 | House of Orange heap exploit |
| Villainous | 5/5 | Protocol reversing + C++ vtable exploitation |

---

### Bug Bounty CTF 2025

**Focus:** Web application security / Bug bounty methodology

Official Repo: [hackthebox/bug-bounty-ctf](https://github.com/hackthebox/bug-bounty-ctf)

| Challenge | Category | Key Technique |
|-----------|----------|---------------|
| CriticalOps | Web | Secret key disclosure, JWT manipulation |
| JinjaCare | Web | Server-Side Template Injection (SSTI) |
| Neovault | Web | IDOR + MongoDB ObjectId bruteforce |
| CitiSmart | Web | Directory fuzzing, API info disclosure |
| Speednet | Web | GraphQL introspection, IDOR, 2FA bypass, batching attack, ATO |
| Novaenergy | Web | Directory fuzzing, API info disclosure |
| sattrack | Web | JS analysis, client-side prototype pollution, JSON injection, CSP bypass, XSS |

---

### Holmes 2025

**Focus:** Defensive security investigation (Threat Intel, SOC, DFIR, Malware Analysis)

Official Repo: [hackthebox/holmes-2025](https://github.com/hackthebox/holmes-2025)

| Challenge | Category | Difficulty |
|-----------|----------|-----------|
| The Card | Threat Intelligence | 2/5 |
| The Watchman's Residue | SOC | 2/5 |
| The Enduring Echo | DFIR | 3/5 |
| The Tunnel Without Walls | DFIR | 3/5 |
| The Payload | Malware Analysis | 4/5 |

---

## 2024 Events

---

### Cyber Apocalypse 2024 - Hacker Royale

**Date:** March 2024 | **Participants:** 5,730 teams | **Total Challenges:** 67 | **42,848 flags submitted** | **8 teams solved all 67**

Official Repo: [hackthebox/cyber-apocalypse-2024](https://github.com/hackthebox/cyber-apocalypse-2024)

#### Crypto (10 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Dynastic | Very Easy | - |
| Makeshift | Very Easy | - |
| Primary Knowledge | Very Easy | - |
| Blunt | Easy | - |
| Iced Tea | Easy | - |
| Arranged | Medium | - |
| Partial Tenacity | Medium | - |
| Permuted | Hard | - |
| Tsayaki | Hard | - |
| ROT128 | Insane | - |

#### Forensics (10 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| An unusual sighting | Very Easy | - |
| It Has Begun | Very Easy | - |
| Urgent | Very Easy | - |
| Fake Boost | Easy | Discord token analysis |
| Pursue The Tracks | Easy | - |
| Data Siege | Medium | - |
| Phreaky | Medium | PCAP analysis |
| Confinement | Hard | - |
| Game Invitation | Hard | Malware analysis |
| Oblique Final | Insane | - |

#### Misc (10 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Character | Very Easy | - |
| Stop Drop and Roll | Very Easy | - |
| Cubicle Riddle | Easy | - |
| Unbreakable | Easy | - |
| Were Pickle Phreaks | Easy | Python pickle deserialization |
| Colored Squares | Medium | - |
| Quantum Conundrum | Medium | - |
| Were Pickle Phreaks Revenge | Medium | - |
| MultiDigilingual | Hard | - |
| Path of Survival | Hard | - |

#### Pwn (10 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Delulu | Very Easy | - |
| Tutorial | Very Easy | - |
| Writing on the wall | Very Easy | - |
| Pet companion | Easy | - |
| Rocket Blaster XXX | Easy | - |
| Death Note | Medium | - |
| Sound of Silence | Medium | - |
| Maze of Mist | Hard | - |
| Oracle | Hard | - |
| Gloater | Insane | - |

#### Reversing (9 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| BoxCutter | Very Easy | - |
| LootStash | Very Easy | - |
| PackedAway | Very Easy | UPX unpacking |
| Crushing | Easy | - |
| FollowThePath | Medium | - |
| QuickScan | Medium | - |
| FlecksOfGold | Hard | - |
| Metagaming | Hard | C++ template metaprogramming |
| MazeOfPower | Insane | - |

#### Web (9 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Flag Command | Very Easy | - |
| KORP Terminal | Very Easy | - |
| TimeKORP | Very Easy | - |
| Labyrinth Linguist | Easy | SSTI |
| Testimonial | Easy | - |
| LockTalk | Medium | JWT + Python CVE |
| SerialFlow | Medium | Deserialization |
| Percetron | Hard | - |
| apexsurvive | Insane | - |

#### Hardware (5 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| BunnyPass | Very Easy | - |
| Maze | Very Easy | - |
| Rids | Easy | - |
| The PROM | Medium | - |
| Flash-ing Logs | Hard | - |

#### Blockchain (3 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Russian Roulette | Very Easy | - |
| Recovery | Easy | - |
| Lucky Faucet | Easy | - |

---

### Business CTF 2024 - The Vault of Hope

**Date:** May 2024 | **Total Challenges:** 66

Official Repo: [hackthebox/business-ctf-2024](https://github.com/hackthebox/business-ctf-2024)

#### FullPwn (5 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Submerged | Very Easy |
| Survivor | Easy |
| Swarm | Easy |
| NeoHub | Medium |
| Bulwark | Hard |

#### Blockchain (4 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Recruitment | Very Easy |
| NotADemocraticElection | Easy |
| MetaVault | Easy |
| Brokenswap | Medium |

#### Cloud (5 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Scurried | Very Easy | - |
| MetaRooted | Easy | - |
| Protrude | Easy | - |
| CloudOfSmoke | Medium | - |
| Asceticism | Insane | - |

#### Coding (5 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Computational Recruiting | Very Easy |
| Bag Secured | Easy |
| Dynamic Paths | Easy |
| Branching Tactics | Medium |
| Nothing Without A Cost | Hard |

#### Crypto (5 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| eXciting Outpost Recon | Very Easy |
| Bloom Bloom | Easy |
| Living with Elegance | Easy |
| Not that random | Medium |
| Blessed | Hard |

#### Forensics (5 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Caving | Very Easy |
| Silicon Data Sleuthing | Easy |
| Tangled Heist | Easy |
| Mitigation | Medium |
| Counter Defensive | Hard |

#### Hardware (3 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| It's Oops PM | Very Easy |
| Say Cheese! | Easy |
| Six Five O Two | Medium |

#### ICS/SCADA (3 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Shush Protocol | Very Easy |
| Sneak peek | Easy |
| Knock Knock | Medium |

#### Misc (7 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Aptitude Test | Very Easy |
| Chrono Mind | Easy |
| Hidden Path | Easy |
| Locked Away | Easy |
| Super-Duper Pwn | Easy |
| Prison Pipeline | Medium |
| Zephyr | Medium |

#### Pwn (5 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Regularity | Very Easy |
| Abyss | Easy |
| No Gadgets | Easy |
| Insidious | Medium |
| Pyrrhus | Hard |

#### Reversing (5 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| FlagCasino | Very Easy |
| DontPanic | Easy |
| SnappedShut | Easy |
| TunnelMadness | Medium |
| SatelliteHijack | Hard |

#### Web (6 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| Jailbreak | Very Easy | - |
| Blueprint Heist | Easy | - |
| HTB Proxy | Easy | - |
| Magicom | Medium | - |
| OmniWatch | Medium | - |
| SOS or SSO? | Hard | - |

---

### University CTF 2024 - Binary Badlands

**Date:** December 13-15, 2024 | **Total Challenges:** 39 | **8 categories**

Official Repo: [hackthebox/university-ctf-2024](https://github.com/hackthebox/university-ctf-2024)

#### Blockchain (4 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| CryoPod | Very Easy | - |
| ForgottenArtifact | Easy | - |
| FrontierMarketplace | Medium | - |
| Stargazer | Hard | UUPSUpgradeable + ERC1967Proxy |

#### Coding (5 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Conflict Cruncher | - |
| Exclusivity | - |
| Word Wrangler | - |
| Energy Crystals | - |
| Weighted Starfield | - |

#### Crypto (5 challenges)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| alphascii clashing | Very Easy | MD5 collision |
| MulTLock | Very Easy | Weak timestamp-based encryption |
| exfiltrated entropy | Easy | Exploiting Linear Congruential Generator |
| cryptospiracy theory | Medium | Brute-force AES key + weak affine cipher |
| Clutch | Hard | - |

#### Forensics (4 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Frontier Exposed | Very Easy |
| Wanted Alive | Easy |
| Binary Badresources | Medium |
| Signaling Victorious | Hard |

#### FullPwn (3 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Apolo | Very Easy |
| Clouded | Easy |
| Freedom | Medium |

#### Pwn (4 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Reconstruction | Very Easy |
| Recruitment | Easy |
| Prison Break | Medium |
| Dead or Alive | Hard |

#### Reversing (4 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| CryoWarmup | Very Easy |
| SecurityInTheFront | Easy |
| ColossalBreach | Medium |
| GravitometerGambit | Hard |

#### Web (4 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Armaxis | Very Easy |
| Breaking Bank | Easy |
| EncoDecept | Medium |
| Intergalactic Bounty | Hard |

---

### Hack The Boo 2024

**Date:** October 2024 | **Total Challenges:** 30

Official Repo: [hackthebox/hacktheboo-2024](https://github.com/hackthebox/hacktheboo-2024)

#### Crypto (5 challenges)

| Challenge |
|-----------|
| brevi moduli |
| sekur julius |
| sugar free candies |
| binary basis |
| hybrid unifier |

#### Web (4 challenges)

| Challenge |
|-----------|
| waywitch |
| phantom script |
| unholy union |
| void whispers |

#### Forensics (5 challenges)

| Challenge |
|-----------|
| Forbidden Manuscript |
| Sp00ky Theme |
| The Shortcut Haunting |
| Foggy Intrusion |
| Ghostly Persistence |

#### Reversing (5 challenges)

| Challenge |
|-----------|
| CryptOfTheUndead |
| Graverobber |
| SpookyPass |
| LinkHands |
| Terrorfryer |

#### Pwn (5 challenges)

| Challenge |
|-----------|
| El Teteo |
| Mathematricks |
| Que onda |
| El Mundo |
| El Pipo |

#### Coding (5 challenges)

| Challenge |
|-----------|
| addition |
| oddly_even |
| reversal |
| minimax |
| replacement |

---

### HHV CTF 2024 (DEFCON Hardware Hacking Village)

**Date:** August 2024 | **Total Challenges:** 4 | **Focus:** Hardware only

Official Repo: [hackthebox/hhv-ctf-2024](https://github.com/hackthebox/hhv-ctf-2024)

| Challenge | Difficulty | Key Technique |
|-----------|-----------|---------------|
| FF Jump Street | Easy | 6502 assembly - bypass hardware bug |
| yoU ART | Easy | Decode dynamic UART data |
| Override | Medium | Modify MD5 hash in flash memory |
| The Last Frontier | Hard | Modbus/TCP custom function code analysis |

---

## 2023 Events

---

### Cyber Apocalypse 2023 - The Cursed Mission

**Date:** March 19-23, 2023 | **Participants:** 12,000+ players | **Total Challenges:** 68+

No official GitHub repo. Community master writeup: [HTB-CA23-Master-Writeup](https://github.com/michael-hart-github/HTB-CA23-Master-Writeup)

#### Blockchain (3 challenges)

| Challenge |
|-----------|
| Navigating the Unknown |
| Shooting 101 |
| The Art of Deception |

#### Cryptography (10 challenges)

| Challenge |
|-----------|
| Ancient Encodings |
| Small StEps |
| Perfect Synchronization |
| Multipage Recyclings |
| Inside the Matrix |
| Converging Visions |
| Colliding Heritage |
| Biased Heritage |
| Elliptic Labyrinth |
| Elliptic Labyrinth Revenge |

#### Forensics (10 challenges)

| Challenge |
|-----------|
| Alien Cradle |
| Extraterrestrial Persistence |
| Packet Cyclone |
| Plaintext Tleasure |
| Roten |
| Artifacts of Dangerous Sightings |
| Bashic Ransomware |
| Relic Maps |
| Interstellar C2 |
| Pandora's Bane |

#### Hardware (5 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Critical Flight | Circuit analysis |
| Debug | - |
| HM74 | Hamming (7,4) error correction |
| Secret Code | PCB signals + 7-segment LED |
| Timed Transmission | - |

#### Machine Learning (6 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Reconfiguration | Very Easy |
| Reading the Stars | - |
| Mysterious Learnings | Easy |
| Last Hope | Medium |
| On the Rescue | Medium |
| Vision Chip | Medium |

#### Misc (8 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Persistence | - |
| Restricted | - |
| Remote Computation | - |
| Calibration | - |
| Janken | - |
| Hijack | YAML deserialization RCE |
| Nehebkaus Trap | - |
| The Chasms Crossing Conundrum | - |

#### Pwn (10 challenges)

| Challenge |
|-----------|
| Getting Started |
| Questionnaire |
| Initialise Connection |
| Labyrinth |
| Pandora's Box |
| Control Room |
| Kana |
| Math Door |
| Runic |
| Void |

#### Reversing (7 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Shattered Tablet | - |
| She Shells C Shells | - |
| Needle in a Haystack | - |
| Hunting License | - |
| Alien Saboteur | - |
| Cave System | Angr symbolic execution |
| Vessel Cartographer | - |

#### Web (9 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Trapped Source | Sensitive data exposure |
| Gunhead | Command injection |
| Drobots | SQL injection |
| Passman | GraphQL |
| Orbital | - |
| Didactic Octo Paddle | - |
| SpyBug | XSS |
| TrapTrack | SSRF + Redis deserialization RCE |
| UnEarthly Shop | - |

---

### Business CTF 2023 - The Great Escape

**Date:** July 14-16, 2023 | **Participants:** 982 teams / 5,117 players | **Total Challenges:** 30+

No official GitHub repo. Community writeups: [0xKrat0s writeups](https://github.com/0xKrat0s/HTB-Business-CTF-2023-The-Great-Escape)

Categories: Web, Pwn, Crypto, Forensics, Reversing, Cloud, Blockchain, SCADA, FullPwn

#### Crypto (5 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Initialization | - |
| I'm gRoot | - |
| Interception | - |
| PRaNsomG | - |
| Vitrium Stash | - |

#### Forensics (3+ challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Red Miners | - |
| Scripts and Formulas | - |
| Hypercraft | Obfuscated malware analysis |

#### Blockchain (2+ challenges)

| Challenge |
|-----------|
| Funds Secured |
| PaidContr-actor |

#### Cloud (2 challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Emit | - |
| Unveiled | S3 bucket misconfiguration |

#### SCADA (2+ challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Watch Tower | - |
| Intrusion | Modbus network traffic analysis |

#### Web (2+ challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Watersnake | Java SnakeYaml deserialization |
| Lazy Ballot | - |

#### FullPwn (2+ challenges)

| Challenge | Key Technique |
|-----------|---------------|
| Langmon | WordPress exploitation |
| Vanguard | Insecure file upload + request smuggling |

#### Pwn (known challenges)

| Challenge |
|-----------|
| Backtrack |
| Hackback |
| Payback |

#### Reversing (known challenges)

| Challenge |
|-----------|
| DrillingPlatform |

---

### University CTF 2023 - Brains & Bytes

**Date:** December 2023 | **Total Challenges:** 18

Official Repo: [hackthebox/uni-ctf-2023](https://github.com/hackthebox/uni-ctf-2023)

#### Crypto (4 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| MSS | Easy |
| MSS Revenge | Easy |
| Mayday Mayday | Medium |
| Zombie Rolled | Hard |

#### Forensics (3 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| One Step Closer | Easy |
| ZombieNet | Medium |
| Shadow of the Undead | Hard |

#### FullPwn (3 challenges)

| Challenge |
|-----------|
| Androcat |
| Apethanto |
| Umbrella |

#### Pwn (3 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| Great Old Talisman | Easy |
| Zombienator | Medium |
| Zombiedote | Hard |

#### Reversing (3 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| WindowOfOpportunity | Easy |
| BioBundle | Medium |
| RiseFromTheDead | Hard |

#### Web (3 challenges)

| Challenge | Difficulty |
|-----------|-----------|
| GateCrash | Easy |
| Nexus Void | Medium |
| PhantomFeed | Hard |

---

### Hack The Boo 2023

**Date:** October 2023 | **Total Challenges:** 26

Official Repo: [hackthebox/htboo-ctf-2023](https://github.com/hackthebox/htboo-ctf-2023)

#### Web (6 challenges)

| Challenge |
|-----------|
| CandyVault |
| Spellbound Servants |
| SpookTastic |
| HauntMArt |
| PumpkinSpice |
| GhostlyTemplates |

#### Pwn (5 challenges)

| Challenge |
|-----------|
| Lemonade Stand v1 |
| Lesson |
| Magic Trick |
| Pinata |
| Claw Machine |

#### Reversing (5 challenges)

| Challenge |
|-----------|
| CandyBowl |
| Dynamic Secrets |
| GhostInTheMachine |
| SpellBrewery |
| SpookyCheck |

#### Forensics (5 challenges)

| Challenge |
|-----------|
| Bat Problems |
| Spooky phishing |
| Vulnerable Season |
| Trick or Treat |
| Valhalloween |

#### Crypto (5 challenges)

| Challenge |
|-----------|
| Hexoding64 |
| SPG |
| yesnce |
| Symbols |
| Leaking Park |

---

## Official Writeup Repositories (All Events)

| Event | Repository | Branch |
|-------|-----------|--------|
| Cyber Apocalypse 2025 | [hackthebox/cyber-apocalypse-2025](https://github.com/hackthebox/cyber-apocalypse-2025) | main |
| Business CTF 2025 | [hackthebox/business-ctf-2025](https://github.com/hackthebox/business-ctf-2025) | master |
| University CTF 2025 | [hackthebox/university-ctf-2025](https://github.com/hackthebox/university-ctf-2025) | main |
| StackSmash 2025 | [hackthebox/stack-smash-2025](https://github.com/hackthebox/stack-smash-2025) | - |
| Bug Bounty CTF 2025 | [hackthebox/bug-bounty-ctf](https://github.com/hackthebox/bug-bounty-ctf) | - |
| Holmes 2025 | [hackthebox/holmes-2025](https://github.com/hackthebox/holmes-2025) | - |
| Cyber Apocalypse 2024 | [hackthebox/cyber-apocalypse-2024](https://github.com/hackthebox/cyber-apocalypse-2024) | main |
| Business CTF 2024 | [hackthebox/business-ctf-2024](https://github.com/hackthebox/business-ctf-2024) | main |
| University CTF 2024 | [hackthebox/university-ctf-2024](https://github.com/hackthebox/university-ctf-2024) | master |
| Hack The Boo 2024 | [hackthebox/hacktheboo-2024](https://github.com/hackthebox/hacktheboo-2024) | - |
| HHV CTF 2024 | [hackthebox/hhv-ctf-2024](https://github.com/hackthebox/hhv-ctf-2024) | - |
| University CTF 2023 | [hackthebox/uni-ctf-2023](https://github.com/hackthebox/uni-ctf-2023) | main |
| Hack The Boo 2023 | [hackthebox/htboo-ctf-2023](https://github.com/hackthebox/htboo-ctf-2023) | - |

## Community Writeup Resources

- [CTFtime - HTB CTF Events](https://ctftime.org/ctf/554/) - Event ratings, tasks, and community writeups
- [0xdf hacks stuff](https://0xdf.gitlab.io/) - Comprehensive HTB writeups
- [7Rocky CTF scripts](https://github.com/7Rocky/CTF-scripts) - Crypto/Pwn challenge solutions
- [HTB-CA23 Master Writeup](https://github.com/michael-hart-github/HTB-CA23-Master-Writeup) - Community-compiled CA2023 writeups
- [InfoSec Write-ups (Medium)](https://infosecwriteups.com/) - Community writeup platform

## Challenge Statistics Summary

| Event | Blockchain | Cloud | Coding | Crypto | Forensics | Hardware/ICS | ML/AI | Misc | OSINT | Pwn | Reversing | Web | SecCoding | FullPwn | Other | Total |
|-------|-----------|-------|--------|--------|-----------|-------------|-------|------|-------|-----|-----------|-----|-----------|---------|-------|-------|
| CA 2025 | 3 | - | 5 | 7 | 7 | - | 5 | - | 7 | 7 | 7 | 6 | 3 | - | 5 PI | 62+ |
| Biz 2025 | 3 | 5 | 5 | 5 | 5 | 5+4 | 5+3 | - | - | 5 | 5 | 4 | 3 | - | 1 Mobile | 63 |
| Uni 2025 | - | - | 3 | 3 | 3 | - | - | - | 3 | 3 | 3 | 3 | - | - | - | 21 |
| CA 2024 | 3 | - | - | 10 | 10 | 5 | - | 10 | - | 10 | 9 | 9 | - | - | - | 66 |
| Biz 2024 | 4 | 5 | 5 | 5 | 5 | 3+3 | - | 7 | - | 5 | 5 | 6 | - | 5 | - | 63 |
| Uni 2024 | 4 | - | 5 | 5 | 4 | - | - | - | - | 4 | 4 | 4 | - | 3 | - | 33+ |
| CA 2023 | 3 | - | - | 10 | 10 | 5 | 6 | 8 | - | 10 | 7 | 9 | - | - | - | 68 |
| Biz 2023 | 2+ | 2 | - | 5 | 3+ | 2+ SCADA | - | - | - | 3+ | 1+ | 2+ | - | 2+ | - | 30+ |
| Uni 2023 | - | - | - | 4 | 3 | - | - | - | - | 3 | 3 | 3 | - | 3 | - | 19 |

## Tips for CTF Competition

1. **Form a balanced team** - Cover web, crypto, pwn, reversing, forensics
2. **Solve easy challenges first** - Quick points build momentum
3. **Time-box hard challenges** - Don't spend 4 hours on one problem
4. **Read the challenge description carefully** - Hints are often in the name/description
5. **Keep detailed notes** - You'll need them for writeups
6. **Use Docker** - Many web challenges provide Dockerfiles, use them locally
7. **Check challenge files thoroughly** - Hidden files, metadata, comments
8. **Communicate with teammates** - Share findings, avoid duplicate work
