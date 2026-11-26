# Cyber Security Resources

## Knowledge

### Core (use first)

- [OWASP Top 10:2025](https://top10.owasp.org/2025/)
  Local copy: `sources/owasp-top10-2025/` (CC BY 3.0). The consensus list of the ten most critical web application security risk categories, each with description, CWE mapping, prevention advice and example attack scenarios. Use for: the spine of every lesson; A01 and A07 in depth.
- Course repo: [HartmannDemoCode/security](https://github.com/HartmannDemoCode/security)
  Local copy: `sources/course-notes/`. Learning goals, the learner's problem statement, the report template, the teacher's course plan and vocabulary, and a fellow student's notes. Use for: aligning lessons with the exam and with the course's own terminology.
- Sheet Herder: [API](https://github.com/dhangaard/sheet-herder-api) · [App](https://github.com/dhangaard/sheet-herder-app)
  Local copies: `sources/sheet-herder-api/`, `sources/sheet-herder-app/`. The system under investigation. Use for: grounding every concept in a real endpoint, filter or component.

### Supporting (only when a lesson needs it)

- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
  Concise, practical prevention guidance per topic. Use for: the *fix* side of a finding, chiefly the Authorization, Authentication, Session Management, Password Storage and JSON Web Token for Java cheat sheets (the teacher's course plan cites several of these).
- [OWASP Web Security Testing Guide (WSTG)](https://owasp.org/www-project-web-security-testing-guide/)
  A methodology for testing web apps, organised by test category. Use for: the investigation method chapter, mainly its authentication, authorization and session management tests. Do not survey the whole guide.
- [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/)
  Verifiable security requirements. Use for: turning "expected security behaviour" into checkable requirements, and for the peer-review workshop (course plan lecture 11).
- [PortSwigger Web Security Academy](https://portswigger.net/web-security)
  Free explanations plus hands-on labs. Use for: practice labs on access control, authentication, CORS and JWT (named in the teacher's course plan).

## Practice environments

- [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/), running locally in the learner's Kali VM at `localhost:3000`. Use for: safe exploitation practice across the Top 10 before testing Sheet Herder.
- [Campfire Security](https://campfiresecurity.dk/), a Danish training platform (free with a student email) whose single courses include OWASP Top 10:2025. Use for: guided labs and intro paths.

## Wisdom (Communities)

- Study group and teacher (Thomas) on the elective. Use for: the threat-model workshop, the findings review and peer feedback (course milestones).

## Gaps

- **Danish legal and ethical framework for penetration testing** (a knowledge learning goal and sub-question 2): no authoritative source chosen yet. Look for primary legal text and official Danish guidance.
- No external practitioner community chosen yet.
