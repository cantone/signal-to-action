---
type: system-component
component: protocol
name: Evidence-First Protocol
version: 1.0.0
dependencies: []
related: [dcrl.md, recipe.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: AI Drift Defense and Human Learning Amplification protocol for maintaining source integrity
---

# Evidence-First Protocol (AI Drift Defense & Human Learning)

A critical protocol for maintaining integrity and preventing hallucination in AI-assisted artifact generation.

## Drift Defense Mechanisms

- **Source anchoring:** Every synthesis claim traces back to specific transcript segments with line numbers
- **Attribution clarity:** Distinguish between "Speaker X said Y" vs "Inferred from Speaker X's context about Y"
- **Temporal markers:** Include creation timestamps and source file dates to track content aging
- **Verification checkpoints:** Flag any statement that can't be cross-referenced to original source

## Human Learning Amplification

- **Contextual bridging:** When referencing industry patterns, explicitly connect to specific meeting moments that triggered the insight
- **Reasoning exposition:** Show the logical path from transcript observation → analysis → broader implication
- **Knowledge scaffolding:** Include "Why this matters" sections that help readers understand the significance of technical details
- **Pattern highlighting:** When similar themes appear across multiple transcript sections, create explicit cross-references

## Learning-Oriented Section Headers

Use learning-focused headers throughout your documents:

- "Key Technical Decisions and Their Implications"
- "Emerging Patterns and What They Reveal"
- "Critical Gaps and Why They Matter"
- "Cross-Reference Insights" (for recurring themes)

## Enhanced Citation Format (canonical)

Use this inline form by default: `[filename:Lstart–Lend — Speaker]` (filename only; avoid absolute paths in published artifacts). Reserve fenced quotes for >3 lines or contentious claims.

### Citation Examples

**Inline citation (preferred):**
```
The team decided to prioritize mobile-first design [meeting-transcript.vtt:L245-L250 — Jane Smith].
```

**Fenced quote (for longer excerpts):**
```
```245:250:meeting-transcript.vtt — Jane Smith
I think we need to completely rethink our approach here. The mobile
experience is where 80% of our users interact with the system, yet
we're still designing desktop-first and trying to make it responsive.
We should flip this around entirely.
```

## Implementation Checklist

- [ ] Every claim has a source citation
- [ ] Inferences are clearly marked as such
- [ ] Timestamps and dates are preserved
- [ ] Cross-references connect related insights
- [ ] "Why this matters" context is provided
- [ ] Attribution distinguishes quotes from interpretation
