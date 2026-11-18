---
name: workshop-sprint-coach
description: Self-service interactive workshop launcher that matches an individual attendee to a scoped Antigravity experiment, pre-seeded demo, official skill, or Google Codelab and immediately starts executing it—no second copy-paste required.
---

# Workshop Sprint Coach

Help an individual attendee go from a blank slate to hands-on learning in under 60 seconds. Keep interactions fast, practical, and focused on discovery over code volume.

## Step 1: Fast-Pick or 3-Question Check-In

- **If the attendee already named a track, number, or topic** (e.g., `"Track 1"`, `"Camera BOM"`, `"google/skills"`, `"demo10"`, `"codelab"`): skip the questions and jump straight to **Step 3**.
- **Otherwise**, ask these 3 short multiple-choice questions in one concise message:

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
3. **What do you want to try right now?**
   - A) **Build App** — one-shot Camera BOM viewer, spec-driven feature, or `reveal.js` HTML deck
   - B) **Build MCP** — connect Antigravity to local domain data via `FastMCP`
   - C) **Audit or Harden a Repo** — vertical-slicing audit, `AGENTS.md` hierarchy, or negative security tests
   - D) **Skills & Pre-Seeded Demos** — install an official `google/skills` package or run a ready-to-go workbench demo (`demo1`–`demo10`)
   - E) **Guided Codelab** — work step-by-step through an official Google Developer Codelab with Antigravity coaching

## Step 2: Recommend Top 2–3 Options

1. Read `references/tracks.md` (and `references/resources.md` for codelabs/repos).
2. Present the **top 2–3 matching tracks** from the **Track Selection Matrix** with:
   - Track number, title, and difficulty
   - What you'll learn (e.g., `/plan`, `/grill-me`, `/browser`, `AGENTS.md`, `.agents/skills/`, MCP, or subagents)
   - Any extra GCP IAM note if a cloud-deploy codelab is included
3. Ask them to reply with a **track number** (or ask to see the full 13-track menu).

## Step 3: Execute Immediately (No Second Copy-Paste)

Once the attendee picks a track:
1. Read that track's full instructions in `references/tracks.md` and **start executing it immediately in this same session**—do **NOT** dump a prompt and ask them to copy-paste it into a new chat.
2. Explain briefly what you are doing as you go (e.g., cloning the demo, installing the skill, asking `/grill-me` questions for `SPEC.md`, or walking through Step 1 of the codelab).
3. Include **2–3 relevant links** from `references/resources.md` for reference.

## Step 4: Capture Takeaways Before Share-Out

Remind the attendee that **learning, friction discoveries, and reusable patterns matter more than finished code**—and offer to run **Track 10 (Synthesis & `/learn`)** in the final 15 minutes to summarize their top 3 takeaways for their group's `2:00 PM` share-out.
