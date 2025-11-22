---
type: system-component
component: core
name: Recipe Overview - What It Does and How
version: 1.0.0
dependencies: [recipe.md]
related: [recipe.md, meta-recipe.md, recipe-summary.md]
parent: signal-to-action-system
created: 2025-10-15
updated: 2025-11-22
maintainer: capturebox-team
description: Comprehensive overview of recipe functionality and workflow
---

Your recipe is a repeatable framework to turn any meeting transcript or product artifact into
actionable outputs and creative fuel, with built‑in governance and traceability for XDR/UX work.

## What it does

- **Purpose**: Convert inputs (transcripts, JIRA stories, specs) into executive summaries, action
  items, brainstorms, and optional UX design outputs.
- **Outputs**: Executive summary, action items, brainstorm, worksheet, optional Figma screens, AI
  design prompts.
- **Traceability**: Enforces evidence‑first citations, TS-n (takeaways) → AI-n (actions) linkage,
  and rollup conventions.

## Core flow (end‑to‑end)

1. **Collect inputs**
   - Pull from specified knowledge docs under `knowledge/` and the source artifact.
2. **Extract high‑signal summary**
   - Create executive summary (`<TOPIC><date>-executive-summary.md`), focused on outcomes,
     decisions, open questions.
3. **Scope & Focus gates**
   - Focus Gate (domain focus + XDR relevance).
   - Topic Scope Gate (primary topic vs parking lot).
4. **Choose context block**
   - UX Problem Snapshot (if focus = ux-xdr) or Domain Brief (otherwise).
   - Add XDR Relations and optional Scenarios when helpful.
5. **Convert to action items**
   - Action items list with citations, owners, acceptance (optional), impact, dependencies.
   - Each action references at least one TS-n. Output `<TOPIC>-<date>-action-items.md`.
6. **Prepend stakeholders/roles**
   - Infer/mark explicit vs inferred roles.
7. **Derivative brainstorm (DCRL-driven)**
   - Big swings + constraints/tests; produce `<TOPIC>-<date>-brainstorm.md>`.
8. **Optional prioritization & ad‑hoc worksheet**
   - Role‑play prioritization and a structured worksheet for problem/solution.
9. **UX design additions (when focus = ux-xdr)**
   - Figma screens inventory → AI design prompts; maintain screen IDs and traceability.
10. **Hygiene & governance**

- Consistent YAML frontmatter, naming, daily governance touch, deliverables checklist.

## Required frontmatter (by artifact)

- **Executive summary**
  - Fields: type, topic, source, created (source date), scope, audience, polish, version.
- **Action items**
  - Fields: type, topic, source, created (source date), scope, rollup_of (optional), version.
- **Brainstorm**
  - Fields: type, topic, seed (path to action-items), created (seed date), scope, version.
- **Figma screens**
  - Fields: type, topic, source, created, fidelity, scope, version.
- **AI design prompts**
  - Fields: type, topic, source (figma screens), created, target_tools, fidelity, version.

## Key protocols and safeguards

- **Evidence‑First (AI Drift Defense)**
  - Every claim is anchored to citations `[filename:Lstart–Lend — Speaker]`.
  - Distinguish quotes vs inference; add timestamps and verification checkpoints.
- **Cognitive Integrity Safeguards**
  - Partition Source vs Analysis vs Industry knowledge.
  - Confidence labels; anti‑drift tripwires; abort/revise warning signs.
- **Security Domain Traceability**
  - Flag security terms; preserve exact terminology; tag assumptions; keep threat/compliance context
    intact.

## XDR relations and scenarios

- **XDR Relations**: Bridge type (concept/process/data/system), impact to XDR, assumptions,
  evidence.
- **Scenarios**: Primary/Edge/Failure; use when unknowns affect behavior or correctness.

## DCRL (Dual‑Channel Recursion Lock)

- **Cycle**: A (generate 3–5 micro‑specs) ↔ B (add constraints/tests) → converge to make‑spec in ≤3
  cycles.
- **Acceptance**: Buildable ≤20 min, ≤3 assets, anchored to the problem.

## File hygiene and naming

- **Naming**: ASCII‑safe; date‑stamp; include YAML frontmatter.
- **Session outputs**:
  - Executive summary: `<Topic><YYYY-MM-DD>-executive-summary.md`
  - Action items: `<Topic>-<YYYY-MM-DD>-action-items.md`
  - Brainstorm: `<Topic>-<YYYY-MM-DD>-brainstorm.md`
- **No TS→AI trace maps** in summaries (linkage is enforced in actions, not mapped visually).

## UX design extensions (when applicable)

- **Figma screens inventory**
  - Screen IDs: `{STORY-ID}-{000n}-{brief-description}` (kebab-case, ≤64 chars).
  - Map flows, constraints, success metrics; trace to [AI-n].
- **AI design prompts**
  - Generate prompts for Figma Make, v0, Cursor; prioritize speed/structure over polish; retain
    screen IDs.

## Deliverables checklist

- **Speakers/roles overview**
- **Top takeaways**
- **Action items with citations**
- **DCRL brainstorm**
- **Optional role‑play prioritization**
- **Worksheet**
- **Figma screens** (UX focus)
- **AI design prompts** (UX focus)

## Practical quick start

- **Step 1**: Run Focus Gate + Topic Scope Gate.
- **Step 2**: Write executive summary with citations and TS-n markers.
- **Step 3**: Produce action items with owners, acceptance (as needed), and evidence; reference
  TS‑n.
- **Step 4**: Prepend stakeholders/roles; then create brainstorm seeded by action items (DCRL).
- **Step 5**: If UX: generate Figma screens inventory → AI design prompts.
- **Step 6**: Ensure YAML frontmatter and naming; log daily governance; check deliverables list.
