---
type: system-component
component: reference
name: Frontmatter Specification
version: 1.0.0
dependencies: []
related: [naming-conventions.md, linkage-protocol.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Complete specification for frontmatter across all system components and artifacts
---

# Frontmatter Specification

Comprehensive guide to frontmatter requirements for system components and data artifacts.

## Overview

Frontmatter provides structured metadata that enables:
- Component discovery and relationships
- Version tracking and maintenance
- Automated processing and validation
- Clear separation of system vs. data

## System Component Frontmatter

All files in `/projects/systems/signal-to-action/` must include:

```yaml
---
type: system-component
component: core|protocol|template|gate|extension|command|documentation|reference|knowledge-index
name: <human-readable name>
version: <major.minor.patch>
dependencies: [<list of required components>]
related: [<list of related components>]
parent: <parent component or system>
created: YYYY-MM-DD
updated: YYYY-MM-DD
maintainer: <team or person>
description: <one-line description>
---
```

### Field Definitions

#### `type` (required)
Always `system-component` for system files.

#### `component` (required)
Component category:
- `core` - Main recipes and variants
- `protocol` - Processing protocols (Evidence-First, DCRL)
- `template` - Artifact templates
- `gate` - Decision gates
- `extension` - Optional add-ons
- `command` - Slash command definitions
- `documentation` - README, guides
- `reference` - Specifications like this file
- `knowledge-index` - Knowledge resource mappings

#### `name` (required)
Human-readable name, used in documentation and discovery.

#### `version` (required)
Semantic versioning (major.minor.patch):
- Major: Breaking changes
- Minor: New features, backward compatible
- Patch: Bug fixes, documentation updates

#### `dependencies` (required)
Array of components this file requires. Use exact names from other components' `name` field. Empty array `[]` if no dependencies.

#### `related` (required)
Array of components that are related but not required. Helps with discovery and navigation.

#### `parent` (required)
The parent system or component. Usually `signal-to-action-system` for top-level components.

#### `created` (required)
ISO date when component was first created.

#### `updated` (required)
ISO date of last significant update.

#### `maintainer` (required)
Team or person responsible for this component.

#### `description` (required)
One-line description for indexes and summaries.

### Additional Fields for Variants

Recipe variants include extra fields:

```yaml
variant-of: main-recipe
variant-type: specialized|simplified|extended
use-case: <specific use case description>
```

## Data Artifact Frontmatter

Files in `/capturebox/data/signal-to-action/` use artifact-specific frontmatter.

### Executive Summary

```yaml
---
type: executive-summary
topic: <Topic — YYYY-MM-DD>
source: <filename.ext>
created: <YYYY-MM-DD>  # Source artifact date
scope: meeting|story|spec
audience: me|team|leadership
polish: scratch|team-ready|leadership-ready
version: 1
---
```

#### Field Definitions

- `type`: Always `executive-summary`
- `topic`: Human-readable topic with date
- `source`: Original source filename
- `created`: Date of source artifact (not summary creation)
- `scope`: Source type classification
- `audience`: Intended readers
- `polish`: Edit/review status
- `version`: Iteration number (summaries are snapshots)

### Action Items

```yaml
---
type: action-items  
topic: <Topic — YYYY-MM-DD>
source: <filename.ext>
created: <YYYY-MM-DD>  # Source artifact date
scope: meeting|story|spec
rollup_of: [<YYYY-MM-DD>, ...]  # Optional
version: 1  # Increments with updates
---
```

#### Additional Fields

- `rollup_of`: Array of dates when combining multiple sessions

### Brainstorm

```yaml
---
type: brainstorm
topic: <human-readable title>
seed: </path/to/action-items.md>
created: <YYYY-MM-DD>  # Seed artifact date
scope: meeting|story|spec
version: 1
---
```

#### Unique Fields

- `seed`: Path to action items that seeded this brainstorm

### Figma Screens

```yaml
---
type: figma-screens
topic: <Topic — YYYY-MM-DD>
source: <action-items-file.md>
created: <YYYY-MM-DD>
fidelity: low|medium|high
scope: story|epic
version: 1
---
```

#### Unique Fields

- `fidelity`: Design detail level
- `scope`: Usually story or epic level

### AI Design Prompts

```yaml
---
type: design-prompts
topic: <Topic — YYYY-MM-DD>
source: <figma-screens-file.md>
created: <YYYY-MM-DD>
target_tools: [figma-make, v0, cursor]
fidelity: low|medium|high
version: 1
---
```

#### Unique Fields

- `target_tools`: AI tools these prompts target

## Validation Rules

### Required Fields
Every frontmatter block must have:
- `type` - Identifies system component vs. data artifact
- `created` - Enables temporal tracking
- `version` - Supports iteration

### Type-Specific Requirements
Each `type` value enforces specific required fields:
- System components need full metadata
- Data artifacts need source tracking
- Living documents need version management

### Format Requirements
- Dates: ISO format (YYYY-MM-DD)
- Versions: Semver for system, integers for data
- Arrays: Square brackets, comma-separated
- Paths: Relative to workspace root

## Examples

### System Component Example

```yaml
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
description: AI Drift Defense and Human Learning protocol
---
```

### Data Artifact Example

```yaml
---
type: executive-summary
topic: Mobile Threat Dashboard Redesign — 2025-11-20
source: design-review-meeting.vtt
created: 2025-11-20
scope: meeting
audience: team
polish: team-ready
version: 1
---
```

### Variant Example

```yaml
---
type: system-component
component: core
name: Quick Recipe - 5-Minute Version
version: 1.0.0
dependencies: [recipe.md, protocols/evidence-first.md]
related: [recipe.md]
parent: recipe.md
variant-of: main-recipe
variant-type: simplified
use-case: Time-constrained analysis needing just key takeaways
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Simplified recipe for quick processing
---
```

## Migration Guide

When moving files into the system:

1. Determine if it's system or data
2. Add appropriate frontmatter type
3. Fill required fields for that type
4. Set version to 1.0.0 (system) or 1 (data)
5. Use current date for `updated`
6. Preserve original `created` if known

## Tooling Support

Frontmatter enables:
- Automated dependency checking
- Version compatibility validation
- Component discovery and indexing
- Relationship graphing
- Update tracking
