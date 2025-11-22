---
type: system-component
component: extension
name: Figma Screens Extension
version: 1.0.0
dependencies: [templates/action-items.md]
related: [ai-prompts.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Template for creating Figma design screen inventories from action items
---

# Figma Design Screens Extension

Generate comprehensive screen inventories for Figma design work when focus = ux-xdr.

## When to Use

Activate this extension when:
- Focus Gate returns `ux-xdr`
- Action items include UX/design work
- Team needs visual deliverables
- Figma is the design tool of choice

## Required Frontmatter

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

## Template Structure

```markdown
## <Topic> — Figma Design Screens (Low-Fidelity)

### User Flow Mapping
**Primary Flow**: <Main user journey description>
**Secondary Flows**: <Alternative/edge case journeys>
**Personas**: <Which personas use these flows>

### Screen Inventory
1. **<Screen Name>** [<Flow Context>] `{STORY-ID}-0001-{brief-screen-description}`
   **Purpose**: <What this screen accomplishes>
   **Key Elements**: <Main UI components/content areas needed>
   **User Actions**: <Primary actions user can take>
   **Entry Points**: <How user arrives at this screen>
   **Exit Points**: <Where user goes next>
   **Success Criteria**: <How to know this screen is "done">
   **Supports Action Items**: [AI-n], [AI-m]

2. **<Screen Name>** [<Flow Context>] `{STORY-ID}-0002-{brief-screen-description}`
   [Continue pattern for all screens]

### Flow Connections
**Navigation Map**: <How screens connect to each other>
**Decision Points**: <Where user choices affect flow direction>
**Error/Edge Cases**: <What happens when things go wrong>

### Design Constraints
- **Responsive Requirements**: <Mobile/tablet considerations>
- **Accessibility Notes**: <A11y considerations>
- **Technical Constraints**: <Platform/framework limitations>
- **Brand/Style**: <Design system requirements>

### Success Metrics
- **User Task Completion**: <What tasks should be completable>
- **Efficiency Gains**: <Expected speed improvements>
- **Error Reduction**: <What errors should be prevented>

### Implementation Phases
**Phase 1**: <Initial screens/features>
**Phase 2**: <Enhanced functionality>
**Phase 3**: <Polish and optimization>
```

## Screen Naming Convention

### Pattern
`{STORY-ID}-{000n}-{brief-screen-description}`

### Components
- **STORY-ID**: Source story/epic identifier (e.g., XDR-30117)
- **000n**: Sequential 4-digit number (0001, 0002, 0003...)
- **brief-screen-description**: Kebab-case, descriptive but concise
- **Total length**: <64 characters for tool compatibility

### Examples
```
XDR-30117-0001-threat-overview-dashboard
XDR-30117-0002-filter-panel
XDR-30117-0003-threat-detail-modal
XDR-30117-0004-export-options
```

### Description Guidelines
- Use kebab-case (lowercase, hyphens)
- Focus on main function/purpose, not UI details
- Keep under 30 characters when possible
- Be specific but concise

## Integration Points

### Input Requirements
- Action items document with `[AI-n]` tags
- Clear understanding of user flows
- Persona definitions from knowledge base

### Output Usage
- Direct input to Figma for mockup creation
- Source for AI design prompt generation
- Reference for development team
- Basis for usability testing scenarios

## Quality Guidelines

### Screen Completeness
Each screen entry must include:
- Clear purpose statement
- Key UI elements needed
- User actions available
- Navigation context (entry/exit)
- Success criteria
- Link to driving action items

### Flow Clarity
- Primary flow should be obvious
- Alternative paths clearly marked
- Error states considered
- Edge cases documented

### Fidelity Levels

#### Low Fidelity (default)
- Focus on layout and flow
- Basic component identification
- Minimal visual detail
- Speed over polish

#### Medium Fidelity
- More detailed components
- Basic styling indicated
- Interaction patterns defined
- Some visual hierarchy

#### High Fidelity
- Detailed specifications
- Full component definitions
- Complete interaction design
- Production-ready specs

## Examples

### Security Dashboard Redesign

```markdown
## Security Dashboard Redesign — Figma Design Screens (Low-Fidelity)

### User Flow Mapping
**Primary Flow**: View threats → Filter by severity → Investigate specific threat → Take action
**Secondary Flows**: 
- Export threat data for reporting
- Configure dashboard widgets
- Set up automated responses
**Personas**: SAM (Security Analyst), REMI (Incident Responder)

### Screen Inventory
1. **Main Dashboard** [Entry Point] `XDR-30117-0001-main-threat-dashboard`
   **Purpose**: Provide at-a-glance security posture overview
   **Key Elements**: Threat count widgets, severity breakdown chart, recent alerts list, time range selector
   **User Actions**: Click into threat details, apply filters, change time range, access settings
   **Entry Points**: Login landing, main navigation
   **Exit Points**: Threat details, settings, reports
   **Success Criteria**: Analyst identifies critical threats in <10 seconds
   **Supports Action Items**: [AI-1], [AI-3]

2. **Threat Detail View** [Investigation] `XDR-30117-0002-threat-investigation`
   **Purpose**: Deep dive into specific security threat
   **Key Elements**: Threat timeline, affected assets, related indicators, action buttons
   **User Actions**: Analyze evidence, correlate events, initiate response, add notes
   **Entry Points**: Click from dashboard, direct link from alert
   **Exit Points**: Back to dashboard, response workflow, related threats
   **Success Criteria**: All relevant threat data accessible without navigation
   **Supports Action Items**: [AI-2], [AI-4]
```

## Common Patterns

### Dashboard → Detail → Action
Most common flow pattern for security interfaces:
1. Overview screen showing multiple items
2. Detail screen for investigation
3. Action screen for response

### Filter → Results → Refine
For search and analysis workflows:
1. Initial filter/search screen
2. Results list with preview
3. Refinement options

### Wizard Flows
For complex multi-step processes:
1. Step indicator across all screens
2. Clear forward/back navigation
3. Summary before confirmation

## Traceability

Always maintain connection to source action items:
- Each screen references supporting `[AI-n]` tags
- Purpose aligns with action item goals
- Success criteria support acceptance criteria

This ensures design work directly addresses identified needs rather than creating speculative features.
