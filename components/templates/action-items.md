---
type: system-component
component: template
name: Action Items Template
version: 1.0.0
dependencies: [protocols/evidence-first.md, templates/executive-summary.md]
related: [executive-summary.md, brainstorm.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Template for creating actionable work items from executive summaries
---

# Action Items Template

Use this template to convert executive summary takeaways into assignable, testable work items.

## Required Frontmatter

```yaml
---
type: action-items
topic: <Topic — YYYY-MM-DD>
source: <filename.ext>
created: <YYYY-MM-DD>  # Date of source artifact, not creation date
scope: <meeting|story|spec>
rollup_of: [<YYYY-MM-DD>, ...]  # Optional: for multi-session topics
version: 1
---
```

## Template Structure

```markdown
## <Topic> — Action Items

### Speakers and Roles
- <Name> — <Role/Org> [EXPLICIT/INFERRED]
- <Name> — <Role/Org> [EXPLICIT/INFERRED]

### Action Items — List

1. <Outcome, can be multi‑clause> [AI-1]
   **Owners**: <Full names, not initials>
   **Focus**: <Alignment|Convergence|AI‑Gen|Playbooks|Audit|Research|Agentic‑Now>
   **Acceptance (optional)**: <done looks like>
   **Impact (optional)**: User=<H/M/L>, System=<H/M/L>, Business=<H/M/L>
   **Cost of Delay (optional)**: <L/M/H> — <why>
   **Evidence**: [file:Lstart–Lend — Speaker][TS-n]

2. <Outcome, can be multi‑clause> [AI-2]
   **Owners**: <Full names, not initials>
   **Focus**: <Alignment|Convergence|AI‑Gen|Playbooks|Audit|Research|Agentic‑Now>
   **Acceptance (optional)**: <done looks like>
   **Impact (optional)**: User=<H/M/L>, System=<H/M/L>, Business=<H/M/L>
   **Cost of Delay (optional)**: <L/M/H> — <why>
   **Evidence**: [file:Lstart–Lend — Speaker][TS-n]

<!-- Table format removed to reduce drift. Use the list format only. -->
```

## Key Guidelines

### Linkage Protocol
- Every action item MUST reference at least one `[TS-n]` from the corresponding executive summary
- Include evidence citations in format: `[file:Lstart–Lend — Speaker][TS-n]`
- Do NOT create trace maps showing TS→AI relationships

### Focus Categories
Choose one focus area per action item:
- **Alignment**: Getting stakeholders on same page
- **Convergence**: Narrowing options to decision
- **AI-Gen**: AI/ML-generated content or automation
- **Playbooks**: Process documentation
- **Audit**: Review/assessment activities
- **Research**: Investigation/exploration
- **Agentic-Now**: Immediate autonomous action

### Optional Fields
Include these when they add clarity:
- **Acceptance**: Specific criteria for "done"
- **Impact**: User/System/Business ratings (H/M/L)
- **Cost of Delay**: What happens if we wait

### Living Document
- Action items are meant to be updated as work progresses
- Increment `version` in frontmatter when making updates
- Keep original `[AI-n]` tags stable across versions

## Examples

### Meeting-Based Action Item
```markdown
1. Create mobile-first wireframes for threat dashboard [AI-1]
   **Owners**: Jane Smith, Tom Rodriguez
   **Focus**: Convergence
   **Acceptance**: 3 wireframe variations reviewed by UX team
   **Impact**: User=H, System=L, Business=M
   **Cost of Delay**: M — Q1 launch at risk
   **Evidence**: [meeting-20251122.vtt:L245-L260 — Jane Smith][TS-1]
```

### Story-Based Action Item
```markdown
1. Implement event correlation algorithm with 100K/sec throughput [AI-1]
   **Owners**: Engineering Team Lead (TBD)
   **Focus**: AI-Gen
   **Acceptance**: Performance test shows sustained 100K events/sec
   **Impact**: User=M, System=H, Business=H
   **Evidence**: [XDR-1234-story.md:L15-L18 — Product Owner][TS-1][TS-4]
```

## Integration Points

### Inputs
- Executive Summary with `[TS-n]` tagged takeaways
- Source artifact (transcript/story/spec) for evidence

### Outputs
- Seeds for Brainstorm generation (using DCRL protocol)
- Work items for tracking systems
- Input for role-play prioritization

## Per-Item Micro-Bullets (Optional)

For additional clarity, you can add role-specific details:

### For UX Items
- Why it matters: <user impact>
- Acceptance: <artifact type + review process>
- Artifact link: <where it will live>

### For Engineering Items
- Why it matters: <technical impact>
- Acceptance: <Given/When/Then format>
- Tests/telemetry: <how we'll know it works>
