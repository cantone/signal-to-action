---
type: system-component
component: gate
name: Focus Gate
version: 1.0.0
dependencies: []
related: [topic-scope-gate.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Quick classification gate to determine domain focus and relevance
---

# Focus Gate

A rapid assessment tool to classify source material and determine processing path. Complete in 60-120 seconds with no branching logic.

## Purpose

The Focus Gate helps you:
- Quickly classify the domain focus of your source material
- Assess relevance to XDR/security context  
- Determine which templates and protocols to apply
- Make go/no-go decisions on full recipe execution

## Gate Components

### 1. Source Focus
Pick one category that best describes the primary domain:

- **ux-xdr**: User experience for XDR/security products
- **security-tech**: Technical security architecture/implementation
- **org-culture**: Organizational processes, team dynamics, culture
- **other**: Domains outside the above categories

### 2. XDR Relevance
Assess connection to XDR/security work:

- **none**: No connection to security/XDR context
- **low**: Tangential or indirect relationship
- **medium**: Clear connections but not primary focus
- **high**: Direct impact on XDR/security outcomes

### 3. Relevance Reason
Provide 1-2 lines explaining the relevance assessment, including a citation from source material.

## Decision Logic

Based on Focus Gate results:

### Continue with Full Recipe if:
- Focus = `ux-xdr` (any relevance level)
- Focus = `security-tech` with relevance ≥ `medium`
- Any focus with relevance = `high`

### Create Minimal Artifacts if:
- Focus = `other` with relevance = `medium`
- Focus = `org-culture` with relevance ≥ `medium`

### Skip Recipe Processing if:
- Relevance = `none`
- Focus = `other` with relevance = `low`

## Template Usage

```markdown
## Focus Gate (answer in 60–120 seconds; no branching logic)

- Source focus (pick one): ux-xdr
- XDR relevance (pick one): high  
- Relevance reason (1–2 lines + citation): Discussion centers on redesigning threat investigation workflow for security analysts [transcript.vtt:L45-L89 — Product Manager]
```

## Examples

### Example 1: UX-Focused Meeting
```
- Source focus: ux-xdr
- XDR relevance: high
- Relevance reason: Entire meeting dedicated to security analyst persona workflows and pain points [meeting-20251120.vtt:L12-L450 — UX Researcher]
```

### Example 2: Technical Architecture Discussion  
```
- Source focus: security-tech
- XDR relevance: medium
- Relevance reason: Discusses general microservices patterns with some mentions of threat detection services [arch-review.md:L234-L245 — Tech Lead]
```

### Example 3: Team Retrospective
```
- Source focus: org-culture  
- XDR relevance: low
- Relevance reason: Sprint retro focused on team communication issues, minimal product discussion [retro-notes.md:L5-L89 — Scrum Master]
```

## Integration Notes

- Run Focus Gate before Topic Scope Gate
- Results determine which context blocks to use (UX Problem Snapshot vs Domain Brief)
- High relevance triggers inclusion of XDR Relations section
- Low relevance may skip optional components like Scenarios
