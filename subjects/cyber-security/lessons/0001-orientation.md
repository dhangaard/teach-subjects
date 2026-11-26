# Lesson 0001: Orientation to the OWASP Top 10:2025

**Category:** all (A01–A10, overview) · **Time:** ~45 min · **Phase:** 1, OWASP Top 10:2025

## Goals

By the end of this lesson you can:

1. Say what the OWASP Top 10 *is* and what it is not.
2. Explain in about 60 seconds, in Danish, how the 2025 list was built.
3. Use the core vocabulary without mixing up *vulnerability*, *threat* and *risk*.
4. Name all ten categories and give a rough idea of where each would show up in Sheet Herder.
5. Use the four-part answer (**what / attack / impact / prevention**) that every later lesson trains.

Sources: `sources/owasp-top10-2025/0x00_2025-Introduction.md` and `0x02_2025-What_are_Application_Security_Risks.md`. Vocabulary comes from Thomas's `sources/course-notes/thomas/it-security-vocabulary.md`.

---

## 1. What the Top 10 is (5 min)

The OWASP Top 10 is a **ranked list of ten risk categories** for web applications. 2025 is the 8th edition.

Three things to get right, because examiners like to probe them:

- **Each entry is a category, not a single bug.** Every category groups a set of CWEs. There are 248 CWEs across the ten categories, between 5 (A03, A09) and 40 (A01) per category. That's why "Injection" covers both XSS and SQL injection.
- **The categories describe causes, not symptoms.** OWASP says it focused "on the root cause over the symptoms as much as possible". "Cryptographic Failure" is a cause; "Sensitive Data Exposure" is a symptom. The 2025 list prefers causes because the cause tells you what to fix.
- **It is an awareness list, not a complete standard.** It ranks risks across millions of applications. Your *own* system's risk depends on its context. OWASP's example is a CMS used for public information versus the same CMS used for health records: the software is identical, but the risk is very different (0x02). For checkable requirements, OWASP recommends ASVS instead. It also warns that no tool can claim full Top 10 coverage (0x03). We'll use ASVS later in the course.

> **Exam phrasing (DA):** *"OWASP Top 10 er en rangeret liste over de ti mest kritiske risikokategorier for webapplikationer. Hver kategori samler en række CWE'er og fokuserer så vidt muligt på grundårsagen frem for symptomet."*

## 2. How the 2025 list was built (10 min)

This is a likely opening question ("Hvorfor er Broken Access Control nr. 1?"), so learn the outline.

**Data-informed, not blindly data-driven.**

- Organisations donated test results from **more than 2.8 million applications**.
- From the data they ranked 12 categories and took **8**. The remaining **2 came from a community survey** of practitioners. The data looks backwards, and some risks are hard to test automatically, so they never show up in the data.
  - **A03 Software Supply Chain Failures** was top-ranked in the survey (50% of respondents put it #1).
  - **A09 Security Logging & Alerting Failures** was voted in by the survey, for the third time.

**What was measured:**

| Factor | Meaning | Danish |
|---|---|---|
| **Incidence rate** | % of tested applications that had at least one CWE from the category. *Not* how many times it appeared: one hit or 4,000 count the same. | forekomst (andel af applikationer) |
| **Coverage** | % of applications that were tested for that CWE at all. Higher coverage means the incidence figure is more trustworthy. | testdækning |
| **Exploit / Impact** | Average CVSS exploit and impact sub-scores from CVEs mapped to the CWEs (NVD data). | udnyttelighed / konsekvens |

These are combined into a risk score. Broken Access Control scored highest (621.60).

**Why A01 is #1:** 100% of the applications tested had *some* form of broken access control. On average 3.73% of tested applications had one of its 40 CWEs. It also has the highest number of occurrences in the data and the second-highest number of related CVEs (`A01_2025-Broken_Access_Control.md`).

**What changed since 2021** (the examiner may ask "hvad er nyt?"):

- **A10 Mishandling of Exceptional Conditions** is **new**: error handling, logic errors, *failing open*.
- **A03 Software Supply Chain Failures** grew out of 2021's *Vulnerable and Outdated Components*. It now covers the whole chain: dependencies, build systems and distribution.
- **SSRF** was folded into **A01** (in 2021 it was its own category).
- **A02 Security Misconfiguration** rose from #5 to #2, because more and more of an application's behaviour is set by configuration.
- Two categories were renamed. A07 dropped "Identification and", and A09 changed "Monitoring" to "**Alerting**", because logging nobody acts on has little value.

> **Exam phrasing (DA):** *"Listen er datainformeret: otte kategorier er udvalgt ud fra testdata fra over 2,8 millioner applikationer, målt på andelen af applikationer med mindst én forekomst, og to er udvalgt via en survey blandt praktikere, fordi data altid ser bagud."*

## 3. Core vocabulary (10 min)

These words are the frame for every answer. The full list is in `reference/glossary.md`.

| English | Danish | One-line meaning (after Thomas's vocabulary) |
|---|---|---|
| Asset | aktiv | Something of value that needs protection: data, accounts, services, reputation. |
| Vulnerability | sårbarhed | A weakness that a threat can exploit. Not every bug is one; it needs a *security consequence*. |
| Threat | trussel | A circumstance or event that could cause harm. |
| Threat actor | trusselsaktør | The person or group behind a deliberate attack. |
| Exploit | exploit / udnyttelse | The input or sequence of actions that takes advantage of a vulnerability. |
| Risk | risiko | Likelihood × impact, in context. |
| Security control | sikkerhedskontrol / sikringsforanstaltning | A measure that reduces risk: preventive, detective or corrective. |
| Attack vector / attack surface | angrebsvektor / angrebsflade | One route for an attack / all exposed entry points together. |
| Trust boundary | tillidsgrænse | Where data crosses between trust levels, e.g. from the React app to the API. |
| CIA triad | CIA (fortrolighed, integritet, tilgængelighed) | Confidentiality, integrity, availability. |
| CWE / CVE / CVSS | – | Weakness *type* / one *specific* disclosed vulnerability / a *severity* score. |

**The distinction to nail:** a *vulnerability* is the weakness, a *threat* is what could cause harm through it, and *risk* is how likely that is and how bad it would be for *this* system.

**Sheet Herder example, framed as a hypothesis (not a finding):**

- Asset: a user's character sheets and e-mail address.
- Threat: another logged-in user who wants to read them.
- The vulnerability you will test for: the API returns a sheet without checking who owns it.
- Risk: depends on how easy it is (just change an ID?) and how bad it is (personal data, so GDPR applies).

Whether that vulnerability actually exists is what lesson 0003 investigates.

## 4. The ten, and where they would live in Sheet Herder (10 min)

Learn the English names; they are what everyone says, in Danish too. The Danish glosses are only to help you explain them.

| ID | Name | Danish gloss | Where to look in Sheet Herder (attack surface, *not* findings) |
|---|---|---|---|
| A01 | Broken Access Control | brudt adgangskontrol | `ApplicationConfig.java` registers `authenticate` and `authorize` as `beforeMatched` filters (lines 90–91); ownership checks in `CharacterSheetService` / `UserService`; CORS in `configureCors` (line 94); `ProtectedRoute.jsx` in the app (which is client-side only) |
| A02 | Security Misconfiguration | sikkerhedsfejlkonfiguration | `Dockerfile`, env variables such as `CORS_ALLOWED_ORIGINS`, Caddy config, `logback.xml` |
| A03 | Software Supply Chain Failures | fejl i softwareforsyningskæden | `pom.xml`, `package.json` / `package-lock.json`, base image in `Dockerfile`, CI workflows |
| A04 | Cryptographic Failures | kryptografiske fejl | `PasswordUtil.java` (hashing), `JWTUtil.java` (signing), TLS at Caddy |
| A05 | Injection | injektion | JPQL in the DAOs (e.g. `UserDAO.java:106`), `Validator.java`, React rendering of user text |
| A06 | Insecure Design | usikkert design | `docs/business-rules.md`, `docs/user-stories.md`: are misuse cases designed for? |
| A07 | Authentication Failures | autentificeringsfejl | `SecurityService.java`, `SecurityController.java`, `JWTUtil.java`, `AuthProvider.jsx` (token storage, logout) |
| A08 | Software or Data Integrity Failures | fejl i software- eller dataintegritet | unsigned or unverified data the API trusts; build artefacts; the external D&D API in `DNDClient.java` |
| A09 | Security Logging & Alerting Failures | mangelfuld sikkerhedslogning og alarmering | `logback.xml`: are failed logins and denied access logged, and does anyone get alerted? |
| A10 | Mishandling of Exceptional Conditions | mangelfuld håndtering af undtagelsestilstande | Exception handlers in `ApplicationConfig.java` (lines 120–136): what does the client see, and does an error ever *fail open*? |

Paths are relative to `sources/sheet-herder-api/src/main/java/app/` (API) or `sources/sheet-herder-app/src/` (app). This is a map of *where to look*. The table makes no claim that anything is broken.

**Memory hook for the order:** *Access, Config, Chain, Crypto, Inject · Design, Auth, Integrity, Logs, Exceptions.*

## 5. The four-part answer (5 min)

Every category lesson trains the same structure. Use it in the exam:

| Part | Danish | Question it answers |
|---|---|---|
| **What** | Hvad er det? | Definition plus root cause, one or two sentences |
| **Attack** | Typisk angreb | One concrete scenario, ideally from OWASP's example scenarios |
| **Impact** | Konsekvens | Which part of CIA is hit, and the business impact |
| **Prevention** | Forebyggelse | Two or three controls, and *where* they belong (server, client, config, process) |

A worked example using A01, at the level you'll reach by lesson 0002:

> **Hvad:** Brudt adgangskontrol er, når systemet ikke håndhæver, hvad en autentificeret eller anonym bruger må gøre, så brugere kan handle uden for deres tilladelser.
> **Angreb:** En bruger ændrer et id i URL'en, fx `/api/sheets/42` til `/api/sheets/43`, og får en andens data (IDOR).
> **Konsekvens:** Brud på fortrolighed og evt. integritet. Ved personoplysninger også et GDPR-problem.
> **Forebyggelse:** Deny by default, ejerskabskontrol på serveren for hver forespørgsel, og test af adgangsmatricen. Skjulte knapper i React er ikke en kontrol.

The URL is an illustration, not a real Sheet Herder route.

---

## Practice (in your Kali VM)

1. **Juice Shop: find the Score Board.** Start the container (`sudo docker start juice-shop`) and open `http://localhost:3000`. The Score Board page isn't linked from the menu, and finding it is the first challenge. Hint: a SPA's routes are defined in the JavaScript the browser downloads, so open DevTools → *Sources* and search. When you find it, look at how the challenges are tagged by category. That's your map for the coming lessons. *Lesson link:* a "hidden" page is not a protected page, which is a preview of A01.
2. **Campfire:** open the single course on OWASP Top 10:2025 and do only its introduction/overview part. Note in a sentence or two anything it explains differently from this lesson.

## Check yourself

Answer without looking. Then check against sections 1–4.

1. Why does OWASP count *applications with at least one instance* instead of the total number of instances?
2. Which two categories came from the survey, and why does OWASP use a survey at all?
3. What is the difference between a CWE and a CVE? Give one example of a CWE in A01.
4. Name two changes from 2021 to 2025.
5. Is "Sensitive Data Exposure" a root cause or a symptom? Which 2025 category would usually be its root cause?

## Say it in Danish (out loud, record yourself if you can)

1. **60 seconds:** "Hvad er OWASP Top 10, og hvordan er 2025-udgaven lavet?"
2. **30 seconds:** Forklar forskellen på *sårbarhed*, *trussel* og *risiko* med et eksempel fra Sheet Herder.
3. Name the ten categories in order, in English, with one Danish sentence about each. Saying something vague is fine for now; each one gets its own lesson.

**Next:** lesson 0002, A01 Broken Access Control concepts.
