
---
type: system-component
component: core
name: Recipe Summary - TLDR Version
version: 1.0.0
dependencies: [recipe.md]
related: [recipe.md, meta-recipe.md, overview-of-recipe.md]
parent: signal-to-action-system
created: 2025-09-30
updated: 2025-11-22
maintainer: capturebox-team
description: Concise summary of the signal-to-action pipeline recipe
audience: anyone
---

## TLDR: recipe.md

**Purpose**: Repeatable workflow to transform meeting transcripts, JIRA stories, and specs into structured, evidence-backed action artifacts for XDR UX work.

**Input → Output Pipeline**:
1. **Source** (transcript/story/spec) → **Executive Summary** (10-15 takeaways tagged `[TS-n]`)
2. Executive Summary → **Action Items** (with owners, evidence, impact; tagged `[AI-n]`)
3. Action Items → **Brainstorm** (using DCRL: Dual-Channel Recursion Lock)
4. Optional: **Figma Screens** + **AI Design Prompts** (when focus = ux-xdr)
5. Optional: **Worksheet** (problem/solution analysis)

**Core Protocols**:
- **Evidence-First**: Every claim cites source (line numbers, speakers, timestamps)—anti-hallucination defense
- **DCRL (Dual-Channel Recursion Lock)**: Channel A = creative seeds; Channel B = constraints/tests; 2-3 cycles to converge
- **Focus Gate**: Classify as ux-xdr | security-tech | org-culture | other
- **Analysis Levels**: L0 (skim), L1 (triage—default), L2 (mini-argument)

**Key Personas**: SAM (Security Analyst), REMI (Incident Responder), ALEX (Architect), KIT (IT Admin), NIK (Network Admin)

**Quality Guardrails**:
- Frontmatter (type, topic, source, date, scope, version) on all artifacts
- Citation format: `[filename:Lstart-Lend — Speaker]`
- No orphaned claims; trace maps optional (default off, separate artifact if enabled); mark inferences vs. facts
- "Don't let perfect be the enemy of good" for low-fidelity outputs

**Deliverables**: Speakers list, takeaways, action items, brainstorm, optional role-play/worksheet, optional Figma screens + prompts—all Markdown, evidence-linked, timestamped.