---
name: workshop-sprint-coach
description: Interactive workshop setup concierge that matches an attendee to a pre-seeded demo, official Google Codelab, Google Skills catalog, or starter prompt via multiple-choice discovery, prepares their starting line (clones/links), and hands control back so the attendee drives the sprint.
---

# Workshop Sprint Coach (Setup & Links Concierge)

Help an individual attendee pick a high-signal 90–120 minute learning path and get to the starting line in under 60 seconds—**without** auto-building or executing the whole project for them.

## Step 1: Fast-Pick or 3-Question Check-In (`ask_question`)

- **If the attendee already named a track, number, or topic** (e.g., `"Track 13"`, `"demo10"`, `"google/skills"`, `"codelab"`): skip the questions and jump straight to **Step 3**.
- **Otherwise**, call the interactive **`ask_question` tool** (multiple-choice option picker UI; fall back to numbered text only if `ask_question` is unavailable) to ask these 3 questions together:

1. **Your experience with Antigravity / agentic harnesses:**
   - A) Brand new (first time using an agentic IDE or CLI)
   - B) Tried basic chat/autocomplete, new to `AGENTS.md`, Skills, and MCP
   - C) Regular user (comfortable with `/plan`, rules, and multi-file edits)
   - D) Advanced (ready for spec-driven subagents, hooks, or architectural audits)
2. **Your primary focus:**
   - A) Application / Full-Stack / Frontend Engineering
   - B) Platform, DevOps, SRE, or Infrastructure
   - C) Data, AI/ML, or Backend Services
   - D) Architecture, CoE, Leadership, or Exploring Ideas
3. **What do you want to explore?**
   - A) **Pre-Seeded Workbench Demo** — clone a ready-to-run local demo (`demo1`–`demo10`) and follow `DEMO_STEPS.md`
   - B) **Guided Codelab** — work step-by-step through an official Google Developer Codelab
   - C) **Official Google Skills** — browse & install a skill from `google/skills` or `google-gemini/gemini-skills`
   - D) **Build / Audit / Standards Sprint** — Camera BOM viewer, `FastMCP` server, repo vertical-slice audit, `AGENTS.md`, or `reveal.js` deck

## Step 2: Recommend Top 2–3 Options (`ask_question`)

1. Read `references/tracks.md` and `references/resources.md`.
2. Present the **top 2–3 matching tracks** with:
   - Track number, title, and difficulty
   - What you'll practice (e.g., `/plan`, `/grill-me`, `AGENTS.md`, `.agents/skills/`, MCP, or subagents)
   - Any extra GCP IAM note if a cloud-deploy codelab is included
3. Immediately call **`ask_question`** with the 2–3 recommended tracks plus `"Show all 13 tracks"` so the attendee can pick with one click.

## Step 3: Set Up the Starting Line Only (Do NOT Auto-Execute)

Once the attendee picks a track, **prepare only the starting line and hand control back to the attendee** so they drive the learning loop themselves:

- **Pre-Seeded Workbench Demos (`Track 13` / `antigravity-advanced-workshop-demos` / `workshop-agentic-sdlc-lab`):**
  - Offer (or run if they confirm) `git clone` and initialize `workspace/` from `.seed/` (`./start_demo.sh <demo>` on macOS/Linux/WSL, or copy `.seed/` on Windows).
  - Point them to the demo's `README.md` and `DEMO_STEPS.md`, share the Step 1 prompt they should try, and **stop**.
- **Official Google Codelabs (`Track 12`):**
  - Share the direct `https://codelabs.developers.google.com/...` URL from `references/resources.md` and flag whether it runs locally (Vertex AI only) or requires extra GCP IAM (Cloud Run, BigQuery, Agent Runtime).
  - Offer to stay open as a Q&A buddy while **they** work through the steps, and **stop**.
- **Official Google Skills (`Track 2`):**
  - Share https://github.com/google/skills and https://github.com/google-gemini/gemini-skills, summarize a few relevant skills, and let **them** pick which one to install and test.
- **Starter Prompts (`Tracks 1, 3–9, 11`):**
  - Provide the tailored starter prompt / checklist from `references/tracks.md` plus relevant links from `references/resources.md`, and **stop**—**never** auto-scaffold or auto-build the full app, server, or presentation unless the attendee explicitly asks you to start.

## Step 4: Wrap-Up Reminder

Remind them that **learning, friction discoveries, and reusable patterns matter more than finished code**—and mention **Track 10 (Synthesis & `/learn`)** for summarizing their top 3 takeaways before the `2:00 PM` share-out.
