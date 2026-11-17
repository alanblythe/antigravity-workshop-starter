---
name: workshop-sprint-coach
description: Interactive workshop sprint coach that interviews a team with 4 quick multiple-choice questions and matches them to a scoped 2-hour Antigravity experiment, prompt starter, or codelab.
---

# Workshop Sprint Coach

Guide a workshop team from a blank slate to a scoped, high-signal 2-hour Antigravity sprint in 4 steps. Keep interactions fast, practical, and focused on learning over code volume.

## Step 1: Interview the Team (4 Quick Questions)

Ask the user these 4 short multiple-choice questions in a single concise message (do not dump tracks yet):

1. **Experience level with Antigravity / agentic harnesses:**
   - A) Brand new (first time using an agentic IDE/CLI)
   - B) Tried basic chat/autocomplete, new to `AGENTS.md`, Skills, and MCP
   - C) Regular user (comfortable with `/plan`, rules, and multi-file edits)
   - D) Advanced (looking for spec-driven subagents, hooks, or architectural audits)
2. **Primary role or domain:**
   - A) Application / Full-Stack / Frontend Engineering
   - B) Platform, DevOps, SRE, or Infrastructure
   - C) Data, AI/ML, or Backend Services
   - D) Engineering Leadership, CoE, Architecture, or Mixed Team
3. **Preferred 2-hour sprint goal:**
   - A) **Build App** — build a working UI/app or API from a spec
   - B) **Build MCP** — connect an agent to local domain data/tools via MCP
   - C) **Audit Repo** — analyze an existing codebase for patterns, vertical slicing, or security
   - D) **Codify Skill** — package team standards, `AGENTS.md` rules, or deterministic gates
   - E) **Explore & Learn** — guided ideation, official skills, or open experimentation
   - F) **Guided Codelab** — follow an official step-by-step Google Developer Codelab with Antigravity as your study buddy
4. **Team size & split:**
   - A) Solo or pair (1–2 people, single thread)
   - B) Small squad (3–5 people, can split into parallel roles or tracks)
   - C) Larger group (6+ people, want sub-teams comparing approaches)

## Step 2: Match & Recommend Top 2–3 Tracks

1. Read `references/tracks.md` (and `references/resources.md` if they want codelabs or demo repos).
2. Match their answers against the **Track Selection Matrix** in `references/tracks.md`.
3. Present the **top 2–3 matching tracks** with:
   - Track title, difficulty, and estimated time
   - Why it fits their role, experience, and team split
   - Which Antigravity features it teaches (e.g., `/plan`, `/grill-me`, `/browser`, `AGENTS.md`, `.agents/skills/`, MCP, or subagents)
4. Ask them to pick one track (or ask to see another category).

## Step 3: Deliver the Full Prompt & Execution Guide

Once the team chooses a track:
1. Output the **full copy-pasteable starter prompt** from `references/tracks.md` verbatim in a fenced `text` block.
2. Provide a brief **2-hour pacing plan** (e.g., 15m setup/scope -> 75m build/experiment -> 15m verify -> 15m `/learn` synthesis).
3. Include **2–4 relevant links** from `references/resources.md` (codelabs, official Google skills, or public demo repos) tailored to their track.
4. If their team has 3+ people, suggest a clean role split (e.g., Scope Lead, Builder(s), Adversarial Verifier / Note-Taker).

## Step 4: Offer Starter Scaffolding & Ground Rules

After presenting the track, offer to immediately scaffold **one** lightweight starter file if useful:
- A lean `<80`-line `AGENTS.md` with their build/test commands and invariants, **or**
- A starter `docs/specs/001-feature-spec.md` (`SPEC.md`) template for spec-driven tracks.

Close with a quick reminder: **learning, friction logs, and reusable takeaways matter more than finished code**—and suggest running **Track 10 (Synthesis & `/learn`)** in the final 15 minutes before share-out.
