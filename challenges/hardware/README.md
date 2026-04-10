# Hardware Challenges

Writeups for HTB Hardware hacking challenges.

## Challenge Index

| Challenge | Difficulty | Techniques | Key Takeaway |
|-----------|-----------|------------|--------------|
| [Debugging Interface](debugging-interface/) | Very Easy | UART, Serial | Reading data from UART interface |
| [Photon Lockdown](photon-lockdown/) | Very Easy | Firmware Extraction | Extracting secrets from firmware images |
| [BabyFirmware](baby-firmware/) | Easy | Firmware Analysis | Analyzing embedded firmware |
| [The Needle](the-needle/) | Easy | Firmware, String Analysis | Finding secrets in firmware blobs |
| [Timed Transmission](timed-transmission/) | Easy | Signal Analysis, Timing | Decoding timed signal transmissions |
| [Flash-ing Logs](flash-ing-logs/) | Medium | SPI Flash, Memory Dump | Analyzing SPI flash memory dumps |
| [Secret Codes](secret-codes/) | Medium | DTMF, Signal Decoding | Decoding dual-tone signals |
| [Industrial](industrial/) | Hard | SCADA, Modbus | Industrial protocol analysis |

## Key Concepts

| Protocol | Description | Tools |
|----------|-------------|-------|
| UART | Universal Asynchronous Receiver/Transmitter | minicom, screen, picocom |
| SPI | Serial Peripheral Interface | flashrom, Logic analyzer |
| I2C | Inter-Integrated Circuit | i2c-tools |
| JTAG | Joint Test Action Group | OpenOCD |
| Modbus | Industrial protocol | modbus-cli, pymodbus |

## Tools

| Tool | Purpose |
|------|---------|
| binwalk | Firmware extraction and analysis |
| firmware-mod-kit | Firmware modification |
| Saleae Logic | Logic analyzer software |
| PulseView/sigrok | Open-source signal analysis |
| baudrate.py | UART baud rate detection |
| flashrom | SPI flash reading/writing |
| OpenOCD | JTAG/SWD debugging |
| Audacity | Audio/signal analysis |
