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

A survival toolkit for the sole UX resource on massive enterprise projects - transform unstructured inputs into structured, evidence-backed artifacts using natural language recipes.

## What Is This?

The Signal-to-Action system (formerly "recipe system") was created out of necessity. When you're the only UX person supporting hundreds of engineers across a complex platform, you need systems that scale your impact. This framework converts meeting transcripts, JIRA stories, specifications, and other unstructured inputs into actionable outputs with built-in traceability and governance.

It's designed for reality: too many meetings, not enough time, constant context switching, and the need to maintain quality while moving fast.

## Why This Exists

**The Problem**: You're the sole UX resource on a project with:
- Hundreds of engineers needing design support
- Multiple teams running in parallel
- Daily meetings that generate hours of discussion
- Constant requests to "do more with less"
- No time to document decisions properly
- Colleagues equally overwhelmed, minimal bandwidth to help

**The Solution**: This system acts as a force multiplier, enabling one person to:
- Process meetings 5-10x faster
- Maintain consistent quality across all outputs
- Build traceable decision history
- Scale influence across multiple teams
- Reduce cognitive load through systematization

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

### UX-Centric Hierarchy
The system maintains clear information hierarchy:
- **Primary**: UX decisions, user needs, design rationale
- **Supporting**: Technical constraints, implementation details
- **Background**: Framework specifics, data structures, APIs

This filtering allows you to stay focused on design work while processing technical discussions.

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
- UX focus maintained through structured templates

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

### Meeting to Actions (UX-Focused)
```
Source: meeting-transcript.vtt
Focus: ux-xdr
Output: Executive summary → Action items → Brainstorm
Result: UX decisions elevated, technical details relegated to context
Time: ~20 minutes
```

### Story to Design
```
Source: JIRA-1234-story.md  
Focus: ux-xdr
Output: All artifacts including Figma screens
Result: User flows prioritized over implementation details
Time: ~30 minutes
```

### Technical Meeting with UX Impact
```
Source: architecture-review.vtt
Focus: ux-xdr (even though it's a technical meeting)
Output: UX-relevant decisions extracted from technical discussion
Result: Stay focused on user impact, not database schemas
Time: ~20 minutes
```

### Spec to Technical Plan
```
Source: technical-spec.md
Focus: security-tech
Output: Summary → Action items → Worksheet
Result: Technical focus maintained when UX not primary
Time: ~15 minutes
```

## Best Practices for Solo Practitioners

1. **Run Focus Gate first** - Every minute counts when you're supporting hundreds
2. **Set focus to `ux-xdr` liberally** - Even technical meetings often have UX implications
3. **One topic per summary** - Ruthlessly defer non-critical items with Topic Scope Gate
4. **Update action items** - They're living documents that track your commitments
5. **Use lens packs** - Don't load everything; your cognitive bandwidth is precious
6. **Maintain citations** - You WILL be asked "why did we decide this?" months later
7. **Batch similar inputs** - Process all weekly sync meetings together
8. **Template everything** - If you do it twice, it needs a template
9. **Park strategically** - Not everything needs immediate attention
10. **Filter aggressively** - Let technical details stay in the background

### Maintaining UX Focus

When processing any input:
- **Always ask**: "What's the user impact?"
- **Extract UX decisions** even from technical discussions
- **Mark technical details** as supporting context, not primary content
- **Stay in design mode** - don't get pulled into implementation debates
- **Use the hierarchy**: User needs → Design decisions → Technical constraints

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
