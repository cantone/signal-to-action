---
type: system-component
component: core
name: Meta Recipe Documentation
version: 1.0.0
dependencies: [recipe.md]
related: [recipe.md, recipe-summary.md, overview-of-recipe.md]
parent: signal-to-action-system
created: 2025-10-30
updated: 2025-11-22
maintainer: capturebox-team
description: High-level overview of recipe mechanics and adaptation guidelines
---

I'll open your `recipe.md` to extract its structure and key mechanics, then produce a concise meta-summary with how it works, why, and how to adapt it to other scenarios.

[1 tool called]

I scanned your `recipe.md` and pulled out the mechanics, guardrails, and how to adapt it to new contexts. Now I’ll give you a concise meta‑summary you can reuse for your narrative.

### What this recipe is
- A repeatable, evidence‑first workflow to convert any source artifact (meeting transcript, JIRA story, PRD/spec) into a small set of linked outputs: executive summary → action items → derivative brainstorms → optional role‑play priorities → UX artifacts (Figma inventory, AI design prompts) → worksheet.
- It’s opinionated about structure, traceability, and drift defense so outputs stay accountable and reusable across teams.

### How it works (end‑to‑end flow)
- Collect inputs: point to the source artifact and domain knowledge bundle; set a workspace target.
- Extract high‑signal summary: produce an executive summary with a Focus Gate, Topic Scope Gate, optional UX Snapshot/Domain Brief, XDR Relations, and optional scenarios; stamp YAML frontmatter; tag takeaways as TS‑n.
- Convert to action: translate takeaways to assignable action items (AI‑n) with explicit owners, focus, optional acceptance and impact, and mandatory inline evidence citations; enforce TS‑n ↔ AI‑n linkage.
- Add stakeholders/roles: infer and mark explicit vs inferred roles.
- Evidence‑first guardrails: apply drift‑defense, learning amplification, learning‑oriented headers, and canonical inline citation format.
- Synthesis rigor: choose an analysis level (L0/L1/L2), run the quality checklist, type contradictions and unknowns, and label confidence.
- Security traceability (when relevant): flag terms, preserve domain boundaries, and mark assumptions.
- Derivatives: seed a DCRL‑driven brainstorm, optionally run role‑play prioritization, and create an ad‑hoc worksheet for decisions.
- UX‑specific outputs (when focus = ux‑xdr): generate Figma screen inventory (with canonical IDs) and AI design prompts; maintain traceability from AI‑n → screens → prompts.
- Hygiene and governance: consistent headers, frontmatter, naming, and a deliverables checklist; maintain action items as the single source of execution truth.

### Why it works (design principles)
- Evidence over assertion: every claim links to source lines; analysis vs inference vs industry context are separated.
- Learning‑first structure: headers and templated sections force explicit “why it matters,” impacts, and next tests.
- Accountability through linkage: TS‑n tags roll forward into AI‑n; action items become the operational backbone.
- Anti‑drift mechanisms: confidence labels, quote accuracy, scope limiting, and warning‑sign aborts.
- Bias to progress: DCRL enforces small, buildable cycles with a quality gate; iteration policy keeps summaries stable and actions living.

### The artifacts and their roles
- Executive summary: snapshot for leadership and alignment; no execution details.
- Action items: operational source of truth; owns status, owners, acceptance, and evidence.
- Brainstorm (DCRL): idea generation constrained by evidence and tests; never back‑propagates into summaries.
- Role‑play prioritization: rapid prioritization via personas and constrained choices.
- Figma inventory and AI prompts: low‑fidelity, traceable UX deliverables derived from action items.
- Worksheet: compact decision record for options/tradeoffs.

### How to adapt it to other scenarios
- Non‑security domains: swap the “XDR Relations” section for domain‑specific relations; keep the same Focus/Scope gates and evidence standards.
- Engineering RFCs/architecture reviews: emphasize “Constraints/Risks,” “Contradictions & Gaps,” and “Technical Term Flagging”; keep TS‑n/AI‑n linkage to decisions and experiments.
- Product discovery: use “Scenarios” and L2 mini‑arguments more; capture unknowns with owners/timeframes; brainstorm turns into hypothesis backlogs.
- Incident postmortems: keep the executive summary short, expand “Evidence‑First” and “Security Context Preservation,” and bias AI‑n toward preventive controls and telemetry.
- Research spikes: privilege confidence labels and “Industry Partition”; require verified URLs for external claims; treat outputs as time‑boxed learning assets.

### Minimal steps to make it work (portable checklist)
- Define source + frontmatter: set type/topic/source/created/scope/version.
- Run Focus Gate + Topic Scope Gate: declare focus and relevance; split topics if needed.
- Capture TS‑n: 10–15 high‑signal takeaways with explicit confidence labels.
- Create AI‑n: one outcome per item with owners, focus, and inline evidence; reference TS‑n.
- Choose analysis level and apply quality checklist; type contradictions/unknowns and assign follow‑ups.
- If UX: generate Figma inventory (canonical IDs) and AI design prompts; link back to AI‑n.
- Brainstorm via DCRL; stop after a clear make‑spec passes the quality bet test.
- Name, date, and store consistently; keep action items living, summaries snapshot‑only.

Status: I reviewed your `recipe.md` and distilled its purpose, flow, guardrails, and adaptation patterns into a concise narrative.

Let’s get you moving fast with slash commands, then map them to your recipe.md workflow.

### What are Cursor slash commands?
Type “/” in the Chat (or Command Palette) to trigger purpose-built actions that use current context (selection, open files, diffs, tests, terminal). Most commands work best when:
- You select code/text in the editor first
- You have relevant files open
- You give a short, outcome-focused instruction

Common, high-signal commands:
- /edit: Apply an instruction to selected text/code
- /fix: Repair errors in the selection or current file
- /review: Review a diff or a file and suggest improvements
- /doc: Generate docstrings/comments for selected code or file
- /test: Create or update tests for selected code/file
- /commit: Propose a conventional commit message from current changes
- /optimize: Improve performance/readability for selected code
- /explain: Explain selected code or errors
- /terminal: Open a non-interactive shell command (for quick runs)
- /summarize: TL;DR of a file or selection
- /plan: Create a task breakdown before edits

Tip: For /edit, always select the target content first in the editor, then run the command with a clear instruction.

### How to use them with your recipe.md workflow
Your recipe.md likely has stages. Here’s a practical mapping you can reuse each session.

- Discovery/Scope
  - Select the “Goal” or “Scope” section in `recipe.md`, then:
    - /summarize: “Turn this into 3 crisp bullets and one acceptance criterion.”
    - /plan: “Create a 5–7 step plan with clear deliverables from this scope.”

- Inputs and Constraints
  - Select the “Inputs” section:
    - /edit: “Normalize into a checklist; add missing inputs you infer.”
  - Select “Constraints”:
    - /edit: “Convert to MUST/SHOULD/COULD; remove duplicates.”

- Implementation Template
  - Select a step block to transform:
    - /edit: “Rewrite this step using imperative voice, ‘Do X to achieve Y,’ max 4 sentences.”
    - /doc: “Generate a one-paragraph rationale for this step.”

- Execution
  - For code changes referenced by a step:
    - Select the target code in editor → /edit: “Apply these changes per Step N in recipe.md.”
    - If tests are in scope: /test: “Generate missing table-driven tests for this function per Step N.”

- Validation
  - Select validation criteria in `recipe.md`:
    - /edit: “Convert to precise, verifiable checks. Include pass/fail examples.”
  - After changes:
    - /review: “Review diffs for alignment with acceptance criteria.”

- Remediation
  - If diagnostics appear:
    - Select the error block or file → /fix: “Resolve these lints without changing public API.”

- Documentation
  - Select a function or module:
    - /doc: “Add docstrings following Google style. Include examples if helpful.”
  - For `recipe.md` itself:
    - /summarize: “Create a 5-line executive summary of this recipe.”

- Commit
  - With changes staged or in working tree:
    - /commit: “Conventional commit message summarizing changes by feature and scope.”

### Concrete examples for your current file
In `recipe-files/recipes/recipe.md`:
- For the section around line ~265 (your cursor point), select that block and run:
  - /edit: “Reformat as a numbered procedure. Each step starts with a verb. Preserve content.”
  - /plan: “Extract this into 6 actionable tasks with acceptance checks.”
  - /summarize: “Create a one-screen TL;DR for stakeholders.”

- To turn a “Checklist” subsection into a crisp, testable list:
  - Select the checklist → /edit: “Rewrite as GIVEN/WHEN/THEN bullets; remove ambiguous phrasing.”

- To keep the recipe consistent:
  - Select the full file in editor (Cmd+A) → /review: “Enforce consistent headings, tense, and list styles. Don’t remove substance.”

### Pro tips
- Be specific: “Rewrite as 6 steps max,” “Keep code blocks unchanged,” “Don’t alter URLs.”
- Use selections: Slash commands respect the selected text/file. Target precisely.
- Iterate quickly: Run /edit, skim the diff, adjust instruction, re-run.
- Chain commands: /plan → /edit → /review → /commit is a fast loop.

If you want, tell me the intent of the section at line ~265 and I’ll give you an exact /edit instruction to paste.