# Antigravity Workshop Starter

Starter repository for 2-hour Antigravity developer workshop sprints. Learning, experimentation, and reusable takeaways matter more than shipping finished code.

## Repository Layout

- `.agents/skills/workshop-sprint-coach/` — active workspace symlink to the sprint coach skill
- `skills/workshop-sprint-coach/` — skill instructions (`SKILL.md`) and curated track/resource references
- `AGENTS.md` — concise standing instructions loaded at session start (keep under 80 lines)

## Working Agreements

- **Start with scope:** Run `workshop-sprint-coach` (or `/grill-me` -> `/plan`) before writing code.
- **Keep context lean:** Put domain-specific rules in `.agents/rules/` or `docs/specs/` rather than bloating this file.
- **No secrets or production data:** Use synthetic fixtures (`data.js`, SQLite/JSON mocks) for all workshop experiments.
- **Verify changes:** Run unit tests (`python3 -m unittest` / `pytest`) or `/browser` checks before wrapping up.
- **Capture learnings:** Reserve the final 15 minutes for Track 10 (`/learn` synthesis) to extract reusable rules and friction notes.

## Quick Commands

- Validate Python scripts/tests (if added): `python3 -m unittest discover -s tests`
- Serve static web apps locally: `python3 -m http.server 8000`
