---
type: system-component
component: documentation
name: Signal-to-Action System README
version: 1.0.0
dependencies: []
related: [STRUCTURE.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Overview and quick start guide for the signal-to-action system
---

# Signal-to-Action System

Transform unstructured inputs into structured, evidence-backed artifacts using natural language recipes.

## What Is This?

The Signal-to-Action system (formerly "recipe system") is a repeatable framework for converting meeting transcripts, JIRA stories, specifications, and other unstructured inputs into actionable outputs with built-in traceability and governance.

## Quick Start

### 1. Run the Recipe

```bash
/run-recipe
```

Then provide:
- Source file (transcript, story, or spec)
- Output directory for artifacts
- Focus area (ux-xdr, security-tech, org-culture, other)

### 2. What You Get

The system generates these linked artifacts:

1. **Executive Summary** - Key takeaways with evidence citations [TS-n]
2. **Action Items** - Assignable work items linked to takeaways [AI-n]  
3. **Brainstorm** - Creative expansions using DCRL protocol
4. **Figma Screens** - UI inventory (when focus = ux-xdr)
5. **AI Design Prompts** - Tool-ready prompts (when focus = ux-xdr)

## Core Principles

### Evidence-First
Every claim traces back to source material with citations: `[filename:L123-L456 — Speaker Name]`

### Natural Language Processing
Instructions written for LLMs in plain markdown - no code required.

### Modular Components
Mix and match protocols, templates, and gates for different use cases.

### Built-in Governance
- Frontmatter tracks relationships and versions
- Citation format prevents hallucination
- Gates ensure appropriate processing

## System Architecture

```
signal-to-action/
├── core/                   # Main recipes and documentation
├── components/             # Modular pieces
│   ├── protocols/         # Evidence-First, DCRL
│   ├── templates/         # Artifact templates  
│   ├── gates/            # Decision points
│   └── extensions/       # Optional add-ons
├── commands/              # Slash command definitions
├── knowledge/             # Links to domain knowledge
└── reference/            # Specifications and conventions
```

## Data Organization

Keep system files separate from data:

```
/capturebox/data/signal-to-action/
├── raw-inputs/            # Source materials
├── processed-outputs/     # Generated artifacts
├── config/               # Workspace settings
├── archive/              # Historical data
└── workspace/            # Active projects
```

## Key Personas

The system optimizes for these security professionals:

- **SAM** - Security Analyst (primary)
- **REMI** - Incident Responder  
- **ALEX** - Security Architect
- **KIT** - IT Administrator
- **NIK** - Network Administrator

## Extending the System

### Add a Recipe Variant

1. Create new recipe in `core/recipes/`
2. Set `variant-of: main-recipe` in frontmatter
3. Define use case and modifications
4. Register any new commands

### Add a Protocol

1. Create protocol in `components/protocols/`
2. Document usage and examples
3. Update recipes that should use it

### Add a Template

1. Create template in `components/templates/`
2. Include frontmatter spec and examples
3. Link to relevant protocols

## Common Workflows

### Meeting to Actions
```
Source: meeting-transcript.vtt
Focus: ux-xdr
Output: Executive summary → Action items → Brainstorm
Time: ~20 minutes
```

### Story to Design
```
Source: JIRA-1234-story.md  
Focus: ux-xdr
Output: All artifacts including Figma screens
Time: ~30 minutes
```

### Spec to Technical Plan
```
Source: technical-spec.md
Focus: security-tech
Output: Summary → Action items → Worksheet
Time: ~15 minutes
```

## Best Practices

1. **Run Focus Gate first** - Saves time by determining relevance
2. **One topic per summary** - Use Topic Scope Gate to maintain focus
3. **Update action items** - They're living documents, unlike summaries
4. **Use appropriate lens** - Load only needed knowledge files
5. **Maintain citations** - Every claim needs evidence

## Troubleshooting

### Recipe takes too long
- Use lens packs to load only needed knowledge
- Run gates first to skip irrelevant processing
- Break large sources into topic-focused chunks

### Too many topics emerging
- Use Topic Scope Gate aggressively  
- Create separate summaries per topic
- Park non-urgent items explicitly

### Unclear focus area
- Default to `other` and let relevance guide
- Run full context lens pack
- Review output and re-run with better focus

## Getting Help

- **System documentation**: See `STRUCTURE.md`
- **Recipe details**: Read `core/recipe.md`
- **Component docs**: Check individual files in `components/`
- **Examples**: Look in `reference/` directory

## Version History

- v1.0.0 (2025-11-22): Initial systematization from recipe-files
