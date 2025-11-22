---
type: system-component
component: reference
name: Linkage Protocol Specification
version: 1.0.0
dependencies: []
related: [frontmatter-spec.md, naming-conventions.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Specification for linking takeaways to action items and maintaining traceability
---

# Linkage Protocol Specification

Rules and standards for maintaining traceable links between artifacts in the signal-to-action pipeline.

## Overview

The linkage protocol ensures every action item traces back to evidence through a chain of tagged references:

```
Source Material → [TS-n] Takeaways → [AI-n] Action Items → Derivatives
```

## Core Principles

1. **No Orphans**: Every action item must link to at least one takeaway
2. **Bidirectional**: Links work forward (TS→AI) but not backward
3. **Stable IDs**: Tags remain constant across versions
4. **Evidence Chain**: Full traceability to original source
5. **No Visual Maps**: Linkages are inline, not separate diagrams

## Tag Specifications

### Takeaway Tags [TS-n]

Used in Executive Summaries to mark key takeaways.

**Format**: `[TS-n]` where n is a sequential integer starting at 1

**Placement**: At the end of each takeaway line

**Example**:
```markdown
1. Team agreed to prioritize mobile-first design approach [TS-1]
2. Budget constraints limit hiring to 2 engineers, not 5 [TS-2]
3. Security review process is primary blocker for releases [TS-3]
```

**Rules**:
- Sequential numbering (no gaps)
- Numbers don't change if takeaways are reordered
- One tag per takeaway
- Format: Square brackets, TS in caps, hyphen, number

### Action Item Tags [AI-n]

Used in Action Items to identify each actionable work item.

**Format**: `[AI-n]` where n is a sequential integer starting at 1

**Placement**: At the end of the action item description line

**Example**:
```markdown
1. Create mobile-first wireframes for threat dashboard [AI-1]
   **Owners**: Jane Smith, Tom Rodriguez
   **Focus**: Convergence
   **Evidence**: [meeting-20251122.vtt:L245-L260 — Jane Smith][TS-1]
```

**Rules**:
- Sequential numbering within document
- Stable across versions (don't renumber)
- One tag per action item
- Must include Evidence field with [TS-n] reference

## Linkage Requirements

### Mandatory Links

Every action item MUST include:
1. Its own `[AI-n]` tag
2. At least one `[TS-n]` reference in Evidence field
3. At least one source citation

**Format**:
```markdown
**Evidence**: [filename:Lstart-Lend — Speaker][TS-n]
```

### Multiple References

Action items can reference multiple takeaways:
```markdown
**Evidence**: [transcript.vtt:L100-L120 — PM][TS-1][TS-3][TS-7]
```

### Cross-Document References

When action items combine multiple sessions:
```yaml
---
rollup_of: [2025-11-20, 2025-11-18, 2025-11-15]
---
```

Reference format includes date:
```markdown
**Evidence**: [meeting-20251120.vtt:L50-L60 — Lead][TS-1-20251120]
```

## What NOT to Do

### No Trace Maps

Do NOT create visual maps like this:
```markdown
### Trace Map
TS-1 → AI-1, AI-3
TS-2 → AI-2
TS-3 → AI-1, AI-4
```

These are explicitly prohibited to reduce maintenance burden.

### No Backward References

Executive Summaries should NOT reference action items:
```markdown
❌ Bad: Key decision on auth flow [TS-3] (see AI-1 for implementation)
✅ Good: Key decision on auth flow [TS-3]
```

### No Orphaned Items

Never create action items without takeaway references:
```markdown
❌ Bad:
1. Implement caching layer [AI-1]
   **Evidence**: [meeting.vtt:L200-L210 — Architect]

✅ Good:  
1. Implement caching layer [AI-1]
   **Evidence**: [meeting.vtt:L200-L210 — Architect][TS-4]
```

## Evidence Chain Example

### 1. Source Material
```
meeting-transcript.vtt:
L245: Jane: "We really need to flip this around and go mobile-first"
L246: Jane: "80% of our users are on mobile but we design for desktop"
```

### 2. Executive Summary
```markdown
### Top Takeaways
1. Mobile usage is 80% but design process is desktop-first [confidence: Confirmed] [TS-1]
```

### 3. Action Items  
```markdown
1. Redesign workflow to be mobile-first [AI-1]
   **Owners**: Jane Smith, Design Team
   **Evidence**: [meeting-transcript.vtt:L245-L246 — Jane Smith][TS-1]
```

### 4. Brainstorm (derivative)
```markdown
### Concrete Riffs (mapped to action areas)

**Related to [AI-1]**: Redesign workflow to be mobile-first
- Riff A: Create mobile component library first
- Riff B: Test all designs on phone before desktop
- Riff C: Flip our Figma templates to mobile frames
```

## Validation Rules

### Executive Summary Validation
- All takeaways have [TS-n] tags
- Tags are sequential (1, 2, 3... no gaps)
- No duplicate tag numbers
- Tags appear at line end

### Action Items Validation
- All items have [AI-n] tags
- All items have Evidence field
- Evidence includes at least one [TS-n]
- Evidence includes source citation
- No [AI-n] without corresponding [TS-n]

### Brainstorm Validation
- References [AI-n] tags from seed document
- Does not create new [TS-n] tags
- Maintains connection to original evidence

## Special Cases

### Multi-Source Action Items

When an action item draws from multiple meetings:
```markdown
1. Create unified authentication approach [AI-1]
   **Evidence**: 
   - [security-review-20251120.vtt:L34-L45 — CISO][TS-2-20251120]
   - [arch-meeting-20251118.vtt:L234-L240 — Architect][TS-5-20251118]
```

### Inferred Action Items

When creating action items not directly stated:
```markdown
1. Document API versioning strategy [AI-3]
   **Owners**: API Team (INFERRED)
   **Evidence**: [discussion-20251122.md:L56-L78 — Multiple][TS-4]
   **Note**: Inferred from confusion about versions
```

### Combined Takeaways

When one action addresses multiple takeaways:
```markdown
1. Implement comprehensive monitoring solution [AI-2]
   **Evidence**: [all-hands-20251121.vtt:L345-L380 — CTO][TS-3][TS-4][TS-7]
```

## Maintenance Guidelines

### When Updating Action Items
- Keep [AI-n] tags stable
- Increment version in frontmatter
- Add new items with next sequential number
- Mark completed items but keep their tags

### When Creating Rollups
- Preserve original [TS-n] tags with dates
- Create new [AI-n] sequence
- List all source dates in `rollup_of`
- Maintain full evidence chains

### When Splitting Topics
- Each topic gets its own [TS-n] sequence
- Action items reference only their topic's takeaways
- Cross-reference in frontmatter if needed

## Anti-Patterns

### Don't Create Circular References
```markdown
❌ Executive Summary: See [AI-1] for implementation details [TS-1]
```

### Don't Skip Evidence
```markdown
❌ Action Item without [TS-n] reference in Evidence field
```

### Don't Renumber  
```markdown
❌ Changing [AI-1] to [AI-3] because you deleted [AI-2]
```

### Don't Create Meta-Tags
```markdown
❌ [TS-1a], [TS-1.1], [AI-1-subtask]
```

## Quick Reference

| Artifact | Tag Format | Location | Links To |
| -------- | ---------- | -------- | -------- |
| Executive Summary | [TS-n] | End of takeaway | Source via citation |
| Action Items | [AI-n] | End of item description | [TS-n] via Evidence |
| Brainstorm | None new | References [AI-n] | Seed action items |
| Figma Screens | None | References [AI-n] | Supporting actions |

## Examples of Proper Linking

### Simple Case
```
Source: "We need OAuth2" 
→ Takeaway: "Team decided on OAuth2 for auth [TS-1]"
→ Action: "Implement OAuth2 [AI-1]... Evidence: [TS-1]"
```

### Complex Case  
```
Sources: Multiple meetings discussing performance
→ Takeaway: "Performance degradation is critical [TS-1]"
→ Takeaway: "Users report 5-second delays [TS-2]"  
→ Action: "Fix performance issues [AI-1]... Evidence: [TS-1][TS-2]"
→ Brainstorm: "Related to [AI-1]: Try caching, CDN, query optimization"
```
