---
type: system-component
component: command
name: Run Recipe Command
version: 1.2.0
dependencies: [recipe.md, protocols/evidence-first.md, protocols/dcrl.md, templates/executive-summary.md, templates/action-items.md, knowledge/index.md]
related: [index.md]
parent: signal-to-action-system
created: 2025-10-30
updated: 2025-11-22
maintainer: capturebox-team
description: Primary command to execute the signal-to-action recipe workflow
---

/SLASH-COMMAND: /run-recipe

DESCRIPTION:
Execute the Solutions Recipe system. Transform unstructured input (meeting transcripts, design artifacts, brainstorming notes, specs, scenarios, JIRA stories via MCP) into structured, evidence-backed artifacts.

This recipe system is built to handle and transform a wide range of input types—including direct JIRA story 
fetching via MCP integration. For JIRA stories, simply provide the URL (e.g., https://cisco-sbg.atlassian.net/browse/XDR-XXXXX) 
and the system will automatically fetch and process with UX-centric filtering. For best results, always clarify 
what the input is, what format it's in, and what the user's end goal or problem is. Leverage the knowledge file list 
(domain briefs, personas, UX guides, etc.) as reference points for context and rigor when analyzing material or 
drafting outputs. Use this system as both a flexible creative tool for design thinking and a framework for 
tactical decision-making; asking clarifying questions up front leads to quality results.

AVAILABLE ARTIFACTS:
- Executive Summary (10-15 takeaways with evidence citations)
- Action Items (owners, impact, priority)
- Brainstorm (using DCRL: Dual-Channel Recursion Lock)
- Speakers List (attributed, timestamped)
- Optional: Figma Screens + AI Design Prompts
- Optional: Worksheet (problem/solution analysis)
- Optional: Role-play (dialogue-based exploration)

ACTION:
1. Ask clarifying questions: input type, format, context, end goal
2. Generate first two core artifacts (Executive Summary + Action Items)
3. Pause for refinement direction
4. Proceed iteratively or generate optional artifacts as needed

BEHAVIOR:
- Evidence-first: Every claim cites source (filename, line range, speaker)
- DCRL cycles: Channel A (creative seeds) vs. Channel B (constraints); 2-3 iterations
- Focus gate: Classify input (ux-xdr | security-tech | org-culture | other)
- Frontmatter on all outputs (type, topic, source, date, scope, version)

REFERENCE:
- Core Recipe: /projects/systems/signal-to-action/core/recipe.md
- Recipe Summary: /projects/systems/signal-to-action/core/recipe-summary.md
- Templates: /projects/systems/signal-to-action/components/templates/
- Protocols: /projects/systems/signal-to-action/components/protocols/
- Knowledge: /projects/systems/signal-to-action/knowledge/index.md

GUARDRAILS:
- No orphaned claims; mark inferences vs. facts
- Citation format: [filename:Lstart-Lend — Speaker]
- Don't let perfect be the enemy of good for low-fidelity outputs
- Request clarification to improve accuracy