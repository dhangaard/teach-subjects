# teach-subjects

One folder per subject under `subjects/`, each a self-contained workspace for the `/teach` skill.

## Layout

```
subjects/
├── _template/            ← copy this to start a new subject
│   └── CLAUDE.md
└── ai-prompting/
    ├── CLAUDE.md         ← isolation rules + what's in sources/
    ├── RESOURCES.md      ← curated sources (seeded; /teach extends it)
    ├── sources/          ← primary material you supply (PDFs, markdown files, notes)
    │   └── the-prompt-report.pdf
    │   # created by /teach as you go:
    ├── MISSION.md
    ├── NOTES.md
    ├── lessons/          ← 0001-*.html …
    ├── reference/        ← cheat sheets, glossary
    ├── learning-records/ ← 0001-*.md …
    └── assets/           ← shared lesson CSS/widgets
```

## Studying a subject

Always open the **subject folder** itself, not the repo root. `/teach` keeps all its state (mission, lessons, learning records) in the folder Claude Code was started from, so the folder you open is the subject you're studying.

- **VS Code:** `File → Open Folder… → subjects/<subject-slug>` (or `code subjects/<subject-slug>`), then start Claude Code in that window.
- **Terminal:** `cd subjects/<subject-slug> && claude`

Then run `/teach`. For the first session, paste the subject's `KICKOFF.md` prompt instead of a bare `/teach`; it interviews you for `MISSION.md`. Later sessions pick up from the learning records, so run `/teach` again to continue, or `/teach <specific thing>` to aim the next lesson. Lessons are HTML files in `lessons/`; open them in a browser. Ask Claude follow-up questions in the same session.

### Where the skills come from

The skills (`/teach` and the rest, from [mattpocock/skills](https://github.com/mattpocock/skills)) are installed once, at the repo root, in `.claude/skills/`. Claude Code also looks for `.claude/skills/` in the parent folders of the one you open, so every subject folder gets them without its own copy. Type `/` in the Claude Code prompt to check that `/teach` is listed.

- The repo-root `CLAUDE.md` is loaded too. It only configures the engineering skills (see `docs/agents/`), and each subject's own `CLAUDE.md` says it doesn't apply to teaching.
- If the installer creates symlinks with absolute paths, moving or re-cloning the repo breaks them. Reinstall the skills in the new location.
- A subject folder kept **outside** this repo won't see these skills. Install them at user level (`~/.claude/skills/`) instead.

## Start a new subject

1. `cp -r subjects/_template subjects/<subject-slug>` and fill in `CLAUDE.md` and `KICKOFF.md`.
2. Put primary sources in `subjects/<subject-slug>/sources/`. This repo is **public**, so commit them only if the license allows redistribution (e.g. Creative Commons), and keep the attribution in `RESOURCES.md`. Otherwise link them from `RESOURCES.md` only.
3. Add the subject to the list below, open its folder (see [Studying a subject](#studying-a-subject)) and run `/teach`.

## Subjects

- [AI prompting](subjects/ai-prompting/): grounded in _The Prompt Report_ (arXiv:2406.06608).
- [Cyber security](subjects/cyber-security/): the 4th-semester security elective exam, starting with OWASP Top 10:2025 and applied to Sheet Herder. Its `sources/` holds git submodules (see below).

## Subjects with submodules

Some subjects pull reference repos (course notes, the app under study) into `sources/` as git submodules, pinned to a commit.

- After cloning this repo: `git submodule update --init`
- To pull the latest notes or code: `git submodule update --remote` (then commit the new pins)
