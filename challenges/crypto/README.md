# Crypto Challenges

Writeups for HTB Cryptography challenges.

## Challenge Index

| Challenge | Difficulty | Techniques | Key Takeaway |
|-----------|-----------|------------|--------------|
| [BabyEncryption](baby-encryption/) | Very Easy | Custom Cipher, Modular Arithmetic | Simple substitution cipher |
| [The Last Dance](the-last-dance/) | Very Easy | ChaCha20, Nonce Reuse | Nonce reuse in stream ciphers |
| [Ancient Encodings](ancient-encodings/) | Very Easy | Base64, Hex, Encoding Chains | Multi-layer encoding |
| [Primary Knowledge](primary-knowledge/) | Easy | RSA, Small e | RSA with small public exponent |
| [XORed](xored/) | Easy | XOR, Known Plaintext | XOR cipher with known plaintext attack |
| [LunaCrypt](lunacrypt/) | Easy | Custom Cipher, Frequency Analysis | Breaking custom encryption |
| [SPG](spg/) | Easy | Weak RNG, Python Random | Predictable random number generator |
| [Infinite Descent](infinite-descent/) | Easy | RSA, Fermat Factorization | Factoring RSA with close primes |
| [RSAisEasy](rsa-is-easy/) | Easy | RSA, CRT Fault | RSA implementation flaws |
| [RoboEncryption](robo-encryption/) | Easy | Substitution Cipher | Automated cipher breaking |
| [LFSR Warmup](lfsr-warmup/) | Medium | Linear Feedback Shift Register | LFSR state recovery |
| [Revolving Door](revolving-door/) | Medium | AES-CBC, Bit Flipping | CBC bit-flipping attack |
| [Elliptic Labyrinth](elliptic-labyrinth/) | Medium | ECC, Invalid Curve Attack | Elliptic curve point validation |
| [How The Columns Have Turned](columns/) | Medium | Columnar Transposition | Classical cipher analysis |
| [Partial Tenacity](partial-tenacity/) | Medium | RSA, Partial Key Recovery | Recovering RSA key from partial information |
| [Inside The Matrix](inside-the-matrix/) | Medium | Lattice, LLL Algorithm | Lattice-based cryptanalysis |
| [Arranged](arranged/) | Hard | RSA, Coppersmith | RSA with known bits of p |
| [Crypto Apocalypse](crypto-apocalypse/) | Hard | Elliptic Curve, ECDSA | ECDSA nonce reuse attack |
| [Tsayaki](tsayaki/) | Hard | AES-GCM, Forbidden Attack | AES-GCM nonce reuse |

## Key Concepts

| Concept | Challenges | Tools |
|---------|-----------|-------|
| RSA Attacks | Primary Knowledge, Infinite Descent, RSAisEasy, Arranged | RsaCtfTool, SageMath |
| AES Attacks | Revolving Door, Tsayaki | CyberChef, PyCryptodome |
| ECC Attacks | Elliptic Labyrinth, Crypto Apocalypse | SageMath |
| Custom Ciphers | BabyEncryption, LunaCrypt, XORed | Python |
| PRNG Attacks | SPG, LFSR Warmup | z3, Python |
| Classical Ciphers | How The Columns Have Turned, RoboEncryption | dcode.fr, quipqiup |
| Lattice Attacks | Inside The Matrix | fpLLL, SageMath |

## Recommended Tools

- **SageMath** - Mathematical computation for RSA, ECC, lattice attacks
- **PyCryptodome** - Python crypto library
- **RsaCtfTool** - Automated RSA attack tool
- **CyberChef** - Encoding/decoding transformations
- **z3** - SMT solver for constraint-based crypto
- **hashcat/john** - Hash cracking
