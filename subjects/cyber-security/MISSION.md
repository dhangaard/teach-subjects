# Mission

## Who

Datamatiker student, 4th semester (Denmark), on the security elective (10 ECTS). Builds and owns Sheet Herder (React SPA + Java/Javalin REST API, JWT auth, Docker behind Caddy). Has completed Campfire Security's *Introduction to Campfire Training* path. Juice Shop is running in the Kali VM (`localhost:3000`), with no challenges solved yet.

## Why

An **individual oral exam in Danish**: 30 min, 7-point scale, internal examiner, **early to mid January 2027**. The learner defends a vulnerability analysis of Sheet Herder scoped to A01 Broken Access Control and A07 Authentication Failures (`sources/course-notes/daniel/problemformulering.md`). The examiner assesses against the course learning goals (`sources/course-notes/README.md`) and may ask about **any** OWASP Top 10:2025 category.

## Phase 1: OWASP Top 10:2025 (now until mid-December 2026)

Starting point: knows the category names, can't yet explain most of them.

Done when the learner can:

1. **Explain all ten categories in Danish**, each with what it is, a typical attack, the impact, and how to prevent it, without notes, in about two minutes per category.
2. **A01 and A07 in depth:** name the main weakness types in each (for example IDOR, privilege escalation, CORS misconfiguration and JWT tampering for A01; credential stuffing, weak password storage and session/token lifecycle for A07). Point to where each control lives, or would live, in Sheet Herder, and say how to test and fix it.
3. **Link a vulnerability to its prevention** in a concrete codebase (learning goal: *forklare sammenhængen mellem en identificeret sårbarhed og relevante forebyggende tiltag*).
4. **Have hands-on evidence:** solve at least one Juice Shop challenge or Campfire lab per category where one exists, in authorised environments only.

## Later phases (follow the learning goals)

Threat modelling, testing method, ethics and Danish law, remediation and verification, Linux.

## Format

- About 45-minute lessons, one category per lesson. A01 and A07 get two lessons each (concept, then Sheet Herder).
- Lessons in English, with Danish terms alongside key concepts. Every lesson ends with a short "say it in Danish" exercise.
- Grounded in `sources/owasp-top10-2025/` first, then the course notes and Sheet Herder code.
