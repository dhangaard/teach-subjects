# Glossary (English → Danish)

Grows with each lesson. Definitions follow Thomas's vocabulary (`sources/course-notes/thomas/it-security-vocabulary.md`) unless noted. Where Danish practitioners normally use the English word, the English word is listed first.

## Foundations (lesson 0001)

| English | Danish | Meaning |
|---|---|---|
| Asset | aktiv | Anything valuable that needs protection: data, accounts, services, reputation. |
| Vulnerability | sårbarhed | A weakness in software, configuration, design or procedure that a threat can exploit. A bug is only a vulnerability if it has a security consequence. |
| Threat | trussel | A circumstance or event that could harm an asset: deliberate, accidental or environmental. |
| Threat actor | trusselsaktør | A person or group that carries out or attempts harmful activity. |
| Exploit | exploit / udnyttelse | Code, input or actions that take advantage of a vulnerability. |
| Payload | payload | What an exploit delivers to produce its effect. |
| Risk | risiko | Likelihood × impact, in context. An introductory model, not a precise formula. |
| Residual risk | restrisiko | Risk that remains after controls are applied. |
| Security control | sikkerhedskontrol / sikringsforanstaltning | A measure that prevents, detects or helps recover from incidents. |
| Attack vector | angrebsvektor | One route by which an attacker reaches a target. |
| Attack surface | angrebsflade | All exposed entry points together. |
| Trust boundary | tillidsgrænse | Where data or actions cross between trust levels (e.g. React → API). |
| Confidentiality / Integrity / Availability | fortrolighed / integritet / tilgængelighed | The CIA triad. |
| Authentication | autentificering | "Who are you?" |
| Authorization | autorisation | "What are you allowed to do?" |
| Access control | adgangskontrol | Policies and mechanisms that enforce authorization. |
| CWE | CWE | Common Weakness Enumeration: a *type* of weakness (e.g. CWE-918 SSRF). |
| CVE | CVE | A *specific* publicly disclosed vulnerability in a product. |
| CVSS | CVSS | A technical severity score. Not a full measure of business risk. |
| Root cause / symptom | grundårsag / symptom | The 2025 list prefers categories named after causes. |
| Incidence rate | forekomst | % of tested apps with ≥1 CWE in a category (OWASP data factor). |
| Fail open | fail open / fejle åbent | On error, the system grants access instead of denying it (A10). |

## OWASP Top 10:2025 category names

| ID | English (use this) | Danish gloss |
|---|---|---|
| A01 | Broken Access Control | brudt adgangskontrol |
| A02 | Security Misconfiguration | sikkerhedsfejlkonfiguration |
| A03 | Software Supply Chain Failures | fejl i softwareforsyningskæden |
| A04 | Cryptographic Failures | kryptografiske fejl |
| A05 | Injection | injektion |
| A06 | Insecure Design | usikkert design |
| A07 | Authentication Failures | autentificeringsfejl |
| A08 | Software or Data Integrity Failures | fejl i software- eller dataintegritet |
| A09 | Security Logging & Alerting Failures | mangelfuld sikkerhedslogning og alarmering |
| A10 | Mishandling of Exceptional Conditions | mangelfuld håndtering af undtagelsestilstande |

The Danish glosses are descriptive translations, not official ones; OWASP publishes no Danish edition in `sources/`.
