---
type: system-component
component: protocol
name: DCRL Protocol - Dual-Channel Recursion Lock
version: 1.0.0
dependencies: []
related: [evidence-first.md, recipe.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Creative constraint protocol for generating high-quality brainstorms and solutions
---

# DCRL — Dual‑Channel Recursion Lock (mini‑protocol)

A structured creative process that balances exploration with constraints to produce actionable outputs.

## Overview

Acceptance test (the lock): buildable ≤20 minutes, ≤3 assets, includes a light + a texture (adapt as needed), anchored to the motif/problem.

## Cycle Process

Repeat 2–3 times with adaptive termination:

1. **Channel A**: propose 3–5 micro‑specs (image‑first, verbs)
2. **Channel B**: select 1; add constraints (time, material, transformation) and a pass/fail test
3. **Channel A**: generate 2–3 variants against constraints
4. **Channel B**: converge to a make‑spec and commit

## Adaptive Termination Criteria

### Continue next cycle if:
- Channel A generated ≥2 meaningfully different variants
- Channel B constraints revealed new failure modes
- Make-spec still feels incomplete or untested

### Stop if:
- Variants are incremental tweaks only
- No new constraints discovered
- Clear winner emerged with solid make-spec

## Quality Gate

After cycle 2, ask: "Would I bet $100 this make-spec works?" 
- If no, run cycle 3
- If yes, stop

## DCRL Template

```markdown
### DCRL Cycle [N]

**Channel A seeds:** 
1. [Micro-spec 1 - image/verb focused]
2. [Micro-spec 2 - image/verb focused]
3. [Micro-spec 3 - image/verb focused]

**Channel B selection:** [Selected spec #] 

**Channel B constraints:** 
- Time: [constraint]
- Material: [constraint]
- Transformation: [constraint]
- Pass/Fail test: [specific test]

**Channel A variants:**
1. [Variant 1 against constraints]
2. [Variant 2 against constraints]
3. [Variant 3 against constraints]

**Cycle decision:** [Continue/Stop + reasoning]

**Make‑spec:**
- Title: [descriptive title]
- Materials (≤3): [list]
- Steps (≤5): [ordered list]
- Success test: [measurable outcome]
```

## Example Application

### DCRL Cycle 1

**Channel A seeds:**
1. Visual dashboard that pulses with threat severity
2. Conversational bot that learns analyst preferences
3. AR overlay for physical security monitoring

**Channel B selection:** #1 (Visual dashboard)

**Channel B constraints:**
- Time: Must load in <3 seconds
- Material: Use existing D3.js library only
- Transformation: Static data → animated insight
- Pass/Fail test: Junior analyst identifies critical threat in <10 seconds

**Channel A variants:**
1. Heat map with expanding ripples for new threats
2. Network graph where node size = severity, edges pulse with traffic
3. Timeline with threat cards that stack and color-code by type

**Cycle decision:** Continue - need more focus on analyst workflow

[Continue for 2-3 cycles total...]
