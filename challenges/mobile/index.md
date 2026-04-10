---
layout: default
title: "Mobile"
parent: Challenges
nav_order: 6
permalink: /challenges/mobile/
---

# Mobile Challenges

Writeups for HTB Mobile security challenges.

## Challenge Index

| Challenge | Difficulty | Platform | Techniques | Key Takeaway |
|-----------|-----------|----------|------------|--------------|
| [Don't Overreact](dont-overreact/) | Very Easy | Android | React Native, JavaScript Analysis | Extracting secrets from React Native bundles |
| [Cat](cat/) | Easy | Android | APK Reversing, Shared Preferences | Insecure local data storage |
| [APKey](apkey/) | Easy | Android | APK Decompilation, String Analysis | Hardcoded credentials in APK |
| [Manager](manager/) | Easy | Android | SQLite, Content Providers | Insecure content provider access |
| [Anchored](anchored/) | Medium | Android | SSL Pinning Bypass, Frida | Bypassing certificate pinning |
| [Pinned](pinned/) | Medium | Android | Certificate Pinning, MITM | Advanced pinning bypass with Frida |
| [SecureVault](secure-vault/) | Medium | Android | Root Detection, Encryption | Bypassing root detection |
| [SAW](saw/) | Hard | Android | Native Library, JNI | Reversing native Android libraries |
| [Pirated Playlist](pirated-playlist/) | Hard | iOS | iOS Binary, Keychain | iOS app reversing and keychain extraction |

## Analysis Workflow

### Static Analysis
```bash
# Decompile APK
apktool d app.apk -o output/
jadx app.apk -d output-java/

# Check for hardcoded secrets
grep -ri "api_key\|password\|secret\|token" output/

# Examine AndroidManifest.xml
cat output/AndroidManifest.xml
```

### Dynamic Analysis
```bash
# Install on emulator
adb install app.apk

# Frida - List processes
frida-ps -U

# Frida - Hook function
frida -U -l hook.js com.app.package

# SSL pinning bypass
frida -U --codeshare pcipolloni/universal-android-ssl-pinning-bypass-with-frida com.app.package

# Objection
objection -g com.app.package explore
objection> android sslpinning disable
objection> android root disable
```

## Tools

| Tool | Purpose |
|------|---------|
| jadx | APK to Java decompilation |
| apktool | APK resource decompilation |
| Frida | Dynamic instrumentation |
| Objection | Runtime mobile exploration |
| MobSF | Automated mobile analysis |
| adb | Android Debug Bridge |
| Genymotion | Android emulator |
| Burp Suite | Traffic interception |
