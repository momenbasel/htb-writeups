# Web Challenges

Writeups for HTB Web exploitation challenges.

## Challenge Index

| Challenge | Difficulty | Techniques | Key Takeaway |
|-----------|-----------|------------|--------------|
| [Trapped Source](trapped-source/) | Very Easy | JavaScript Analysis, Source Code Review | Client-side validation is not security |
| [Gunship](gunship/) | Very Easy | Prototype Pollution, AST Injection | Node.js prototype pollution to RCE |
| [Emdee Five for Life](emdee-five-for-life/) | Easy | Scripting, MD5, Automation | Race condition with time-based responses |
| [FreeLancer](freelancer/) | Easy | SQL Injection, Union-Based | Classic UNION injection in login form |
| [Templated](templated/) | Easy | SSTI, Jinja2 | Server-Side Template Injection in Flask |
| [Toxic](toxic/) | Easy | PHP Deserialization, LFI | Insecure deserialization via cookie |
| [Looking Glass](looking-glass/) | Easy | Command Injection | OS command injection through ping utility |
| [Neonify](neonify/) | Easy | Ruby SSTI, ERB | Template injection in Ruby/ERB |
| [Renderquest](renderquest/) | Easy | Go Template Injection | SSTI in Go templates |
| [C.O.P.](cop/) | Easy | Python Pickle Deserialization | Insecure deserialization in Python |
| [BlinkerFluids](blinkerfluids/) | Easy | Markdown XSS, SSRF | XSS through markdown rendering |
| [Weather App](weather-app/) | Easy | SSRF, SQLi | Chaining SSRF with SQL injection |
| [Juggling Facts](juggling-facts/) | Easy | PHP Type Juggling | PHP loose comparison bypass |
| [Phonebook](phonebook/) | Easy | LDAP Injection | LDAP injection in login form |
| [baby auth](baby-auth/) | Easy | JWT None Algorithm | JWT algorithm confusion attack |
| [baby nginxatsu](baby-nginxatsu/) | Easy | Nginx Misconfiguration | Path traversal via nginx alias misconfiguration |
| [Diogenes' Rage](diogenes-rage/) | Medium | Race Condition | Race condition in coupon redemption |
| [Mutation Lab](mutation-lab/) | Medium | CSS Injection, SSRF | Exfiltrating data via CSS injection |
| [Spookifier](spookifier/) | Medium | SSTI, Mako Templates | Server-Side Template Injection in Mako |
| [Intergalactic Post](intergalactic-post/) | Medium | XSS, SQL Injection | Chained XSS with SQLi |
| [HackBrawl](hackbrawl/) | Medium | GraphQL Injection | GraphQL introspection and injection |
| [PerfectGift](perfectgift/) | Medium | Prototype Pollution, RCE | JS prototype pollution to command execution |
| [ProxyAsAService](proxy-as-a-service/) | Medium | SSRF, URL Parser Differential | Exploiting URL parsing differences for SSRF |
| [SatelliteHijack](satellite-hijack/) | Medium | WebSocket, Command Injection | Command injection through WebSocket messages |
| [Magicom](magicom/) | Hard | Deserialization, PHP POP Chain | Complex PHP object injection chain |
| [Checkpointbots](checkpointbots/) | Hard | XS-Leaks, CSS Injection | Cross-origin information leakage |
| [CuteNews](cutenews/) | Hard | PHP RCE, Avatar Upload | File upload bypass to PHP execution |
| [Breaking Grad](breaking-grad/) | Hard | NodeJS Prototype Pollution | Deep prototype pollution in Node.js |

## Techniques Covered

### Server-Side
- SQL Injection (Union, Blind, Error-based)
- Server-Side Template Injection (Jinja2, Twig, Mako, ERB, Go)
- Server-Side Request Forgery (SSRF)
- Command Injection
- Deserialization (PHP, Python, Java, Node.js)
- LDAP Injection
- GraphQL Exploitation

### Client-Side
- Cross-Site Scripting (Reflected, Stored, DOM)
- CSS Injection
- Prototype Pollution
- JWT Attacks (None algorithm, Key confusion)

### Logic
- Race Conditions
- Type Juggling
- Authentication Bypass
- Access Control Issues
