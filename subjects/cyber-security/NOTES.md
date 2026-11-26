# Teaching notes

## Lesson plan, phase 1 (agreed 2026-11-26)

Deep-first: A01/A07 before the breadth pass, because the report depends on them. Target is to finish by mid-December 2026; exam is early to mid January 2027. About 45 min per lesson, about 5 lessons a week.

| # | Topic | Status |
|---|---|---|
| 0001 | Orientation: method, vocabulary, four-part answer | built |
| 0002 | A01 concepts (IDOR, privilege escalation, force browsing, CORS, JWT tampering, SSRF) | |
| 0003 | A01 in Sheet Herder (filters vs. ownership, client vs. server, permissions matrix) | |
| 0004 | A07 concepts | |
| 0005 | A07 in Sheet Herder | |
| 0006 | A04 Cryptographic Failures | |
| 0007 | A05 Injection | |
| 0008 | A02 Security Misconfiguration | |
| 0009 | A06 Insecure Design | |
| 0010 | A03 Software Supply Chain Failures | |
| 0011 | A08 Software or Data Integrity Failures | |
| 0012 | A09 Security Logging & Alerting Failures | |
| 0013 | A10 Mishandling of Exceptional Conditions | |
| 0014 | Oral drill in Danish, all ten | |

## Learner baseline (2026-11-26)

- Knew category names only (outside A01/A07, which they studied for the problem statement).
- Juice Shop installed, no challenges solved. Campfire intro path done.

## Sheet Herder pointers found so far

Pinned commits: API `8cec636`, app `3b3beb6`. These are pointers only; nothing has been verified as a vulnerability.

- `ApplicationConfig.java:90-91`: `authenticate` / `authorize` as `beforeMatched` filters.
- `ApplicationConfig.java:94-`: `configureCors`, origins from env `CORS_ALLOWED_ORIGINS`.
- `ApplicationConfig.java:120-136`: exception handlers (A10).
- `security/utils/JWTUtil.java`, `PasswordUtil.java`, `security/services/SecurityService.java`.
- App: `components/ProtectedRoute.jsx`, `context/auth/AuthProvider.jsx`.
