# Antigravity Workshop Starter

> [!IMPORTANT]
> **Unofficial Community / Workshop Resource** — Accurate as of 11/17/2026.
> This project is not provided by Google and does not come with any support or warranties. This repository is an unofficial, personal workshop companion and is not an official Google product or supported Google Cloud release.

**What this is**
- A ready-to-clone starter repository for 2-hour Antigravity developer workshop sprints.
- Pre-configured with a lean starter `AGENTS.md` and the `workshop-sprint-coach` skill (`.agents/skills/workshop-sprint-coach/`), which runs a 3-question multiple-choice check-in and returns only direct links and brief guidance for pre-seeded demos, official Google Codelabs, official Google Skills, or sprint topics.

**Why this exists**
- Workshop teams arrive with different backgrounds—some are opening an agentic harness for the first time, while others already have production repos and want to test MCP servers, `AGENTS.md` hierarchies, or spec-driven workflows.
- Cloning this repo gives your team a working `AGENTS.md` + interactive coach in under 30 seconds.

**What this is not**
- not an official Google-maintained skills catalog (see [google-gemini/gemini-skills](https://github.com/google-gemini/gemini-skills) for official Google skills)
- not a production framework, SDK, or grading harness
- not a requirement to ship finished code—workshop sprints optimize for learning, friction discovery, and reusable patterns

**How it works**
- `AGENTS.md`: lean `<30`-line starter rules file loaded automatically when you open the repo
- `.agents/skills/workshop-sprint-coach/`: workspace skill symlink pointing to `skills/workshop-sprint-coach/`
- `skills/workshop-sprint-coach/SKILL.md`: read-only links & guidance concierge (`ask_question` check-in -> track match -> returns only direct links and brief guidance; no prompts, cloning, or execution)
- `skills/workshop-sprint-coach/references/tracks.md`: 13 scoped 2-hour sprint tracks (including official Google Codelabs and pre-seeded workbench demos) with direct links and brief guidance organized by difficulty and category
- `skills/workshop-sprint-coach/references/resources.md`: curated index of official Google Codelabs, official Google Skills & OSS repos, and public workshop demo repos

---

## Quick Start for Workshop Attendees

### Option A: Clone the Starter Repo (Recommended)

```bash
git clone https://github.com/alanblythe/antigravity-workshop-starter
cd antigravity-workshop-starter
```

Open the folder in Antigravity (IDE, App, or CLI) and type:

```text
Run workshop-sprint-coach so I can pick what to explore and start right away.
```

### Option B: Add the Skill to an Existing Repo (Single-Prompt Install)

Paste this prompt into Antigravity inside your existing project directory:

```text
Install workshop-sprint-coach from https://github.com/alanblythe/antigravity-workshop-starter and run it so I can pick what to explore and start right away.
```

## License

Apache 2.0 (see individual linked repositories for their respective licenses).
