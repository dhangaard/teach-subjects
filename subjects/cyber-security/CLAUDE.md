# Teaching workspace: Cyber security (web security elective)

This folder is a self-contained `/teach` workspace. Treat **this folder** as the workspace root: `MISSION.md`, `RESOURCES.md`, `NOTES.md`, `lessons/`, `reference/`, `learning-records/` and `assets/` all live here.

- Do not read, reference or reuse anything from sibling folders under `subjects/`. Each subject is isolated.
- Ground teaching in `sources/` first (see `RESOURCES.md`), then in other high-trust sources. Do not rely on parametric knowledge.
- The repo-root `CLAUDE.md` and `docs/agents/` configure the engineering skills; they do not apply to teaching here.

## Context for the mission interview

The learner is a Datamatiker student, 4th semester (Denmark), taking the security elective (10 ECTS). The subject ends in an **individual oral exam in Danish** (30 min, 7-point scale, internal examiner): the student defends a self-chosen investigation presented as a report or website.

- **Learning goals** (the exam is assessed against them): `sources/course-notes/README.md`
- **Problem statement:** `sources/course-notes/daniel/problemformulering.md`. A vulnerability analysis of Sheet Herder, scoped to **A01 Broken Access Control** and **A07 Authentication Failures**, covering threat model, the ethical and legal framework, API tests, client tests, and verified improvements.
- **Report template:** `sources/course-notes/report_content.md` and `report_format.md`. A security improvement case study with before/after verification.
- **Course plan:** `sources/course-notes/thomas/CoursePlan.md` (12 lectures and their workshops).
- **System under test:** Sheet Herder, the learner's own app: a React SPA (`sources/sheet-herder-app`) and a Java/Javalin + JPA/Hibernate + PostgreSQL REST API (`sources/sheet-herder-api`), JWT auth, Docker behind Caddy.

Phase 1 (the learner's stated starting point): the basics of vulnerabilities through **OWASP Top 10:2025**. **All ten categories are required.** The examiner may ask about any of them, so the learner must be able to explain each one in Danish: what it is, a typical attack, its impact, and how to prevent it. A01 and A07 go deeper still, down to how they would show up in Sheet Herder and how to test and fix them. Later phases follow the learning goals: threat modelling, testing method, ethics and law, remediation and verification, and Linux.

## Teaching rules for this workspace

- **OWASP Top 10:2025 is the spine.** Every lesson maps to a category ID (A01–A10). The other OWASP projects in `RESOURCES.md` are pulled in only to answer a specific question a lesson raises, never surveyed for their own sake.
- **Tie lessons to Sheet Herder.** Wherever possible, point to the actual file or endpoint in `sources/sheet-herder-*` where a weakness or control would live. Do not claim a vulnerability exists without evidence; existing controls that work are valid findings too.
- **Danish exam, English sources.** Give each glossary term its Danish equivalent where one is in common use, so the learner can defend the material in Danish.
- **Practice only in authorised environments.** These are the learner's Kali Linux VM (VirtualBox) running OWASP Juice Shop at `localhost:3000`, Campfire Security labs, PortSwigger labs, and a local Sheet Herder instance. Never suggest testing production or third-party systems. Burp Suite comes later in the learner's plan.
- **The submodules are read-only references.** Do not edit code in `sources/`. The learner fixes Sheet Herder in its own clone.

## Sources

- `sources/owasp-top10-2025/*.md`: the official OWASP Top 10:2025 text (English, from github.com/OWASP/Top10, commit in `.commit`, CC BY 3.0). One file per category.
- `sources/course-notes/`: git submodule of github.com/HartmannDemoCode/security, holding notes by the learner (`daniel/`), a fellow student (`morten/`) and the teacher (`thomas/`). `thomas/vocabulary.md` and `thomas/it-security-vocabulary.md` are the teacher's vocabulary. Prefer it when choosing glossary terms.
- `sources/sheet-herder-api/` and `sources/sheet-herder-app/`: git submodules of the learner's app.
