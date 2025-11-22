---
type: system-component
component: gate
name: Topic Scope Gate
version: 1.0.0
dependencies: [focus-gate.md]
related: [focus-gate.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Gate to identify and scope primary topics versus parking lot items
---

# Topic Scope Gate

A scoping tool to identify the primary topic and defer non-essential topics to maintain focus.

## Purpose

The Topic Scope Gate helps you:
- Identify the single primary topic for deep analysis
- Recognize secondary topics that should be deferred
- Prevent scope creep during artifact generation
- Ensure each executive summary maintains clear focus

## Gate Components

### 1. Primary Topic
Identify the ONE main topic that deserves full recipe treatment. This should be:
- The most urgent or impactful issue
- The topic with the most discussion/detail in source
- The area where decisions are needed now

### 2. Parking Lot
List topics that emerged but should be deferred, with reasons:
- Topic name — Brief reason for deferral
- Keep reasons short (5-10 words)
- Common reasons: "needs separate deep-dive", "pending external input", "lower priority"

### 3. Multi-Topic Rule
If multiple substantial topics deserve full treatment:
- Create separate executive summaries for each
- Run the full recipe independently per topic
- Cross-reference between summaries as needed

## Template Usage

```markdown
## Topic Scope Gate

- Primary topic: <Main focus area>
- Parking Lot (defer/non‑primary topics): 
  - <Topic 1> — <why defer>
  - <Topic 2> — <why defer>
- If >1 substantial topic, create a separate executive summary per topic.
```

## Examples

### Example 1: Clear Single Topic
```markdown
## Topic Scope Gate

- Primary topic: Mobile-first redesign of threat dashboard
- Parking Lot (defer/non‑primary topics):
  - API performance issues — needs engineering deep-dive
  - Team hiring plans — HR-led discussion needed
```

### Example 2: Multiple Substantial Topics
```markdown
## Topic Scope Gate

- Primary topic: Automated threat correlation engine design
- Parking Lot (defer/non‑primary topics): [none - but see note below]
- Note: Meeting also covered "Integration with partner SIEMs" extensively. Creating separate executive summary for that topic.
```

### Example 3: Broad Discussion Needing Focus
```markdown
## Topic Scope Gate

- Primary topic: Q1 security roadmap prioritization
- Parking Lot (defer/non‑primary topics):
  - Technical debt discussion — needs architect review
  - Budget constraints — pending finance approval  
  - Compliance requirements — legal team input needed
  - Team morale concerns — separate 1:1s planned
```

## Decision Guidelines

### Choose Primary Topic Based On:
1. **Urgency**: What needs decisions/action soonest?
2. **Coverage**: What got the most discussion time?
3. **Impact**: What affects the most users/systems?
4. **Readiness**: What has enough info to act on?

### Defer Topics When:
- Insufficient information to analyze properly
- Requires stakeholders not present  
- Depends on other decisions not yet made
- Would dilute focus on urgent primary topic

### Create Multiple Summaries When:
- Two or more topics are equally substantial
- Topics are unrelated (can't be unified)
- Different audiences need different summaries
- Timeline/urgency differs significantly

## Anti-Patterns to Avoid

❌ **Kitchen Sink**: Trying to cover everything in one summary
❌ **False Unity**: Forcing unrelated topics together
❌ **Scope Creep**: Letting parking lot items sneak into analysis
❌ **Over-Deferral**: Parking everything except trivial items

## Integration Notes

- Run after Focus Gate, before writing executive summary
- Primary topic shapes the Context section
- Parking lot items may become future recipe inputs
- Multiple summaries share the same source but different topics
