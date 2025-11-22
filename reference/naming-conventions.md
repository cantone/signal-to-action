---
type: system-component
component: reference
name: Naming Conventions
version: 1.0.0
dependencies: []
related: [frontmatter-spec.md, linkage-protocol.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: File naming standards and conventions for the signal-to-action system
---

# Naming Conventions

Consistent naming standards for files, directories, and identifiers in the signal-to-action system.

## General Principles

1. **ASCII-safe**: Use only ASCII characters for maximum compatibility
2. **Descriptive**: Names should clearly indicate content
3. **Consistent**: Follow patterns across similar files
4. **Sortable**: Include dates where appropriate for chronological ordering
5. **Unique**: Avoid naming collisions through systematic approaches

## System Component Naming

### Files in `/projects/systems/signal-to-action/`

Use lowercase with hyphens (kebab-case):
```
{component-type}-{descriptive-name}.md
```

Examples:
- `evidence-first.md` (protocol)
- `executive-summary.md` (template)
- `focus-gate.md` (gate)
- `run-recipe.md` (command)

### Special Cases
- Main recipe: Simply `recipe.md` (established convention)
- Index files: `index.md` in their directory
- Documentation: `README.md`, `STRUCTURE.md` (standard convention)

## Data Artifact Naming

### Pattern Components

```
{topic}-{date}-{artifact-type}.md
```

Where:
- `{topic}`: Kebab-case topic identifier (20-40 chars)
- `{date}`: ISO date format (YYYY-MM-DD)
- `{artifact-type}`: Artifact type identifier

### Artifact Type Identifiers
- `executive-summary`
- `action-items`
- `brainstorm`
- `figma-screens`
- `design-prompts`
- `worksheet`

### Examples
```
mobile-threat-dashboard-2025-11-20-executive-summary.md
api-versioning-strategy-2025-11-20-action-items.md
oauth2-implementation-2025-11-20-brainstorm.md
XDR-30117-dashboard-2025-11-22-figma-screens.md
```

## Screen and Component IDs

For Figma screens and UI components:

```
{STORY-ID}-{000n}-{brief-description}
```

Components:
- `{STORY-ID}`: JIRA story identifier (e.g., XDR-30117)
- `{000n}`: 4-digit sequence number (0001, 0002, etc.)
- `{brief-description}`: Kebab-case description (max 30 chars)

Constraints:
- Total length: <64 characters
- Use lowercase throughout
- Hyphens only (no underscores or spaces)

Examples:
```
XDR-30117-0001-threat-overview-panel
XDR-30117-0002-filter-dropdown
XDR-30117-0003-severity-indicator
```

## Directory Naming

### System Directories
Lowercase, single words or hyphenated:
```
core/
components/
protocols/
templates/
gates/
commands/
```

### Data Directories
Descriptive, hyphenated for multi-word:
```
raw-inputs/
processed-outputs/
jira-exports/
executive-summaries/
```

## Tag Identifiers

### In Executive Summaries
Takeaway tags: `[TS-n]` where n is sequential integer
```
[TS-1], [TS-2], [TS-3]...
```

### In Action Items  
Action tags: `[AI-n]` where n is sequential integer
```
[AI-1], [AI-2], [AI-3]...
```

### Rules
- Sequential within document
- No gaps in numbering
- Stable across versions
- Start at 1, not 0

## Citation Format

Standard citation: `[filename:Lstart–Lend — Speaker Name]`

Components:
- `filename`: Base filename without path
- `Lstart–Lend`: Line range with en-dash
- `Speaker Name`: Full name from source

Examples:
```
[meeting-transcript.vtt:L123–L145 — Jane Smith]
[XDR-30117-story.md:L23–L25 — Product Owner]
```

## Version Naming

### System Components
Semantic versioning: `major.minor.patch`
```
1.0.0 - Initial release
1.1.0 - Added new feature
1.1.1 - Fixed documentation
2.0.0 - Breaking changes
```

### Data Artifacts
Simple integers in frontmatter:
```
version: 1  # Initial
version: 2  # First update
version: 3  # Second update
```

## Special Characters

### Allowed
- Hyphen `-` for word separation
- Underscore `_` only in established names
- Numbers `0-9`
- Lowercase letters `a-z`

### Avoid
- Spaces (use hyphens)
- Special characters (@, #, $, %, etc.)
- Unicode characters
- Uppercase (except README.md, STRUCTURE.md)

## Topic Naming Guidelines

### Good Topics
Descriptive but concise:
```
mobile-threat-dashboard
api-versioning-strategy  
oauth2-implementation
incident-response-workflow
```

### Poor Topics
Too vague or too long:
```
meeting          # Too generic
stuff            # Non-descriptive
the-meeting-where-we-discussed-the-new-authentication-system  # Too long
ProjectX         # Unclear, mixed case
```

## Date Formats

Always use ISO format: `YYYY-MM-DD`
- In filenames: `2025-11-22`
- In frontmatter: `2025-11-22`
- In content: November 22, 2025 (spelled out)

## Case Consistency

| Context | Convention | Example |
| ------- | ---------- | ------- |
| System files | kebab-case | `evidence-first.md` |
| Data files | kebab-case | `threat-dashboard-2025-11-20-action-items.md` |
| Directories | kebab-case | `raw-inputs/` |
| Frontmatter keys | snake_case | `created_date` |
| Tag IDs | UPPERCASE-n | `[TS-1]`, `[AI-1]` |
| Screen IDs | kebab-case | `XDR-30117-0001-main-panel` |

## Anti-Patterns

### Don't Use
```
Executive Summary.md          # Spaces in filename
executive_summary.md          # Underscore when hyphen preferred  
ExecSummary.md               # CamelCase
exec-sum.md                  # Unclear abbreviation
executive-summary-v2.md      # Version in filename
executive-summary-FINAL.md   # Status in filename
```

### Do Use
```
executive-summary.md         # Standard component name
mobile-dashboard-2025-11-22-executive-summary.md  # Standard artifact name
```

## Migration from Old Names

When migrating existing files:

1. Rename to match conventions
2. Preserve original name in frontmatter if needed:
   ```yaml
   original_filename: "Old Name With Spaces.md"
   ```
3. Create redirects or aliases if referenced elsewhere
4. Update any hardcoded references

## Automation Support

Names should support:
- Glob patterns: `*-executive-summary.md`
- Date extraction: Parse YYYY-MM-DD from filename
- Type detection: Identify artifact from suffix
- Sorting: Chronological or alphabetical
- Searching: Meaningful keywords in names
