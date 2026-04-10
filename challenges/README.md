# HackTheBox Challenges - Comprehensive Index

> Master index of all HackTheBox challenges organized by category with writeup links, difficulty ratings, and key techniques.

---

## Categories Overview

| Category | Count | Path | Key Skills |
|----------|-------|------|------------|
| [Web](#web-challenges) | 75+ | [`challenges/web/`](web/) | XSS, SQLi, SSTI, SSRF, Deserialization, JWT |
| [Crypto](#crypto-challenges) | 93+ | [`challenges/crypto/`](crypto/) | RSA, AES, ECC, Padding Oracle, Custom Ciphers |
| [Forensics](#forensics-challenges) | 33+ | [`challenges/forensics/`](forensics/) | Memory, Disk, Network, Log Analysis |
| [Reversing](#reversing-challenges) | 44+ | [`challenges/reversing/`](reversing/) | x86/x64, ARM, .NET, Java, Obfuscation |
| [Pwn](#pwn-challenges) | 61+ | [`challenges/pwn/`](pwn/) | Stack/Heap, ROP, Format String, Use-After-Free |
| [Mobile](#mobile-challenges) | 10+ | [`challenges/mobile/`](mobile/) | APK Reversing, Frida, Smali, Root Detection |
| [Hardware](#hardware-challenges) | 11+ | [`challenges/hardware/`](hardware/) | UART, SPI, I2C, Firmware, Signal Analysis |
| [OSINT](#osint-challenges) | 12+ | [`challenges/osint/`](osint/) | Geolocation, Social Media, Image Metadata |
| [Misc](#misc-challenges) | 35+ | [`challenges/misc/`](misc/) | Scripting, Logic, Encoding, Pyjail |
| [Stego](#steganography-challenges) | 12+ | [`challenges/stego/`](stego/) | LSB, Steghide, Audio, Image Analysis |
| [Blockchain](#blockchain-challenges) | 10+ | [`challenges/blockchain/`](blockchain/) | Solidity, Smart Contracts, DeFi |
| [AI/ML](#aiml-challenges) | 5+ | [`challenges/ai-ml/`](ai-ml/) | Adversarial ML, Model Exploitation, Prompt Injection |

---

## Web Challenges

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | Trapped Source | Very Easy | Client-Side Source Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 2 | Templated | Very Easy | Jinja2 SSTI | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 3 | Flag Command | Very Easy | API Exploitation, Command Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 4 | looking glass | Easy | SSTI, Command Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 5 | Gunship | Easy | Prototype Pollution, AST Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 6 | Toxic | Easy | PHP Deserialization, Log Poisoning | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 7 | sanitize | Easy | NoSQL Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 8 | baby auth | Easy | Authentication Bypass | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 9 | LoveTok | Easy | PHP Code Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 10 | TimeKORP | Easy | PHP Time Injection, Command Injection | [Medium - Rahul](https://medium.com/@rahulhoysala07/hack-the-box-web-challenge-timekorp-writeup-e03cc2f08d70) |
| 11 | KORP Terminal | Easy | SQL Injection, Hashcat | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 12 | Neonify | Easy | Ruby SSTI, Regex Bypass | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 13 | Slippy | Easy | Python Tar Slip, Path Traversal | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 14 | Full Stack Conf | Easy | Source Code Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 15 | CurlAsAService | Easy | SSRF, curl Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 16 | Wild Goose Hunt | Easy | NoSQL Injection, Regex Extraction | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 17 | E.Tree | Easy | XPath Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 18 | CandyVault | Easy | NoSQL Injection (MongoDB) | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 19 | SpookTastic | Easy | XSS, Bot Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 20 | Saturn | Easy | Path Traversal | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 21 | HTBank | Easy | Race Condition, Integer Overflow | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 22 | Watersnake | Easy | Java Deserialization, SnakeYAML | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 23 | Lazy Ballot | Easy | SQL Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 24 | emoji voting | Easy | SQL Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 25 | ProxyAsAService | Easy | SSRF, Proxy Bypass | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 26 | baby interdimensional internet | Easy | Python Code Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 27 | baby ninja jinja | Easy | Jinja2 SSTI | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 28 | baby CachedView | Easy | SSRF | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 29 | baby website rick | Easy | Source Code Analysis, Cookies | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 30 | baby todo or not todo | Easy | IDOR, API Abuse | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 31 | Intergalactic Post | Easy | SQL Injection (SQLite) | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 32 | BlinkerFluids | Easy | HTML Injection, RCE via PDF | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 33 | Juggling facts | Easy | PHP Type Juggling | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 34 | Spookifier | Easy | Jinja2/Mako SSTI | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 35 | Red Island | Easy | SSRF via Image URL | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 36 | Mutation Lab | Easy | CSS Injection, Session Forgery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 37 | Amidst Us | Easy | Python Pickle Deserialization | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 38 | Diogenes' Rage | Easy | Race Condition, Coupon Abuse | [MadDevs](https://maddevs.io/writeups/hackthebox-diogenes-rage/) |
| 39 | Weather App | Easy | SSRF, SQL Injection | [s-3ntinel](https://s-3ntinel.github.io/hackthebox/challenges/web/weather_app/weather_app.html) |
| 40 | Insomnia | Medium | Authentication Bypass, Logic Flaw | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 41 | jscalc | Medium | JavaScript Sandbox Escape | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 42 | OnlyHacks | Medium | SQL Injection, IDOR | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 43 | Breaking Bank | Medium | JWT Exploitation, Race Condition | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 44 | wafwaf | Medium | WAF Bypass, SQL Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 45 | GhostlyTemplates | Medium | Go Template Injection, SSTI | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 46 | PumpkinSpice | Medium | SSTI, Python Template Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 47 | Spellbound Servants | Medium | Deserialization, PHP Object Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 48 | HauntMart | Medium | SSRF, Internal Service Access | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 49 | 0xBOverchunked | Medium | HTTP Chunked Encoding, SQLi WAF Bypass | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 50 | Percetron | Medium | ML Model Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 51 | Testimonial | Medium | gRPC Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 52 | Horror Feeds | Medium | SQL Injection, XSS | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 53 | baby nginxatsu | Medium | Nginx Misconfiguration, LFI | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 54 | Spiky Tamagotchi | Medium | SQL Injection, Session Hijack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 55 | Kryptos Support | Medium | XSS, Cookie Stealing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 56 | baby breaking grad | Medium | Prototype Pollution | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 57 | Orbital | Medium | SQL Injection, LFI | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 58 | Passman | Medium | GraphQL Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 59 | BatchCraft Potions | Medium | Batch Script Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 60 | baby WAFfles order | Medium | XXE Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 61 | Cursed Secret Party | Medium | Stored XSS, CSP Bypass | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 62 | baby BoneChewerCon | Medium | SSTI, Sandbox Escape | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 63 | RenderQuest | Medium | Go SSTI, Template Injection | [Medium - Tanish](https://medium.com/@tanish.saxena26/hackthebox-renderquest-cf6c493d7b83) |
| 64 | Labyrinth Linguist | Medium | Apache Velocity SSTI, CVE-2020-13936 | [Medium - Rahul](https://medium.com/@rahulhoysala07/hack-the-box-web-challenge-labyrinth-linguist-a67d5005abe0) |
| 65 | CDNio | Hard | CDN Bypass, Cache Poisoning | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 66 | NeoVault | Hard | Neo4j Injection, Cypher Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 67 | PDFy | Hard | PDF Generation SSRF | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 68 | AbuseHumanDB | Hard | XSS Chain, Bot Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 69 | ExpressionalRebel | Hard | Regex ReDoS, Expression Injection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 70 | TrapTrack | Hard | Gopher SSRF, Redis Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 71 | Spybug | Hard | API Key Leak, Stored XSS | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 72 | Didactic Octo Paddles | Hard | JWT None Algorithm, SSTI | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 73 | The Magic Informer | Hard | SQL Injection, Prototype Pollution | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 74 | Letter Dispair | Hard | XSS, SSRF Chain | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |
| 75 | Userland City | Hard | Complex Multi-Stage Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/web/) |

---

## Crypto Challenges

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | Ancient Encodings | Very Easy | Base Encoding, Hex Encoding | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 2 | Weak RSA | Very Easy | RSA Small Key, Factorization | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 3 | Android-in-the-middle | Very Easy | Diffie-Hellman MITM | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 4 | sekur julius | Easy | Caesar Cipher Variant | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 5 | Classic, yet complicated! | Easy | Classical Cipher, Substitution | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 6 | Jenny From The Block | Easy | Hash Length Extension, Block Cipher | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 7 | Down the Rabinhole | Easy | Rabin Cryptosystem | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 8 | How The Columns Have Turned | Easy | Columnar Transposition | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 9 | Dynastic | Easy | Custom Cipher, Python Scripting | [Medium - Rahul](https://medium.com/@rahulhoysala07/hack-the-box-crypto-challenge-dynastic-writeup-0e03ba6cd432) |
| 10 | The Three-Eyed Oracle | Easy | AES ECB Oracle Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 11 | Space Pirates | Easy | Shamir's Secret Sharing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 12 | One Step Closer | Easy | RSA Related Message Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 13 | Infinite Descent | Easy | RSA, Continued Fractions | [GitHub](https://github.com/tilznit/htb_crypto_Infinite_Descent) |
| 14 | Brainy's Cipher | Easy | Custom Cipher Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 15 | Gonna-Lift-Em-All | Easy | Diffie-Hellman Key Recovery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 16 | SPG | Easy | Secure Password Generator Weakness | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 17 | Symbols | Easy | Symbol Substitution Cipher | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 18 | I'm gRoot | Easy | Merkle Tree, Hash Collision | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 19 | Iced Tea | Easy | TEA Cipher, Block Cipher | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 20 | Perfect Synchronization | Easy | AES ECB, Frequency Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 21 | Flippin Bank | Medium | AES CBC Bit Flipping | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 22 | Initialization | Medium | AES Initialization Vector Leak | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 23 | MSS | Medium | Secret Sharing Scheme Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 24 | Mayday Mayday | Medium | RSA CRT Fault Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 25 | Roulette | Medium | PRNG Prediction | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 26 | TurboCipher | Medium | Custom Block Cipher Weakness | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 27 | CryptoConundrum | Medium | Multi-Stage Decryption | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 28 | BFD56 | Medium | Blowfish Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 29 | RLotto | Medium | PRNG Seed Recovery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 30 | Zombie Rolled | Medium | XOR + Custom Cipher | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 31 | Interception | Medium | MITM Key Exchange | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 32 | Vitrium Stash | Medium | Custom Encryption Scheme | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 33 | Rookie Mistake | Medium | RSA Common Factor Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 34 | Partial Tenacity | Medium | RSA Partial Key Recovery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 35 | Arranged | Medium | RSA Lattice Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 36 | Tsayaki | Medium | AES CTR Nonce Reuse | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 37 | Waiting List | Medium | Digital Signature Forgery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 38 | Composition | Medium | Mathematical Composition | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 39 | Fibopadcci | Medium | Fibonacci Padding Oracle | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 40 | I know Mag1k | Medium | Magic Number Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 41 | Homomurphy's Law | Medium | Homomorphic Encryption Weakness | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 42 | signup | Medium | Signature Forgery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 43 | Oracle Leaks | Medium | Padding Oracle Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 44 | Lost Modulus | Medium | RSA Modulus Recovery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 45 | Living with Elegance | Medium | Elliptic Curve Cryptography | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 46 | Blessed | Medium | RSA Oracle Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 47 | Quadratic Points | Medium | ECC Quadratic Residue | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 48 | Not that random | Medium | LCG/PRNG State Recovery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 49 | Bloom Bloom | Medium | Bloom Filter Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 50 | Protein Cookies 2 | Medium | Cookie Crypto Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 51 | Secure Signing | Medium | DSA/ECDSA Nonce Reuse | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 52 | Clutch | Medium | Lattice-Based Crypto Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 53 | baby quick maffs | Medium | Simplified Math Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 54 | binary basis | Medium | Binary Number Theory | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 55 | brevi moduli | Medium | Short RSA Modulus | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 56 | alphascii clashing | Medium | ASCII Hash Collision | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 57 | sugar free candies | Medium | Weak Custom Cipher | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 58 | Hash the Filesystem | Medium | Filesystem Hash Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 59 | Find Marher's Secret | Medium | Mathematical Secret Recovery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 60 | Lost Modulus Again | Hard | RSA Advanced Recovery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 61 | Digital Safety Annex | Hard | Digital Signature Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 62 | Traces | Hard | Side-Channel Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 63 | Twin Oracles | Hard | Dual Oracle Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 64 | Verilicious | Hard | Verification Bypass | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 65 | Copperbox | Hard | Coppersmith's Attack (RSA) | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 66 | Mind In The Clouds | Hard | Cloud Crypto Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 67 | secure source | Hard | Source Code Crypto Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 68 | read before you sign | Hard | Signature Scheme Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 69 | hybrid unifier | Hard | Hybrid Encryption Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 70 | Signing Factory | Hard | Signature Factory Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 71 | Converging Visions | Hard | ECC Point Convergence | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 72 | Biased Heritage | Hard | Biased Nonce Attack (HNP) | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 73 | Elliptic Labyrinth | Hard | ECC Invalid Curve Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 74 | Colliding Heritage | Hard | Hash Collision Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 75 | Inside The Matrix | Hard | Matrix-Based Crypto | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 76 | Multipage Recyclings | Hard | AES Key Schedule Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 77 | TwoForOne | Hard | Signature Forgery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 78 | LunaCrypt | Hard | Custom Crypto Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 79 | 400curves | Hard | ECC Multi-Curve Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 80 | RsaCtfTool | Hard | RSA Multi-Attack Automation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 81 | Nuclear Sale | Hard | Nuclear-Themed Crypto | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 82 | Optimus Prime | Hard | Large Prime Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 83 | AbraCryptabra | Hard | Multi-Layer Decryption | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 84 | quick maffs | Hard | Fast Math Crypto Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 85 | Ebola Virus | Hard | Virus-Themed Crypto | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 86 | ElElGamal | Hard | ElGamal Signature Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 87 | Infinite Knapsack | Hard | Knapsack Problem Attack | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 88 | AESWCM | Hard | AES Weak Counter Mode | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 89 | Bank-er-smith | Hard | Banking Crypto Flaw | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 90 | AHS512 | Hard | Custom Hash Function | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 91 | Spooky RSA | Hard | Multi-Prime RSA | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 92 | Fast Carmichael | Hard | Carmichael Number Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |
| 93 | BBGun06 | Hard | BB84 Quantum Crypto | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/crypto/) |

---

## Forensics Challenges

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | Illumination | Very Easy | Git History Analysis, Token Recovery | [Medium - Nouf](https://enaljammaz.medium.com/hackthebox-forensics-challenge-illumination-walkthrough-f6b032b01211) |
| 2 | An unusual sighting | Very Easy | SSH/Bash Log Analysis | [Medium - Rahul](https://medium.com/@rahulhoysala07/hack-the-box-forensics-an-unusual-sighting-writeup-ba20a80a09db) |
| 3 | Urgent | Very Easy | Phishing Email Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 4 | Alien Cradle | Very Easy | PowerShell Script Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 5 | Extraterrestrial Persistence | Very Easy | Cron Job / Persistence Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 6 | Wrong Spooky Season | Easy | PCAP Analysis, Reverse Shell Detection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 7 | Halloween Invitation | Easy | Macro Analysis, VBA Malware | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 8 | POOF | Easy | Log Analysis, Incident Timeline | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 9 | Downgrade | Easy | Windows Event Log Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 10 | Fake News | Easy | Web Forensics, Source Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 11 | Lure | Easy | Malicious Document Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 12 | Chase | Easy | PCAP Analysis, Wireshark | [Medium - Josh](https://0xect0.medium.com/hackthebox-chase-forensics-challenge-writeup-eebf72d6051f) |
| 13 | Phreaky | Easy | PCAP Analysis, Data Extraction | [Medium - Rahul](https://medium.com/@rahulhoysala07/hack-the-box-forensics-phreaky-writeup-9fde5c245f75) |
| 14 | Export | Easy | Memory Forensics (.raw), Volatility | [Medium - Josh](https://0xect0.medium.com/hackthebox-export-forensics-challenge-writeup-1cbb6c0be4fd) |
| 15 | Insider | Easy | Linux Filesystem Forensics | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 16 | Free Services | Easy | Malicious Email Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 17 | Packet Cyclone | Easy | PCAP + Sigma Rules | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 18 | Automation | Easy | PowerShell Script Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 19 | Keep Tryin' | Easy | Email Forensics, MIME Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 20 | Perseverance | Easy | WMI Persistence Detection | [HTB Blog](https://www.hackthebox.com/blog/perseverance-biz-ctf-2022-forensics-writeup) |
| 21 | Reminiscent | Easy | Memory Forensics, Volatility | [DFIR Blog](https://www.thedigitalforensics.com/blog/hack-the-box-reminiscent) |
| 22 | MarketDump | Medium | Network Forensics, Data Leak | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 23 | Relic Maps | Medium | Malicious Macro, HTA Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 24 | Event Horizon | Medium | Windows .evtx Analysis | [Medium - SecurityNoodle](https://securitynoodle.medium.com/hackthebox-event-horizon-forensics-challenge-writeup-b32839a3307d) |
| 25 | No Place To Hide | Medium | Network Traffic Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 26 | Logger | Medium | Keylogger Forensics | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 27 | Peel Back The Layers | Medium | Docker Image Forensics | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 28 | Deadly Arthropod | Medium | C2 Traffic Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 29 | Artifact Of Dangerous Sighting | Medium | Windows Artifact Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 30 | Valhalloween | Hard | Complex Incident Forensics | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 31 | Interstellar C2 | Hard | C2 Communication Decryption | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 32 | Scripts and Formulas | Hard | Excel Macro Forensics | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |
| 33 | Red Miners | Hard | Cryptominer Forensics | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/forensics/) |

---

## Reversing Challenges

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | Baby RE | Very Easy | Basic x64 Disassembly | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 2 | WIDE | Very Easy | Wide String Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 3 | Find The Easy Pass | Very Easy | .NET Decompilation | [SecJuice](https://www.secjuice.com/htb-find-the-secret-flag-reversing-challenge/) |
| 4 | Impossible Password | Very Easy | String Comparison Bypass | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 5 | Shattered Tablet | Very Easy | Basic Static Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 6 | LootStash | Very Easy | Basic String Analysis | [Medium - Rahul](https://medium.com/@rahulhoysala07/hack-the-box-reversing-challenge-lootstash-93885622734e) |
| 7 | Rebuilding | Easy | Binary Reconstruction | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 8 | Teleport | Easy | Binary Protocol Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 9 | Snakecode | Easy | Python Bytecode Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 10 | You Cant C Me | Easy | C Binary Obfuscation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 11 | Baby Crypt | Easy | Basic Crypto Reversing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 12 | Hunting License | Easy | License Key Reversing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 13 | Ouija | Easy | Ouija-Themed Binary | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 14 | Secured Transfer | Easy | Protocol Reverse Engineering | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 15 | Ransom | Easy | Ransomware Key Recovery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 16 | Anti Flag | Easy | Anti-Debug Bypass | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 17 | Potion Master | Easy | Game Logic Reversing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 18 | Curse Breaker | Easy | Encryption Algorithm Reversing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 19 | SpellBrewery | Easy | String Array Decoding | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 20 | Bypass | Easy | .NET Auth Bypass (dnSpy) | [Medium](https://medium.com/swlh/hack-the-boxdwriteup-rev-1-a94282cb0c63) |
| 21 | Exatlon | Easy | UPX Packed Binary | [Medium - bigkahuna](https://medium.com/@sturu/hackthebox-exatlon-reversing-challenge-writeup-a98243ed5c36) |
| 22 | Spooky License | Easy | Angr Symbolic Execution | [Medium - 0x00](https://nier0x00.medium.com/spooky-license-reversing-challenge-hackthebox-writeup-d0cd20459f29) |
| 23 | Up a Stream | Easy | Data Stream Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 24 | RiseFromTheDead | Easy | Zombie-Themed Reversing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 25 | Snake | Easy | Python Game Reversing | [Medium - Tarun](https://medium.com/@Tarun.N/htb-snake-challenge-walk-through-for-noobs-2475ea7a38ab) |
| 26 | Hissss | Medium | Python Compiled Binary (.pyc) | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 27 | Headache | Medium | Anti-Analysis Techniques | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 28 | The Vault | Medium | Multi-Layer Protection | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 29 | IRCware | Medium | IRC Bot Reversing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 30 | Eat the Cake! | Medium | Obfuscated Binary | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 31 | Alien Saboteaur | Medium | Custom VM Bytecode | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 32 | ChromeMiner | Medium | Browser Extension Reversing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 33 | Sekure Decrypt | Medium | Decryption Routine Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 34 | RetoRetro | Medium | Retro Binary Analysis | [Medium - f0xtty](https://medium.com/@f0xtty/en-hackthebox-retoretro-reversing-challenge-writeup-9db06d6ace2e) |
| 35 | Encryption Bot | Medium | Bot Logic Reversing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 36 | Tear or Dear | Medium | Conditional Logic Reversing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 37 | FlagCasino | Medium | PRNG Seed Recovery | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 38 | Golfer - Part 1 | Medium | Code Golf Reversing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 39 | SpookyPass | Hard | Password Verification Bypass | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 40 | Graverobber | Hard | Complex Binary Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 41 | CryptOfTheUndead | Hard | Encryption Algorithm Reversing | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 42 | Hubbub | Hard | Complex Obfuscation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 43 | BinCrypt Breaker | Hard | Custom Crypto Binary | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |
| 44 | ReRop | Hard | ROP Chain Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/reversing/) |

---

## Pwn Challenges

Full list of 61 pwn challenges: see [pwn/README.md](pwn/README.md) or browse [7Rocky Pwn Index](https://7rocky.github.io/en/ctf/htb-challenges/pwn/).

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | Getting Started | Very Easy | Stack Buffer Overflow Basics | [Medium - Rahul](https://medium.com/@rahulhoysala07/hack-the-box-pwn-challenge-getting-started-54acc706afa7) |
| 2 | Questionnaire | Very Easy | Binary Security Quiz | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/pwn/) |
| 3 | Space pirate: Entrypoint | Very Easy | Buffer Overflow, Basic ROP | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/pwn/) |
| 4 | Space pirate: Going Deeper | Very Easy | Stack Overflow, ROP | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/pwn/) |
| 5 | Vault-breaker | Very Easy | Basic Binary Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/pwn/) |
| 6 | Reg | Easy | Buffer Overflow, ret2win | [Blackfell](https://blackfell.net/technical/labs/HTB-pwn-reg/) |
| 7 | Jeeves | Easy | Format String, ret2win | [JayBailey](https://jaybailey216.com/pwn-challenge-jeeves/) |
| 8 | Void | Easy | ret2libc, Stack Pivot | [Medium - Rahul](https://medium.com/@rahulhoysala07/hack-the-box-pwn-challenge-void-writeup-cee6bdb6c07d) |
| 9 | Ropme | Easy | Return-Oriented Programming | [Medium - Gabriel](https://medium.com/@gabriel.pirjolescu/pwn-hack-the-box-ropme-write-up-b40179cf5573) |
| 10 | Labyrinth | Easy | Stack Overflow, Maze Logic | [Medium - Rahul](https://medium.com/@rahulhoysala07/hack-the-box-pwn-challenge-labyrinth-1ee7c0305713) |
| 11-22 | Fleet Management, Blacksmith, HTB Console, Entity, Leet Test, Format, Bat Computer, Space pirate: Retribution, No Return, Spooky Time, Shooting star, Great Old Talisman | Easy | Various Stack/Format Exploits | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/pwn/) |
| 23-41 | Hellhound, Old Bridge, Trick or Deal, Space, Spellbook, Sacred Scrolls: Revenge, Optimistic, PwnShop, CRSid, Finale, Nightmare, Math Door, Control Room, FileStorage, Auth-or-out, echoland, Robot Factory, Bon-nie-appetit, knote | Medium | Heap/Format String/Advanced | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/pwn/) |
| 42-60 | Zombiedote, Zombienator, Antidote, Dragon Army, Sound of Silence, Maze of Mist, Kernel Adventures: Part 1, Lesson, Nowhere to go, Oxidized ROP, Pixel Audio, Hunting, Regularity, Picture Magic, Sick ROP, Dead or Alive, Fake Snake, Ancient Interface | Hard | Heap/Kernel/Advanced ROP | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/pwn/) |
| 61 | Dream Diary: Chapter 3 | Insane | tcache Poisoning, Heap Feng Shui | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/pwn/) |

---

## Mobile Challenges

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | APKey | Very Easy | APK Analysis, Smali Code, JADX | [Medium - 0xk3r0](https://medium.com/@0xk3r0/hackthebox-apkey-mobile-challenge-6e3cf5647c2d) |
| 2 | APKrypt | Easy | APK Decompilation, Key Recovery | [CSbyGB GitBook](https://csbygb.gitbook.io/pentips/writeups/htbtracks/htb-intro-to-android-exploitation-track) |
| 3 | Don't Overreact | Easy | React Native Reversing, Hardcoded Secrets | [CSbyGB GitBook](https://csbygb.gitbook.io/pentips/writeups/htbtracks/htb-intro-to-android-exploitation-track) |
| 4 | Cat | Easy | Android Backup (.ab) Analysis | [Medium - Danish](https://danishzia.medium.com/hack-the-box-cat-challenge-write-up-914e0877f68d) |
| 5 | SeeTheSharpFlag | Easy | Xamarin/.NET Mobile Reversing | [CSbyGB GitBook](https://csbygb.gitbook.io/pentips/writeups/htbtracks/htb-intro-to-android-exploitation-track) |
| 6 | SAW | Easy | Android Smali Patching | [Hackplayers](https://github.com/Hackplayers/hackthebox-writeups/blob/master/challenges/mobile/htb-mobile-saw-writeup.pdf) |
| 7 | Pinned | Medium | Certificate Pinning Bypass, Frida | [CSbyGB GitBook](https://csbygb.gitbook.io/pentips/writeups/htbtracks/htb-intro-to-android-exploitation-track) |
| 8 | Manager | Medium | Android Password Manager Vuln | [Medium - xProtagonist](https://medium.com/@xprotagonist_/manager-hackthebox-intro-to-android-exploitation-track-by-xprotagonist-7e1ac22fd79a) |
| 9 | Anchored | Medium | Android App Anchoring Bypass | [CSbyGB GitBook](https://csbygb.gitbook.io/pentips/writeups/htbtracks/htb-intro-to-android-exploitation-track) |
| 10 | Cryptohorrific | Medium | Mobile Crypto Exploitation | [Medium - Sanket](https://medium.com/@sanketkumkar77/cryptohorrific-hack-the-box-challenge-writeup-857caf1def0f) |

---

## Hardware Challenges

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | Photon Lockdown | Very Easy | Firmware Extraction, Binwalk | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/hardware/) |
| 2 | HM74 | Very Easy | Hamming Error-Correcting Codes | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/hardware/) |
| 3 | Gawk | Easy | Logic Analyzer, SPI Protocol | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/hardware/) |
| 4 | Unique | Easy | UART Communication Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/hardware/) |
| 5 | Walkie Hackie | Easy | Radio Frequency Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/hardware/) |
| 6 | Secure Digital | Easy | SD Card / SPI Protocol Decode | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/hardware/) |
| 7 | Mini Line | Medium | Line Protocol Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/hardware/) |
| 8 | VHDLock | Medium | VHDL Hardware Description Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/hardware/) |
| 9 | Debugging Interface | Easy | UART Debugging, Serial Comms | [Medium - Justus](https://justus-njogu.medium.com/debugging-interface-challenge-hack-the-box-walk-through-e529c467d3da) |
| 10 | Debug | Easy | Hardware Debug Interface | [Medium - Rahul](https://medium.com/@rahulhoysala07/hack-the-box-hardware-challenge-debug-writeup-3889089897ef) |
| 11 | The Needle | Easy | Linux Firmware Analysis | [Motasem Notes](http://motasem-notes.net/hardware-hacking-p3-linux-firmware-analysis-hackthebox-the-needle/) |

---

## OSINT Challenges

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | Easy Phish | Very Easy | DNS, SPF/DMARC Records | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/osint/) |
| 2 | Infiltration | Easy | LinkedIn, Instagram Recon | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/osint/) |
| 3 | Missing in Action | Easy | LinkedIn, Twitter, Google Dorks | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/osint/) |
| 4 | Money Flowz | Medium | Reddit, Ropsten Ethereum Chain | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/osint/) |
| 5 | Monstrosity | Medium | Twitter API, Geolocation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/osint/) |
| 6 | Various Easy OSINT | Easy | Multi-Source OSINT | [Medium - Vinayak](https://vinayakagrawal95.medium.com/easy-osint-challenges-hack-the-box-3bb3da3f186d) |
| 7 | Various Medium OSINT | Medium | Advanced OSINT Techniques | [Medium - Vinayak](https://vinayakagrawal95.medium.com/medium-osint-challenges-writeup-hack-the-box-a170fa2b4fa) |
| 8-14 | Cyber Apocalypse 2025 OSINT (7 challenges) | Various | Geolocation, Social Media, Public Records | [Medium - Carson](https://blog.carsonshaffer.me/hack-the-box-cyber-apocalypse-ctf-2025-osint-writeup-c5ab878b700c) |

---

## Misc Challenges

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | Emdee five for life | Very Easy | MD5 Hashing, Python Scripting | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 2 | The secret of a Queen | Very Easy | Mary Queen of Scots Cipher | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 3 | Compressor | Easy | Compression/Archive Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 4 | 0ld is g0ld | Easy | PDF Password Cracking | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 5 | fs0ciety | Easy | Mr. Robot Themed, File Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 6 | Da Vinci | Easy | Steganography + Logic | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 7 | Hackerman | Easy | Strings, Basic Steg | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 8 | BitsNBytes | Easy | Binary Analysis, Image Comparison | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 9 | Art | Easy | ASCII Art Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 10 | Milkshake | Easy | Data Transformation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 11 | M0rsarchive | Easy | Morse Code, Nested Archives | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 12 | Pusheen Loves Graphs | Easy | Graph Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 13 | misDIRection | Easy | Directory Structure Analysis | [Medium - Nouf](https://enaljammaz.medium.com/hackthebox-misc-challenge-misdirection-walkthrough-4ec8b7c4cac5) |
| 14 | Chainsmoker | Easy | Chain Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 15 | Hidden Path | Easy | Node.js Source Code Analysis | [MadDevs](https://maddevs.io/writeups/hackthebox-hidden-path/) |
| 16 | Eternal Loop | Medium | Infinite Loop/Archive Puzzle | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 17 | ExploitedStream | Medium | Stream Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 18 | Tree of Danger | Medium | Tree Structure Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 19 | Path of Survival | Medium | Pathfinding Algorithm | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 20 | Pickle Panic | Medium | Python Pickle Deserialization | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 21 | Query | Medium | Database Query Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 22 | Type Exception | Medium | Type System Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 23 | Canvas | Medium | Canvas Drawing Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 24 | Fentastic Moves | Medium | Chess/Game Logic | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 25 | Locked Away | Medium | Lock Picking Logic | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 26 | Branching Tactics | Medium | Git Branch Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 27 | A Nightmare On Math Street | Medium | Math-Based Scripting | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 28 | SecretRezipe | Hard | Recipe-Themed Complex Logic | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 29 | Computational Recruiting | Hard | Algorithm Challenge | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 30 | Man In The Middle | Hard | MITM Network Analysis | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 31 | Replacement | Hard | Data Replacement Logic | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 32 | Deterministic | Hard | Deterministic Computation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 33 | Triangles | Hard | Geometric Math Challenge | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 34 | Bashic Calculator | Hard | Bash Scripting Exploitation | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |
| 35 | Quantum Artifact | Hard | Quantum-Themed Challenge | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/misc/) |

---

## Steganography Challenges

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | Forest | Easy | Image Steg, Steghide, Brightness | [z00mik GitHub](https://github.com/z00mik/Stego-Challenges-HackTheBox-Write-Ups) |
| 2 | Digital Cube | Easy | Image Analysis, Pixel Manipulation | [z00mik GitHub](https://github.com/z00mik/Stego-Challenges-HackTheBox-Write-Ups) |
| 3 | Retro | Easy | Retro Image Steg | [z00mik GitHub](https://github.com/z00mik/Stego-Challenges-HackTheBox-Write-Ups) |
| 4 | Pusheen Loves Graphs | Easy | Graph-Based Steganography | [z00mik GitHub](https://github.com/z00mik/Stego-Challenges-HackTheBox-Write-Ups) |
| 5 | Hackerman | Easy | Steghide, rockyou Wordlist | [Art0fHack](https://art0fhack.blogspot.com/2018/08/stego-hackerman-htb.html) |
| 6 | Widescreen | Easy | Steg Solver | [Hackplayers](https://github.com/Hackplayers/hackthebox-writeups/tree/master/challenges/stego) |
| 7 | Image Processing 101 | Easy | Basic Image Processing | [HTB Forum](https://forum.hackthebox.com/t/stego-image-processing-101/1940) |
| 8 | Unprintable | Medium | Non-Printable Characters | [z00mik GitHub](https://github.com/z00mik/Stego-Challenges-HackTheBox-Write-Ups) |
| 9 | Not Art | Medium | Art-Based Steganography | [z00mik GitHub](https://github.com/z00mik/Stego-Challenges-HackTheBox-Write-Ups) |
| 10 | BitsNBytes | Medium | Image Comparison, ImageMagick | [HTB Forum](https://forum.hackthebox.com/t/stego-challenge-bitsnbytes-write-up-by-alamot/1636) |
| 11 | Massacre | Hard | Complex Multi-Layer Steg | [z00mik GitHub](https://github.com/z00mik/Stego-Challenges-HackTheBox-Write-Ups) |
| 12 | Senseless Behaviour | Hard | Behavioral Analysis Steg | [z00mik GitHub](https://github.com/z00mik/Stego-Challenges-HackTheBox-Write-Ups) |

---

## Blockchain Challenges

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | Survival of the Fittest | Very Easy | Smart Contract Interaction, cast | [InfoSec Writeups](https://infosecwriteups.com/hackthebox-survival-of-the-fittest-blockchain-challenge-writeup-e7302c787d20) |
| 2 | Russian Roulette | Very Easy | Block Hash Manipulation | [Forbytten](https://forbytten.gitlab.io/blog/htb-cyber-apocalypse-writeups-2024/russian-roulette/) |
| 3 | Lucky Faucet | Easy | Integer Overflow, Solidity | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/blockchain/) |
| 4 | Funds Secured | Easy | Incorrect Parameter Verification | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/blockchain/) |
| 5 | Magic Vault | Easy | Private Storage Read, Block Mechanics | [Medium - 0x-professor](https://0x-professor.medium.com/magic-vault-hackthebox-blockchain-challenge-writeup-078f6c1ed87d) |
| 6 | Distract and Destroy | Easy | Smart Contract Logic Exploit | [GitHub - KanakSasak](https://github.com/KanakSasak/HTB-Blockchain) |
| 7 | Confidentiality | Medium | ERC-721, ECDSA Signature Malleability | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/blockchain/) |
| 8 | Honor Among Thieves | Medium | Multi-Contract Exploitation | [GitHub - KanakSasak](https://github.com/KanakSasak/HTB-Blockchain) |
| 9 | Art of Deception | Medium | Smart Contract Deception | [Medium - Nikhil](https://medium.com/@nikhilmemane09/htb-cyber-apocalypse-2023-owning-smart-contracts-art-of-deception-f3348897d5c5) |
| 10 | University CTF 2024 Blockchain | Various | Multiple Smart Contract Challenges | [Medium - Nafiz](https://medium.com/@muhammadnafiz2017/hack-the-box-university-ctf-2024-blockchain-challenges-writeup-1787e97f0fff) |

---

## AI/ML Challenges

| # | Challenge | Difficulty | Key Techniques | Writeup |
|---|-----------|-----------|----------------|---------|
| 1 | Sigma Technology | Easy | Adversarial Machine Learning | [7Rocky](https://7rocky.github.io/en/ctf/htb-challenges/ai---ml/) |
| 2 | AI Space | Easy | Multidimensional Scaling, Data Analysis | [1337Sheets](https://www.1337sheets.com/p/hack-the-box-challenge-ai-space-ml-writeup) |
| 3 | Prometheon | Medium | Multi-Stage Prompt Injection, LLM Bypass | [Medium - Paragbhosale](https://medium.com/@paragbhosale9440/htb-prometheon-exploiting-alignment-boundaries-in-ai-via-prompt-injection-5a195e16a256) |
| 4 | External Affairs | Medium | AI Travel Screening Bypass, Prompt Injection | [hack-lab-256](https://hack-lab-256.com/en/ai-llm-prompt-injection/1680/) |
| 5 | FullHouse (Lab) | Medium | AI Bypass and Exploitation | [HTB Blog](https://www.hackthebox.com/blog/fullhouse-ai-lab) |

---

## Key Writeup Collections

| Source | URL | Coverage |
|--------|-----|----------|
| 7Rocky | [7rocky.github.io](https://7rocky.github.io/en/ctf/htb-challenges/) | 350+ challenges across all categories |
| Hackplayers | [GitHub](https://github.com/Hackplayers/hackthebox-writeups) | Web, Crypto, Forensics, Mobile, Stego, OSINT |
| Rishitsaiya | [GitHub](https://github.com/rishitsaiya/HackTheBox-Challenges) | Crypto, Web, OSINT, Forensics, Reversing |
| z00mik | [GitHub](https://github.com/z00mik/Stego-Challenges-HackTheBox-Write-Ups) | 8 Stego challenges |
| KanakSasak | [GitHub](https://github.com/KanakSasak/HTB-Blockchain) | Blockchain challenges |
| CSbyGB | [GitBook](https://csbygb.gitbook.io/pentips/writeups/htbtracks/htb-intro-to-android-exploitation-track) | Mobile/Android challenges |
| Esther7171 | [GitHub](https://github.com/Esther7171/HackTheBox-Writeups-Walkthroughs) | Multi-category writeups |
| 0xRick | [Blog](https://0xrick.github.io/categories/) | Multi-category writeups |
| zweilosec | [GitBook](https://zweilosec.gitbook.io/htb-writeups) | Machines and Challenges |

## Difficulty Distribution

- **Very Easy** - Great for absolute beginners, teaches fundamentals
- **Easy** - Requires basic understanding of the category
- **Medium** - Solid understanding and creative thinking needed
- **Hard** - Competition-level challenges with complex attack chains
- **Insane** - Expert-level, often requiring novel techniques
