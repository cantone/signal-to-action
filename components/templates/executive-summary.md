---
type: system-component
component: template
name: Executive Summary Template
version: 1.0.0
dependencies: [protocols/evidence-first.md, gates/focus-gate.md, gates/topic-scope-gate.md]
related: [action-items.md, brainstorm.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Template for creating executive summaries from source artifacts
---

# Executive Summary Template

Use this template to create executive summaries from meeting transcripts, JIRA stories, or specification documents.

## Required Frontmatter

```yaml
---
type: executive-summary
topic: <Topic — YYYY-MM-DD>
source: <filename.ext>
created: <YYYY-MM-DD>  # Date of source artifact, not creation date
scope: <meeting|story|spec>
audience: <me|team|leadership>
polish: <scratch|team-ready|leadership-ready>
version: 1
---
```

## Template Structure

```markdown
## <Topic> — Executive Summary

**Executive Summary Created on:** <YYYY-MM-DD>
**Source**: <filename or path>
**Source Date (optional)**: <YYYY-MM-DD>

### Context
<2–4 lines describing the problem or meeting objective>

### Top Takeaways
1. <concise outcome or decision> [confidence: Confirmed | Inferred] [TS-1]
2. <concise outcome or decision> [confidence: Confirmed | Inferred] [TS-2]
3. <concise outcome or decision> [confidence: Confirmed | Inferred] [TS-3]
...
[10-15 takeaways total]

### Signals
- Owners: <Name(s)> [INFERRED/EXPLICIT] — <lines>
- Timeframes/Dates: <phrase> — <lines>
- Priority: <High/Medium/Low> — <lines>

### Impact Triage (optional)
- User=<H/M/L>, System=<H/M/L>, Business=<H/M/L>

### Cost of Delay (optional)
- <L/M/H> — <why>

### Open Questions
- <Question 1>
- <Question 2>

### Constraints and Risks
- <Constraint/Risk 1>
- <Constraint/Risk 2>

### Immediate Next Steps (no owners)
- <Step 1>
- <Step 2>

<!-- Trace Map removed by policy: do not generate or maintain TS→AI maps. -->
```

## Key Guidelines

### Takeaway Formatting
- Number each takeaway and tag with `[TS-n]` where n is sequential
- Mark confidence level: `[confidence: Confirmed]` for direct quotes, `[confidence: Inferred]` for interpretations
- Keep takeaways concise and outcome-focused
- Focus on decisions, not process details

### Evidence Requirements
- Every claim must reference source material
- Use inline citations: `[filename:Lstart-Lend — Speaker]`
- Distinguish between stated facts and inferences

### Scope Management
- If multiple substantial topics emerge, create separate summaries
- Use the Parking Lot section in Topic Scope Gate to defer non-primary topics

## Integration Points

### Before Creating Summary
1. Run Focus Gate (see `gates/focus-gate.md`)
2. Run Topic Scope Gate (see `gates/topic-scope-gate.md`)
3. Choose appropriate context block (UX Problem Snapshot or Domain Brief)

### After Creating Summary
- Executive summary takeaways (`[TS-n]`) become inputs for Action Items
- Each Action Item must reference at least one `[TS-n]`

## Examples

### Meeting Transcript Example
```markdown
### Top Takeaways
1. Team agreed to prioritize mobile-first redesign for Q1 [confidence: Confirmed] [TS-1]
2. Budget constraints will limit hiring to 2 engineers instead of 5 [confidence: Confirmed] [TS-2]
3. Security review process is blocking feature releases [confidence: Inferred] [TS-3]
```

### JIRA Story Example
```markdown
### Context
Story XDR-1234: Implement automated threat correlation engine for reducing false positive alerts in SOC environments.

### Top Takeaways
1. Correlation engine must process 100K events/second minimum [confidence: Confirmed] [TS-1]
2. Integration with existing SIEM tools is critical for adoption [confidence: Inferred] [TS-2]
```
