---
type: system-component
component: template
name: Brainstorm Template
version: 1.0.0
dependencies: [protocols/dcrl.md, templates/action-items.md]
related: [executive-summary.md, action-items.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Template for creating DCRL-driven brainstorms from action items
---

# Brainstorm Template

Use this template to generate creative derivatives from action items using the DCRL (Dual-Channel Recursion Lock) protocol.

## Required Frontmatter

```yaml
---
type: brainstorm
topic: <human-readable title>
seed: </path/to/action-items.md>  # Path to source action items
created: <YYYY-MM-DD>  # Use seed's created date unless new session
scope: <meeting|story|spec>
version: 1
---
```

## Template Structure

```markdown
## <Topic> — Brainstorm

### Seed Context
**Source Action Items**: <link to action-items.md>
**Key Focus Areas**: <derived from action items>
**Constraints**: <time, resources, technical limits>

### Moonshots
Big, ambitious ideas that could transform the problem space:
1. <Moonshot idea 1>
2. <Moonshot idea 2>
3. <Moonshot idea 3>

### Big Swings
Significant but achievable innovations:
1. <Big swing 1>
2. <Big swing 2>
3. <Big swing 3>

### Concrete Riffs (mapped to action areas)
Practical variations on action items:

**Related to [AI-1]**: <action item summary>
- Riff A: <variation>
- Riff B: <variation>
- Riff C: <variation>

**Related to [AI-2]**: <action item summary>
- Riff A: <variation>
- Riff B: <variation>
- Riff C: <variation>

### 1‑Week Micro‑Sprint
What we could ship in one week:
1. <Deliverable 1> — <why valuable>
2. <Deliverable 2> — <why valuable>
3. <Deliverable 3> — <why valuable>

### Artifacts to Ship
Concrete outputs to create:
- <Artifact 1>: <description>
- <Artifact 2>: <description>
- <Artifact 3>: <description>

### DCRL Cycles

[Include 2-3 DCRL cycles here following the protocol]
```

## Key Guidelines

### Using DCRL Protocol
1. Run 2-3 cycles of Channel A (creative) ↔ Channel B (constraints)
2. Include the full DCRL template for each cycle
3. Show progression from broad ideas to specific make-specs

### Brainstorm Categories

#### Moonshots
- Transform the entire problem space
- Ignore current constraints
- Think 2-3 years out
- Ask "What if we could..."

#### Big Swings  
- Significant innovations within current reality
- 6-12 month horizon
- Challenge key assumptions
- Balance ambition with feasibility

#### Concrete Riffs
- Direct variations on action items
- Map each riff to specific `[AI-n]` tags
- Focus on immediate improvements
- Consider different approaches to same outcome

#### 1-Week Micro-Sprint
- Evidence-first approach
- Ship something testable
- Focus on learning quickly
- Bias toward user-facing value

#### Artifacts to Ship
- Specific, nameable deliverables
- Clear format and medium
- Defined audience
- Success criteria

## DCRL Integration Example

```markdown
### DCRL Cycle 1

**Channel A seeds:**
1. AI copilot that writes incident summaries
2. Visual timeline that auto-correlates events
3. Slack bot that suggests next investigative steps

**Channel B selection:** #2 (Visual timeline)

**Channel B constraints:**
- Time: Prototype in 3 days
- Material: D3.js + existing event API
- Transformation: Raw events → visual story
- Pass/Fail: Analyst finds root cause 50% faster

**Channel A variants:**
1. Swimlane view with automated grouping by source
2. Force-directed graph showing event relationships  
3. Gantt-style timeline with severity heat overlay

**Cycle decision:** Continue - need clearer success metric

**Make‑spec:** 
- Title: Event Correlation Timeline v0.1
- Materials: D3.js, Event API, 2 days dev time
- Steps: 1) Pull events, 2) Auto-group by time window, 3) Draw connections, 4) Add filters, 5) Test with analysts
- Success test: 3/5 analysts prefer over current tool
```

## Integration Points

### Inputs
- Action items document with `[AI-n]` tags
- Understanding of constraints and resources
- Key problem areas from executive summary

### Outputs  
- Seeds for prototypes and experiments
- Input for design sprints
- Prioritized list of innovations to explore
- Make-specs ready for implementation

## Tips for Quality Brainstorms

1. **Start wild**: Don't self-censor in early stages
2. **Map to value**: Connect every idea back to user/business impact  
3. **Time-box cycles**: Keep DCRL cycles moving (15-20 min each)
4. **Mix horizons**: Balance long-term vision with quick wins
5. **Stay grounded**: Reference evidence from source materials
