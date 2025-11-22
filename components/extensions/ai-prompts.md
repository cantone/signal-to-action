---
type: system-component
component: extension
name: AI Design Prompts Extension
version: 1.0.0
dependencies: [extensions/figma-screens.md]
related: [figma-screens.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Generate AI tool prompts from Figma screen specifications
---

# AI Design Prompts Extension

Transform Figma screen specifications into actionable prompts for AI design tools.

## When to Use

Activate this extension when:
- Figma screens have been defined
- Team wants to rapidly prototype designs
- AI tools are part of the design workflow
- Low-fidelity validation is the goal

## Supported AI Tools

- **Figma Make**: AI-powered Figma plugin
- **v0**: Vercel's AI interface builder
- **Cursor**: AI-assisted code editor
- **Claude/ChatGPT**: For component code generation
- **Midjourney/DALL-E**: For asset generation

## Required Frontmatter

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

## Template Structure

```markdown
## <Topic> — AI Design Generation Prompts (Low-Fidelity)

### Prompt Philosophy: Speed Over Polish
**Goal**: Get basic structure and user flow right, iterate quickly
**Avoid**: Getting lost in detailed styling, perfect components, or design system nuances
**Focus**: Core functionality, clear user actions, logical flow connections
**Mindset**: "Good enough to test and validate" — we can enhance fidelity later

### Design Context
**Design System**: <Platform> components (don't obsess over exact styling)
**Primary Persona**: <Key user> — focus on their core tasks
**Device Target**: <Desktop/mobile> — basic responsive structure only
**Success Metric**: User can complete key task without confusion
**Screen Naming**: Use canonical screen IDs from Figma Design Screens artifact

### Screen Prompts

#### 1. **<Screen Name>** [<Flow Context>] `{STORY-ID}-0001-{brief-description}`
**Purpose**: <What this screen accomplishes>

**Figma Make Prompt**:
```
Create a basic wireframe for <screen purpose>. Focus on layout and user flow, not visual polish.

Screen ID: {STORY-ID}-000n-{brief-description}
Key Task: <What user needs to accomplish>
Essential Elements:
- <Must-have element 1>
- <Must-have element 2>
- <Basic navigation>

User Actions: <1-2 primary actions, clearly labeled>
Flow: <How user gets here> → <What they do> → <Where they go next>

Style: Simple, clean wireframe. Emphasize clarity over beauty.
```

**v0 Prompt**:
```
Build a simple React component for <screen function>.

Screen ID: {STORY-ID}-000n-{brief-description}
Focus on:
- Clear user task completion
- Basic interaction patterns
- Logical information hierarchy

Don't worry about: Perfect styling, complex states, edge cases (yet)
```

**Cursor Prompt**:
```
Create a <framework> component for <screen purpose>.

Requirements:
- Screen ID: {STORY-ID}-000n-{brief-description}
- Main functionality: <core feature>
- User can: <primary actions>
- Data needed: <key data points>

Keep it simple - basic structure and functionality only.
```

**Supports Action Items**: [AI-n]
```

## Prompt Writing Guidelines

### Core Principles

1. **Clarity First**: Be explicit about what you want
2. **Constraints Help**: Give boundaries to guide generation
3. **Iterate Fast**: Ask for simple versions first
4. **Reference IDs**: Always include screen IDs for tracking

### Tool-Specific Tips

#### Figma Make
- Describe layout spatially (top, left, center)
- Reference common UI patterns
- Specify component types when known
- Ask for grayscale/wireframe style

#### v0 (Vercel)
- Specify framework (React, Vue, etc.)
- Include key interactions
- Reference Tailwind classes if applicable
- Focus on component structure

#### Cursor
- Include file structure preferences
- Specify imports needed
- Reference design system if available
- Ask for inline documentation

### Prompt Evolution

Start simple, then enhance:

1. **Round 1**: Basic layout and structure
2. **Round 2**: Add interactions and states
3. **Round 3**: Include error handling
4. **Round 4**: Polish and refine

## Example Prompts

### Dashboard Overview Screen

```markdown
#### 1. **Threat Dashboard** [Entry Point] `XDR-30117-0001-main-dashboard`
**Purpose**: Show security posture at a glance

**Figma Make Prompt**:
```
Create a security dashboard wireframe with these sections:

Screen ID: XDR-30117-0001-main-dashboard
Layout: 
- Top: Navigation bar with user menu
- Left sidebar: Filter panel (collapsible)
- Main area: 4 metric cards in a row, chart below, table at bottom
- Right: Recent alerts feed (optional panel)

Key Metrics Cards:
- Total Threats (number + trend arrow)
- Critical Alerts (number, red if >0)
- Systems Monitored (number)
- Response Time (average)

User Actions: Click any metric to drill down, adjust time range (top right)

Style: Clean wireframe, use boxes and labels, no colors except red for critical
```

**v0 Prompt**:
```
Create a React dashboard component for security monitoring.

Screen ID: XDR-30117-0001-main-dashboard
Features:
- Grid of 4 metric cards showing: Total Threats, Critical Alerts, Systems, Response Time
- Time range selector (Today, 7 Days, 30 Days)
- Main chart area (placeholder for now)
- Recent alerts list (just titles and timestamps)

Use Tailwind classes. Mobile responsive. Loading states for data.
```
```

### Detail Investigation Screen

```markdown
#### 2. **Threat Investigation** [Deep Dive] `XDR-30117-0002-threat-detail`
**Purpose**: Investigate specific threat in detail

**Figma Make Prompt**:
```
Design a threat investigation screen wireframe.

Screen ID: XDR-30117-0002-threat-detail
Layout:
- Header: Threat title, severity badge, status dropdown
- Timeline: Vertical event list with timestamps
- Affected Assets: Card grid showing impacted systems
- Actions Panel: Buttons for Investigate, Contain, Remediate

Key Information:
- Threat metadata (type, first seen, last seen)
- Event timeline (chronological)
- Asset list with status indicators
- Available actions based on threat state

Navigation: Back to dashboard, Related threats, Export options

Style: Information density is OK, but maintain visual hierarchy
```
```

## Quality Checklist

Before delivering prompts, verify:

- [ ] Screen IDs match Figma screens document
- [ ] Purpose aligns with action items
- [ ] Prompts are tool-appropriate
- [ ] Complexity matches fidelity level
- [ ] User tasks are clearly defined
- [ ] Navigation flow is specified

## Common Patterns

### Form Screens
```
Create a form for <purpose>.
Fields: <list fields with types>
Validation: <key rules>
Submit action: <what happens>
```

### List/Table Views
```
Build a table component showing <data type>.
Columns: <list columns>
Actions per row: <view, edit, delete>
Sorting: <sortable columns>
Filtering: <filter options>
```

### Modal/Dialog
```
Design a modal for <action>.
Trigger: <what opens it>
Content: <what it shows>
Actions: <primary and secondary>
Dismissal: <how to close>
```

## Integration with Development

### Handoff Notes
Include with each prompt set:
- Technical constraints considered
- API endpoints needed (if known)
- State management requirements
- Performance considerations

### Version Control
As prompts evolve:
1. Keep original prompt
2. Document what changed
3. Note why changes were made
4. Link to feedback source

## Measuring Success

### Prompt Effectiveness
- Did AI generate usable output?
- How many iterations were needed?
- Did it match the screen spec?
- Could users complete tasks?

### Iteration Tracking
Document each round:
```markdown
**Iteration 1**: Basic structure ✓
**Iteration 2**: Added error states ✓
**Iteration 3**: Improved mobile layout ⏳
```

## Tips for Non-Designers

If you're not a designer but need to generate UI:

1. **Use References**: "Like Slack's sidebar but for threats"
2. **Describe Function**: Focus on what it does, not how it looks
3. **List Everything**: Better to include too much than too little
4. **Ask for Standards**: "Follow common dashboard patterns"
5. **Iterate Freely**: First version won't be perfect

## Future Enhancements

### Planned Features
- Prompt templates library
- Tool-specific optimizations
- Automated prompt generation
- Success metric tracking

### Integration Ideas
- Direct API to AI tools
- Feedback loop automation
- Version comparison tools
- Prompt effectiveness scoring
