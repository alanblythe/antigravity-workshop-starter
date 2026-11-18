# Workshop Sprint Tracks & Prompt Starters

Ten scoped 2-hour sprint tracks organized by difficulty and category. Use the selection matrix below to match a team's answers to their top 2–3 options.

## Track Selection Matrix

| Track | Title | Difficulty | Goal Category | Best For |
| :--- | :--- | :--- | :--- | :--- |
| **Track 3** | Zero-Idea / First-Time Team Kickoff | Beginner | Explore & Learn | Brand-new teams with no fixed project yet |
| **Track 2** | Install & Apply an Official Google Skill | Beginner -> Intermediate | Explore & Learn / Codify Skill | Learning portable `SKILL.md` workflows fast |
| **Track 8** | Modular `AGENTS.md` + Scoped `.agents/rules/` | Beginner -> Intermediate | Codify Skill | Teams with an existing repo & context bloat |
| **Track 1** | One-Shot App Build: Camera BOM List Viewer | Beginner -> Intermediate | Build App | Fast, zero-bundler UI + `/browser` verification |
| **Track 4** | Build a Custom Domain MCP Server (`FastMCP`) | Intermediate | Build MCP | Backend/platform teams connecting domain data |
| **Track 6** | Codify Repo Standards into `SKILL.md` + Script Gate | Intermediate | Codify Skill | Teams wanting deterministic PR/lint gates |
| **Track 5** | Repo Patterns & Vertical Slicing Audit | Intermediate -> Advanced | Audit Repo | Existing codebases needing `AGENT_READINESS.md` |
| **Track 7** | Spec-Driven Build (Elephant-Goldfish Pattern) | Intermediate -> Advanced | Build App | Practicing `SPEC.md` -> `/clear` -> Subagents |
| **Track 9** | Harden App with Lifecycle Hooks & Negative Tests | Intermediate -> Advanced | Audit Repo / Build App | Security guardrails, SQLi/path-traversal tests |
| **Track 10** | Synthesis & `/learn` Share-Out Prep | All Levels | Wrap-Up (Last 15m) | Turning sprint friction into reusable team rules |
| **Track 11** | Interactive HTML Deck (`reveal.js`) | Beginner -> Intermediate | Build App / Share-Out | Building a live browser-based team readout deck |
| **Track 12** | Guided Official Google Codelab | Beginner -> Intermediate | Guided Codelab | Step-by-step official Codelab with Antigravity coaching |

---

## Category A: Explore, Ideate & Context Hygiene

### Track 3 — Zero-Idea / First-Time Team Kickoff: Use Antigravity to Ideate & Learn
- **Difficulty:** Beginner
- **Teaches:** `/plan`, `/grill-me`, Skills, `AGENTS.md`, MCP, and guided exploration

```text
Our team is new to Antigravity and doesn't have a fixed project yet. We have ~2 hours for a hands-on sprint where learning and practical ideas matter more than finished code.
1. Interview us with 4 short multiple-choice questions about our day-to-day role, biggest recurring engineering/ops bottleneck, preferred tech stack, and whether we want to explore coding, documentation, repo analysis, or automation.
2. Based on our answers, propose 3 scoped 90-minute experiments (one safe/easy, one medium, one stretch) and explain which Antigravity features each one teaches (`/plan`, `/grill-me`, Skills, `AGENTS.md`, MCP, or subagents).
3. Once we pick one, walk us through it step-by-step and explain what the harness is doing as we go.
```

### Track 2 — Install & Apply a Skill from the Official Google Skills Library
- **Difficulty:** Beginner -> Intermediate
- **Teaches:** `.agents/skills/<name>/SKILL.md` discovery, adaptation, and invocation

```text
Browse the official Google Agent Skills catalog at https://github.com/google/skills (broad Google Cloud, Developers, and Analytics skills) and/or https://github.com/google-gemini/gemini-skills (Gemini API/SDK skills).
1. Summarize the available skills and recommend the best 1–2 skills for our team's workflow today.
2. Install the skill we choose into this workspace under `.agents/skills/<skill-name>/` (preserving `SKILL.md` and any bundled `scripts/` or `references/`).
3. Adapt any project-specific paths or rules if needed, then immediately invoke/test the newly installed skill against a real file or change in this repository and show us what it caught or produced.
```

### Track 8 — Design a Modular `AGENTS.md` + Scoped `.agents/rules/` Hierarchy
- **Difficulty:** Beginner -> Intermediate
- **Teaches:** Standing context budgets (`<20k` tokens), root `AGENTS.md` (`<80` lines), and scoped rules

```text
Audit our workspace and help us set up clean, non-bloated hierarchical context without exceeding the 20,000-token standing rules budget:
1. Draft a concise root `AGENTS.md` (<80 lines) containing only repo-wide build/test commands, architecture map, and universal invariants.
2. Identify 2–3 domain-specific or subdirectory-specific rules (e.g., SQL/DB safety, frontend accessibility, API contract checks) and place them either in scoped `.agents/rules/*.md` (with `model_decision` or glob triggers) or a nested `subdir/AGENTS.md`.
3. Verify with an experiment that an agent working in the subdirectory picks up the nested/scoped rule without loading unrelated rules from other directories.
```

---

## Category B: Build Apps & Domain MCP Servers

### Track 1 — One-Shot App Build: Camera BOM (Bill of Materials) List Viewer
- **Difficulty:** Beginner -> Intermediate
- **Teaches:** Zero-build HTML/CSS/JS scaffolding, `unittest` verification, and `/browser` UI testing

```text
Build a self-contained, zero-bundler Camera BOM (Bill of Materials) List Viewer web app in a new directory `./camera-bom-viewer` using vanilla HTML5, CSS3, and ES5/ES6 JavaScript (no external CDNs, frameworks, or npm build steps) plus a tiny Python 3 stdlib server (`python3 -m http.server 8000` or `file://` compatible via `<script src="./app.js">`).

Requirements:
1. Realistic Seed Data (`data.js`): Model 2 camera assemblies (e.g., `EOS-Pro Mirrorless Body` and `Cinema-X Body`) as a 3-level hierarchical BOM tree (Assembly -> Sub-Assembly such as Optical Lens Mount, CMOS Sensor & ISP Board, IBIS Stabilization Unit, Battery & Power Delivery, Magnesium Chassis -> Individual Parts with SKU, Supplier, Lead Time in days, Stock Status [`In Stock`, `Low Stock`, `Backorder`], Unit Cost USD, and Qty per Unit).
2. Interactive Tree & Rollup: Expand/collapse assemblies, search by SKU/part/supplier, filter by Stock Status or Sub-Assembly, and toggle Build Lot Multiplier (`1x`, `10x`, `100x`, `500x`) with live rolled-up Total BOM Cost, Longest Critical-Path Lead Time, and Backorder Risk count.
3. Cost Breakdown & Variant Diff: Render a crisp cost-by-subsystem breakdown bar chart (pure CSS or HiDPI `<canvas>`) and a side-by-side comparison mode between the two camera models showing cost & lead-time deltas.
4. Notes, Persistence & Export: Allow engineers to add part notes or flag alternate suppliers persisted in `localStorage` (wrapped in `try/catch` with in-memory fallback), plus one-click CSV and JSON BOM export.
5. UI & Safety Standards: Use semantic `:root` CSS variables supporting both light and dark modes, use `textContent` / DOM element constructors (never `innerHTML` with data strings), and include a `tests/` script (`python3 -m unittest`) validating BOM cost/lead-time rollup math.
6. Verify Before Finishing: Start the local server, open the app with `/browser`, click through expand/collapse, lot-size multipliers (`1x` -> `100x`), filters, and CSV export, and confirm `0` console errors.
```

### Track 4 — Build a Custom Domain MCP Server (`FastMCP` / Python)
- **Difficulty:** Intermediate
- **Teaches:** `mcp` / `FastMCP` (`stdio`), `.mcp.json` registration, negative input validation, and live tool calls

```text
Design and build a local Model Context Protocol (MCP) server in Python (`mcp` / `FastMCP` with `stdio` transport) tailored to your business domain (e.g., Camera Warranty & Service-Center SLA Lookup, Firmware Compatibility Matrix, or Dealer Order Exception Triage).
1. Create a realistic SQLite or JSON fixture dataset and expose 3 read-only MCP tools (e.g., `lookup_model_warranty`, `check_parts_availability`, `assess_rma_eligibility`) plus 1 read-only MCP resource (`schema://domain-rules`).
2. Add strict input validation and a negative test proving malformed or out-of-policy inputs are rejected cleanly.
3. Register the server in workspace `.mcp.json` (or show the exact config), write unit tests, and run an end-to-end tool call through Antigravity to prove the agent can answer business-domain questions using live tool data rather than guessing.
```

---

## Category C: Repo Audits, Standards Gates, Specs & Security

### Track 5 — Analyze a Repo for Patterns, Consistency & Agentic Readiness (Vertical Slicing Audit)
- **Difficulty:** Intermediate -> Advanced
- **Teaches:** Read-only architectural analysis, context-locality scoring, and `AGENTS.md` synthesis

```text
Perform a read-only architectural and agentic-readiness audit of this repository (do not edit source files yet).
1. Map the directory structure and assess whether the codebase follows clean vertical slices (feature-cohesive modules with clear boundaries) or tangled horizontal/monolithic layers where an agent must load dozens of files to make a single change.
2. Identify inconsistent patterns (naming, error handling, test layout, config loading) and implicit "tribal knowledge" that currently lives only in developers' heads.
3. Produce a prioritized `AGENT_READINESS.md` report with: (a) an Agentic Readiness Score across 5 dimensions, (b) the top 3 low-risk refactors to improve vertical slicing and context locality, and (c) a draft `<80`-line `AGENTS.md` capturing the repo's real build/test commands and invariants.
```

### Track 6 — Codify Repo Standards into a Custom `SKILL.md` + Deterministic Script Gate
- **Difficulty:** Intermediate
- **Teaches:** Moving deterministic checks out of prose into executable `scripts/` with non-zero exit codes

```text
Inspect our repository's PR checklists, linters, folder conventions, and recurring review feedback, then package those standards into a reusable Antigravity Skill at `.agents/skills/repo-standards-gate/`.
1. Keep `SKILL.md` lean (<120 lines) with clear YAML frontmatter (`name`, `description` trigger) and step-by-step instructions.
2. Move deterministic checks out of prose and into `scripts/check_standards.py` (e.g., verifying required tests exist for new modules, banning hardcoded secrets/URLs, checking docstring/typing conventions, and exiting non-zero with JSON/line-numbered diagnostics on failure).
3. Test the skill against a deliberately broken sample change and a clean change to prove deterministic pass/fail behavior.
```

### Track 7 — Spec-Driven Build with Elephant-Goldfish Separation (`SPEC.md` -> `/clear` -> Subagents)
- **Difficulty:** Intermediate -> Advanced
- **Teaches:** `/grill-me` requirements discovery, clean-room `SPEC.md`, and isolated Builder/Reviewer subagents

```text
We want to practice the Elephant-Goldfish Spec-Driven Development pattern on a small feature or internal tool.
1. Act as the stateful **Elephant**: use `/grill-me` (ask crisp multiple-choice questions) to nail down requirements, edge cases, API contracts, and acceptance tests—do NOT write implementation code yet.
2. Write the agreed contract to `docs/specs/001-feature-spec.md`.
3. Guide us to run `/clear` (or spawn fresh-context **Goldfish** subagents: one Builder to implement against `SPEC.md`, and one Adversarial Reviewer that only reads `SPEC.md` + git diff to verify compliance and catch gaps).
```

### Track 9 — Harden an Existing App with Lifecycle Hooks & Negative Security Tests
- **Difficulty:** Intermediate -> Advanced
- **Teaches:** Negative security testing (SQLi, path traversal, destructive SQL) and deterministic hook gates

```text
Take a sample API or database script in this repo (or scaffold a small Flask/FastAPI + SQLite endpoint) and harden it using deterministic harness guardrails:
1. Write negative tests for SQL injection, unvalidated inputs, path traversal, and accidental destructive operations (`DROP TABLE` / `DELETE` without `WHERE`).
2. Add a local verification script or pre-commit/lifecycle hook command that runs these checks automatically before any change is considered done.
3. Demonstrate a failing bad change being blocked deterministically, followed by a clean fix passing all checks.
```

---

## Category D: Wrap-Up & Synthesis (Run in Final 15 Minutes)

### Track 10 — Synthesis & `/learn`: Turn Today's Session into Reusable Team Learnings
- **Difficulty:** All Levels
- **Teaches:** Friction capture, 5-minute share-out synthesis, and `/learn`-style rule extraction

```text
Review everything we tried, broke, fixed, and discovered during our 2-hour sprint today.
1. Summarize our top 3 **Learnings & Takeaways** (what worked well with Antigravity, where the harness or our prompts hit friction, and what surprised us) formatted for our 5-minute afternoon share-out—no demo required if we want to focus on insights.
2. Identify 1 concrete next step or pilot idea for our organization's Engineering CoE.
3. Run `/learn`-style extraction: propose 1 reusable `AGENTS.md` rule or `SKILL.md` improvement we should keep so the next team avoids the same friction.
```

### Track 11 — Interactive HTML Presentation with `reveal.js`
- **Difficulty:** Beginner -> Intermediate
- **Teaches:** Zero-build web slides (`reveal.js`), speaker notes, inline diagrams, and `/browser` visual verification

```text
Build a clean, self-contained HTML presentation in `./team-readout-deck` using **reveal.js** (zero npm build step—load via ES module/CDN or vendored local assets and serve via `python3 -m http.server 8000`).
1. Structure 6–8 crisp slides for our afternoon **Team Learnings & Takeaways** share-out: Title, Problem/Idea, What We Tried with Antigravity, Key Friction & Surprises, Live Demo / Architecture Diagram (inline SVG or Mermaid), and Next Steps for Our CoE.
2. Enable keyboard navigation, slide numbers, incremental bullet fragments, syntax-highlighted code blocks, and `<aside class="notes">` presenter speaker notes.
3. Add a custom light/clean theme CSS override so text is high-contrast and scannable from across the room.
4. Start the local server, step through all slides using `/browser`, and verify layout, navigation, and `0` console errors.
```

### Track 12 — Guided Official Google Codelab (Study Buddy Mode)
- **Difficulty:** Beginner -> Intermediate
- **Teaches:** Self-paced Google Cloud Antigravity, ADK, or MCP fundamentals using official codelabs (`references/resources.md`)

```text
We want to work through an official Google Developer Codelab from `references/resources.md` at our own pace, using Antigravity as a live study buddy.
1. Based on our experience level, pick the best starting codelab (L100: Getting Started with Google Antigravity; L100/L200: Building with Google Antigravity; L200: Spec-Driven Development with Antigravity CLI `sdd-agy-cli`, Build & Deploy to GCP, Building AI Agents with ADK, or ADK Memory & MCP) and share the direct URL.
2. Walk us through prerequisites and explain what each step or command is doing as we go.
3. Help us debug any environment/auth hiccup and capture 3 concrete takeaways for our afternoon team share-out.
```
