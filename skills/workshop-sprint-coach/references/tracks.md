# Workshop Sprint Tracks — Links & Guidance

Thirteen scoped 90–120 minute learning paths. Share only the **links and brief guidance** below—never generate starter prompts or execute setup commands.

## Track Selection Matrix

| Track | Title | Difficulty | Category | Best For |
| :--- | :--- | :--- | :--- | :--- |
| **Track 3** | First-Time Guided Exploration | Beginner | Explore & Learn | Brand-new teams with no fixed project yet |
| **Track 2** | Explore Official Google Skills | Beginner -> Intermediate | Explore & Learn / Skills | Learning portable `SKILL.md` workflows fast |
| **Track 8** | Modular `AGENTS.md` + Scoped Rules | Beginner -> Intermediate | Context Hygiene | Teams with an existing repo & context bloat |
| **Track 1** | Zero-Build Web App (Camera BOM Viewer) | Beginner -> Intermediate | Build App | Fast, zero-bundler HTML/JS UI + `/browser` testing |
| **Track 4** | Custom Domain MCP Server (`FastMCP`) | Intermediate | Build MCP | Backend/platform teams connecting domain data |
| **Track 6** | Repo Standards `SKILL.md` + Script Gate | Intermediate | Codify Skill | Deterministic PR/lint checks via scripts |
| **Track 5** | Repo Vertical Slicing & Readiness Audit | Intermediate -> Advanced | Audit Repo | Existing codebases needing `AGENT_READINESS.md` |
| **Track 7** | Spec-Driven Build (Elephant-Goldfish) | Intermediate -> Advanced | Build App | Practicing `SPEC.md` -> `/clear` -> Subagents |
| **Track 9** | Lifecycle Hooks & Negative Security Tests | Intermediate -> Advanced | Audit / Security | Security guardrails, SQLi/path-traversal tests |
| **Track 10** | Synthesis & `/learn` Share-Out Prep | All Levels | Wrap-Up (Last 15m) | Turning sprint friction into 3 takeaways |
| **Track 11** | Interactive HTML Deck (`reveal.js`) | Beginner -> Intermediate | Build App / Share-Out | Zero-build browser readout slides |
| **Track 12** | Official Google Codelab | Beginner -> Intermediate | Guided Codelab | Step-by-step official Google Developer Codelab |
| **Track 13** | Pre-Seeded Workbench Demo | Beginner -> Intermediate | Pre-Seeded Demo | Local-only resettable demos (`demo1`–`demo10`) |

---

## Track Guidance

### Track 1 — Zero-Build Web App (Camera BOM Viewer)
- **Difficulty:** Beginner -> Intermediate · **Teaches:** `/plan`, zero-bundler HTML/CSS/JS, `python3 -m unittest`, `/browser` verification
- **Links:** [Antigravity Docs](https://antigravity.google/docs) · [App Creator Templates](https://github.com/alanblythe/antigravity-2.0-application-creator)
- **Guidance:**
  - Open a clean local folder and use `/plan` to scope a 3-level Camera BOM tree (data, rollup math, light/dark CSS, `localStorage`).
  - Keep it zero-build (vanilla HTML5/CSS3/JS served with `python3 -m http.server`) and pair it with `unittest` for cost/lead-time math.
  - Verify the rendered UI and console (`0` errors) using `/browser`.

### Track 2 — Explore & Apply Official Google Skills
- **Difficulty:** Beginner -> Intermediate · **Teaches:** `.agents/skills/<name>/SKILL.md` discovery and invocation
- **Links:** [google/skills](https://github.com/google/skills) · [google-gemini/gemini-skills](https://github.com/google-gemini/gemini-skills) · [Knowledge Catalog Plugin](https://github.com/gemini-cli-extensions/knowledge-catalog)
- **Guidance:**
  - Browse the two official catalogs above and pick 1 skill that matches your team's stack (Cloud, Developers, Analytics, or Gemini SDK).
  - Copy or install its `SKILL.md` (and any `scripts/` or `references/`) into `.agents/skills/<skill-name>/`.
  - Test it on a real file in your workspace and note what worked vs. what needed local adaptation.

### Track 3 — First-Time Guided Exploration
- **Difficulty:** Beginner · **Teaches:** `/plan`, `/grill-me`, `AGENTS.md`, Skills, and MCP basics
- **Links:** [Getting Started Codelab](https://codelabs.developers.google.com/getting-started-google-antigravity) · [Antigravity Docs](https://antigravity.google/docs) · [Workshop Starter Repo](https://github.com/alanblythe/antigravity-workshop-starter)
- **Guidance:**
  - Start with the Getting Started Codelab or pick a small pain point from your day-to-day work.
  - Practice `/grill-me` before coding so the agent asks clarifying questions first, then review `/plan` before approving edits.
  - Focus on observing how the harness reads files, runs checks, and recovers from errors.

### Track 4 — Custom Domain MCP Server (`FastMCP` / Python)
- **Difficulty:** Intermediate · **Teaches:** `mcp` / `FastMCP` (`stdio`), `.mcp.json` registration, negative input validation
- **Links:** [MCP Toolbox for Databases](https://github.com/googleapis/mcp-toolbox) · [ADK Memory & MCP Codelab](https://codelabs.developers.google.com/codelabs/adk-memory-mcp)
- **Guidance:**
  - Pick a small domain fixture (JSON or SQLite, e.g., warranty lookup, parts stock, or firmware matrix) and expose 2–3 read-only tools via `FastMCP`.
  - Register it in `.mcp.json` and include a negative test showing malformed inputs fail cleanly.
  - Run a live query through Antigravity to verify it uses your MCP tool output rather than guessing.

### Track 5 — Repo Vertical Slicing & Readiness Audit
- **Difficulty:** Intermediate -> Advanced · **Teaches:** Read-only architectural analysis, context locality, `AGENTS.md` synthesis
- **Links:** [Antigravity Docs](https://antigravity.google/docs) · [Elephant-Goldfish Model](https://egm.dev)
- **Guidance:**
  - Point Antigravity at an existing repo in read-only mode to map directory boundaries (vertical feature slices vs. tangled horizontal layers).
  - Capture inconsistent conventions and tribal knowledge in an `AGENT_READINESS.md` note.
  - Distill only the real build/test commands and universal invariants into a `<80`-line `AGENTS.md`.

### Track 6 — Repo Standards `SKILL.md` + Deterministic Script Gate
- **Difficulty:** Intermediate · **Teaches:** Moving deterministic checks out of prose into executable `scripts/`
- **Links:** [google/skills](https://github.com/google/skills) · [Antigravity Docs](https://antigravity.google/docs)
- **Guidance:**
  - Turn a recurring PR checklist or lint rule into `.agents/skills/<name>/SKILL.md` (`<120` lines).
  - Put deterministic checks (missing tests, banned patterns, naming) into a Python/shell script in `scripts/` that exits non-zero on failure.
  - Test both a failing sample and a clean sample to confirm deterministic pass/fail behavior.

### Track 7 — Spec-Driven Build (Elephant-Goldfish Pattern)
- **Difficulty:** Intermediate -> Advanced · **Teaches:** `/grill-me` requirements discovery, `SPEC.md`, `/clear`, isolated review
- **Links:** [Elephant-Goldfish Model](https://github.com/google/elephant-goldfish-model) · [egm.dev](https://egm.dev) · [SDD with Antigravity CLI Codelab](https://codelabs.developers.google.com/sdd-agy-cli)
- **Guidance:**
  - Use `/grill-me` first to lock down requirements and edge cases into a `SPEC.md` without writing code.
  - Run `/clear` (or use a fresh subagent) so implementation starts with clean context reading only `SPEC.md`.
  - Use a separate review pass comparing `git diff` strictly against `SPEC.md`.

### Track 8 — Modular `AGENTS.md` + Scoped `.agents/rules/`
- **Difficulty:** Beginner -> Intermediate · **Teaches:** Standing context budgets (`<20k` tokens), root `AGENTS.md` (`<80` lines), scoped rules
- **Links:** [Antigravity Docs](https://antigravity.google/docs) · [Workshop Starter Repo](https://github.com/alanblythe/antigravity-workshop-starter)
- **Guidance:**
  - Keep root `AGENTS.md` strictly to repo-wide build/test commands and universal invariants.
  - Move domain-specific rules (SQL, UI, APIs) into `.agents/rules/*.md` with glob or `model_decision` triggers, or nested `subdir/AGENTS.md`.
  - Verify that a task in one subdirectory loads only its relevant rules without bloating unrelated tasks.

### Track 9 — Lifecycle Hooks & Negative Security Tests
- **Difficulty:** Intermediate -> Advanced · **Teaches:** Negative security testing (SQLi, path traversal) and deterministic hook gates
- **Links:** [Antigravity Docs](https://antigravity.google/docs) · [Advanced Workshop Demos (`demo3`, `demo9`)](https://github.com/alanblythe/antigravity-advanced-workshop-demos)
- **Guidance:**
  - Take a small API or DB script and add negative tests for SQL injection, path traversal, and unvalidated inputs.
  - Wire a verification script or pre-commit/hook gate that blocks bad changes automatically.
  - Confirm a seeded bad edit is caught deterministically before verifying the clean fix.

### Track 10 — Synthesis & `/learn` Share-Out Prep (Final 15m)
- **Difficulty:** All Levels · **Teaches:** Friction capture, 5-minute share-out synthesis, `/learn`-style rule extraction
- **Links:** [Workshop Starter Repo](https://github.com/alanblythe/antigravity-workshop-starter)
- **Guidance:**
  - Summarize 3 takeaways for the `2:00 PM` share-out: what worked, where you hit friction, and what surprised you.
  - Identify 1 pilot idea or CoE standard to test next with your team.
  - Capture 1 `AGENTS.md` rule or `SKILL.md` tweak that would have saved time today.

### Track 11 — Interactive HTML Presentation (`reveal.js`)
- **Difficulty:** Beginner -> Intermediate · **Teaches:** Zero-build web slides (`reveal.js`), speaker notes, `/browser` verification
- **Links:** [App Creator Templates](https://github.com/alanblythe/antigravity-2.0-application-creator) · [Antigravity Docs](https://antigravity.google/docs)
- **Guidance:**
  - Scaffold a 6–8 slide HTML deck in a local folder using `reveal.js` (no npm build step; serve with `python3 -m http.server`).
  - Cover Problem/Idea, What You Tried, Friction & Surprises, Diagram/Demo, and CoE Next Steps.
  - Check slide navigation and `0` console errors with `/browser`.

### Track 12 — Official Google Codelab
- **Difficulty:** Beginner -> Intermediate · **Teaches:** Self-paced Antigravity, ADK, or MCP fundamentals
- **Links:** See `references/resources.md` for all L100–L300 Codelab URLs
- **Guidance:**
  - **Local / Baseline Vertex AI friendly (no extra IAM):** *Getting Started with Google Antigravity*, *Building with Google Antigravity*, *Spec-Driven Development with Antigravity CLI*, *Building AI Agents with ADK*, *ADK Agentic Patterns with Memory & MCP*.
  - **Requires extra GCP IAM (Cloud Run / BigQuery / Agent Runtime):** *Build & Deploy to GCP*, *Deploy ADK to Agent Runtime*, *Remote MCP on Cloud Run*, *MCP Toolbox for BigQuery*—confirm permissions with your GCP admin first.
  - Open the codelab URL in your browser and follow it step-by-step, using Antigravity for Q&A if you hit setup friction.

### Track 13 — Pre-Seeded Workbench Demo (`antigravity-advanced-workshop-demos`)
- **Difficulty:** Beginner -> Intermediate · **Teaches:** Pre-seeded local workflows (`AGENTS.md`, ADRs, TDD heal loops, adversarial review, greenfield spec-to-app) with zero extra GCP IAM
- **Links:**
  - [antigravity-advanced-workshop-demos](https://github.com/alanblythe/antigravity-advanced-workshop-demos)
  - [workshop-agentic-sdlc-lab](https://github.com/alanblythe/workshop-agentic-sdlc-lab) *(Account Health Scorer + ADK Coder Agent)*
- **Guidance:**
  - Clone `https://github.com/alanblythe/antigravity-advanced-workshop-demos` locally and open its `README.md` / `DEMO_STEPS.md`.
  - Initialize a demo workspace with `./start_demo.sh <number>` (`1`–`9` or `201` on macOS/Linux/WSL; for `demo10-greenfield-spec-to-app` or Windows, copy `.seed/` into `workspace/`).
  - Good starting picks: `demo1` (`AGENTS.md`), `demo6` (linked ADRs), `demo7` (`/grill-me` -> TDD), `demo9` (adversarial review), or `demo10-greenfield-spec-to-app`.
