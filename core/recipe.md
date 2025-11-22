---
type: system-component
component: core
name: Main Recipe - Signal-to-Action Pipeline
version: 1.1.0
dependencies: [knowledge-index, protocols/evidence-first, protocols/dcrl, templates/executive-summary, templates/action-items, templates/brainstorm]
related: [meta-recipe.md, recipe-summary.md, overview-of-recipe.md]
parent: signal-to-action-system
created: 2025-09-30
updated: 2025-11-22
maintainer: capturebox-team
description: Core recipe for transforming unstructured inputs into structured, evidence-backed artifacts
---

# Solutions Recipe — Meeting/Artifact to Action, Brainstorm, and Worksheet

Use this repeatable checklist to turn any meeting transcript or artifact into actionable outputs and
creative fuel.

## Table of Contents (key anchors)

- Focus Gate
- UX Problem Snapshot / Domain Brief
- XDR Relations
- Scenarios (optional)
- Action Items — Minimal spec (track‑aware)
- Appendix A — Operating Guidance

## 1 Inputs and source material routine

### 1.1a

- use ## Recipe Files and knowledge file list

- this recipe - `recipe.md`

- use the knowledge docs found in `/Users/caantone/Documents/Cisco/capturebox/knowledge`
- `wqXDR_AUT_optimized_minimal.md`
- `coa_object_schema_reference.md`
- `creative_exercises_and_generators.md`
- `soc_foundations_brief.pdf`
- `XDR Positioning_Messaging_Brief_April 2023.pdf`
- `XDR_atomic-groups.compact.json`
- `XDR_atomics.sample.3pct.json`
- `XDR_automation_overview.md`
- `XDR_contextual_guidance_ux_principles.md`
- `XDR_exchange_category_list.json`
- `XDR_exchange_workflow_catalog.json`
- `XDR_sample_incident_data.json.json`
- `XDR_secure-endpoint_threat-hunting_events_incidents.sample_workflow.json`
- `XDR_security_integrations_catalog.json.json`
- `XDR_workflows.selected.json`
- `XDR_Secure_Personas.json`

- Read these in and interpret their meaning as context for the rest of this recipe. Read them twice
  for understanding. They will be used to make decisions later. They give domain context for what
  we're doing next.

- When brainstorming run a choice round (three dimensions recommended):
  - Habitat/focus (e.g., attach‑to‑response, onboarding widget, prompt library, inline notification, nudge, etc.)
  - First “species”/unit (e.g., follow‑up chip, parameter card, privacy starter action, etc.)
  - Output v1 form (e.g., field guide, interactive map, taxonomy + linter, prototype, etc.)
- Capture decisions in the brainstorm doc.

- When synthesizing and analyzing materials for output, this domain knowledge serves as the interpretive "lens" through which all concepts, ideas, challenges, and solutions are evaluated and contextualized.

## A) Collect inputs

- **Source artifact:** JIRA story, JIRA epic, notes, PRD, spec document, or meeting transcript
- **Input types:**
  - Meeting transcripts (`.vtt` files with speakers/timestamps)
  - Agile stories (JIRA tickets, user stories, acceptance criteria)
  - Product specs (PRDs, technical specifications, design docs)
  - **JIRA via MCP:** Direct fetch using JIRA URL (NEW)
- Workspace target directory (e.g., `.../PARENT_DIRECTORY/`)

### A.0) JIRA MCP Integration (for JIRA stories)

When processing JIRA stories, use the MCP integration for seamless fetching:

**Input Format:**
```
Source: https://cisco-sbg.atlassian.net/browse/XDR-XXXXX
Method: JIRA MCP fetch
```

**Automated Process:**
1. Use JIRA MCP to fetch story details directly
2. System extracts:
   - Story title and description
   - Acceptance criteria (primary UX focus)
   - Technical notes (supporting context)
   - Linked issues/dependencies
3. Automatically classify with UX-centric hierarchy:
   - **Primary**: User stories, acceptance criteria, UX requirements
   - **Supporting**: Technical implementation notes
   - **Background**: API details, database changes

**Benefits over manual copy-paste:**
- No context switching to browser
- Preserves formatting and structure
- Maintains JIRA links and references
- Automatic UX signal extraction
- 5-10x faster than manual process

### A.1) Notes on creating arrtifact outputs in markdown (.md)

- Key anchors: Focus Gate, Snapshot/Brief, Scenarios (optional), Action Items, Appendices (ops
  guidance).

## B) Extract high-signal summary

**For transcripts:** Parse speaker statements into 10-15 concise takeaways; include key decisions,
open questions **For stories/specs:** Extract key decisions, requirements, constraints, and open
questions

**For JIRA stories (via MCP):** Apply UX-centric extraction:
- **Primary extraction**: User stories, acceptance criteria, user impact statements
- **Secondary extraction**: Technical constraints that affect UX
- **Background only**: Implementation details, API specs, database schemas
- Automatically elevate any mention of: user experience, workflows, interactions, UI/UX

- Focus on outcomes, decisions, implications (not process details), ensure the UX leader is informed
  on everything in his purview/responsibility/accountability
- Output: `<TOPIC><date>-executive-summary.md`
- Top Takeaways format: ordered list (1..n) with the `[TS-n]` tag appended at the end of each item.
  Ensure there is a newline between each list item.

### Executive Summary — Definition and Boundaries

- Table of Contents (key anchors)
- 1 Inputs and source material routine
  - 1.1a
- A) Collect inputs
  - A.1) Notes on creating arrtifact outputs in markdown (.md)
- B) Extract high-signal summary
  - Executive Summary — Definition and Boundaries
  - Frontmatter (required at top of executive summaries)
- Focus Gate (answer in 60–120 seconds; no branching logic)
- Topic Scope Gate
- UX Problem Snapshot (use when focus = ux-xdr)
- Domain Brief (use when focus ≠ ux-xdr)
- XDR Relations (use when relevance ≠ none)
- Scenarios (optional; 1–3 short slices)
- C) Convert takeaways into action items with evidence
  - Action Items — Minimal spec (track-aware)
  - Frontmatter (required at top of action items)
  - Linkage Protocol — Takeaways ↔ Actions
  - Agent Use Protocol — Consumption Rules (see Appendix A)
- D) Prepend stakeholders and roles
- 2) Evidence-First Protocol (AI Drift Defense \& Human Learning) — see Appendix A
  - Drift Defense Mechanisms
  - Human Learning Amplification
  - Learning-Oriented Section Headers
  - Enhanced Citation Format (canonical)
- 3) Convert takeaways into action items with evidence
  - Iteration Policy
- 3.5) Analysis and Synthesis
- 3.51) Cognitive Integrity Safeguards
  - During Analysis — Grounding Protocols
    - Anti-Drift Measures
    - Warning Signs to Abort/Revise
- 3.6) Security Domain Traceability Protocol
  - Technical Term Flagging
  - Domain Boundary Markers
  - Security Context Preservation
- 4) Prepend speakers and roles
- 5) Generate derivative brainstorm (DCRL-driven)
  - Frontmatter (required at top of brainstorms)
- 5.5) Role-Play Framework Execution Guidelines
  - Failure Mode Prevention
  - Setup Prerequisites
  - Practicing Right—Success Indicators
  - Quality Check
- 6) Optional role‑play prioritization
  - Recipe Files — file list
- 7) Ad‑hoc documentation pattern (worksheet)
- 7.5) Generate Figma design screens inventory (when focus = ux-xdr)
  - Figma Design Screens Template
- 7.6) Generate AI design prompts (when focus = ux-xdr)
  - AI Design Prompts Template
- 8) File hygiene and naming
- 9) Daily governance touch (per directives)
- 10) Deliverables checklist
- DCRL — Dual‑Channel Recursion Lock (mini‑protocol)
- Role‑play prioritization template
- Section templates
  - Speakers and Roles
  - Executive Summary (template)
  - Action Items (template)
  - Context
  - Top Takeaways
  - Action Items (with citations)
  - Brainstorm
  - Worksheet (problem/solution)
- Example filenames (list format for action items; no table tooling)
- Appendix A — Operating Guidance
  - Agent Use Protocol — Consumption Rules
  - Lens pack configuration (for portability)
  - Evidence-First Protocol (AI Drift Defense \& Human Learning)
    - Drift Defense Mechanisms
    - Human Learning Amplification
    - Learning-Oriented Section Headers
    - Enhanced Citation Format (canonical)
- Appendix B — Machine‑enforceable Schema \& Lint
  - Artifact frontmatter (required keys)
  - TS/AI linkage rules
  - Citation format (canonical)
  - Linter usage

### Frontmatter (required at top of executive summaries)

Note: `created` must reflect the source artifact's date (recording/publication), not the date you
ran this procedure.

```
---
type: executive-summary
topic: <human-readable title>
source: <filename.ext>
created: <YYYY-MM-DD>
scope: <meeting|story|spec>
audience: <me|team|leadership>
polish: <scratch|team-ready|leadership-ready>
version: 1
# Additional fields for JIRA MCP sources:
jira_url: <https://instance.atlassian.net/browse/KEY-123>  # If from JIRA
fetch_method: <manual|jira-mcp>  # How source was obtained
ux_extraction: <primary|supporting>  # UX focus level
---
```

## Focus Gate (answer in 60–120 seconds; no branching logic)

- Source focus (pick one): ux-xdr | security-tech | org-culture | other
- XDR relevance (pick one): none | low | medium | high
- Relevance reason (1–2 lines + citation): …

## Topic Scope Gate

- Primary topic: <…>
- Parking Lot (defer/non‑primary topics): <Topic> — <why defer>
- If >1 substantial topic, create a separate executive summary per topic.

<!-- Use one or more of the following blocks as needed. Skip the rest. -->

## UX Problem Snapshot (use when focus = ux-xdr)

- User/Persona:
- Problem (≤3 lines):
- Why it matters (impact):
- Success (metric/behavior change):

## Domain Brief (use when focus ≠ ux-xdr)

- Topic (1–2 lines):
- Key concepts (3 bullets):
- Constraints/Risks (3 bullets):
- Unknowns (2–3 bullets):
- Evidence: [filename:Lstart–Lend — Speaker]

## XDR Relations (use when relevance ≠ none)

- Bridge type: concept | process | data | system
- Why it matters to XDR (1 line):
- Edge/Assumption: [ASSUMPTION] …
- Evidence: [filename:Lstart–Lend — Speaker]

## Scenarios (optional; 1–3 short slices)

- Primary:
- Edge:
- Failure/latency:

<!-- Action items are optional. Create only if focus = ux-xdr OR relevance ∈ {medium, high}. -->


## C) Convert takeaways into action items with evidence

**For transcripts:** Record 
- **Speaker/Owner** Full name, followed by their initials
- **Timestamp range**
- **Why it matters** a sentence or two
- **Relationships to other ideas**
- **Speakers initials, line Number, and supporting quotes** in the transcript (if possible)

**For stories/specs:** Record:
- **Owner/Accountable party** (from story assignee, acceptance criteria, or inferred)
- **Requirement source** (acceptance criteria line, spec section, constraint block)
- **Why it matters** (impact on user, system, business)
- **Relation to other items** (dependencies, technical constraints, integration points)
- **Supporting evidence** with section/line citations referencing source document

- Output: `<TOPIC>-<date>-action-items.md`
- On all artifacts relating to stories/epics/specs ensure the title or brief description of the
  story is placed near the top of the artifact (i.e., near the name of the source)
- Example: "Story: UX - Create design to show workflow re-ordering"

### Action Items — Minimal spec (track-aware)

- Purpose: assignable, testable work items tied to `TS-n`.
- Default format: Readable multi‑line list (no tables); one action per bullet.
- Evidence: at least one inline citation `[filename:Lstart–Lend — Speaker]`.

- Use section header: `### Action Items — List`
- Readable list format (ordered list)(default):

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

- Per‑item micro‑bullets (optional):
  - For UX: Why it matters; Acceptance (artifact + review); Artifact link
  - For ENG: Why it matters; Acceptance (Given/When/Then‑lite); Tests/telemetry

### Frontmatter (required at top of action items)

Note: `created` must reflect the source artifact’s date (recording/publication), not the date you
ran this procedure.

```
---
type: action-items
topic: <human-readable title>
source: <filename.ext>
created: <YYYY-MM-DD>
scope: <meeting|story|spec>
rollup_of: [<YYYY-MM-DD>, ...]  # optional; relates to multiple exec summaries
version: 1
---
```

### Linkage Protocol — Takeaways ↔ Actions

- All action items MUST reference at least one `TS-n` from the corresponding executive summary.
- Default: do NOT compute Trace Maps; omit `TS-n → AI-m` mapping sections from executive summaries. When explicitly enabled, generate a separate Trace Map artifact and keep it out of executive summaries.
- If action items span multiple sessions, keep `AI-n` stable and increment frontmatter `version`
  when edited.

### Agent Use Protocol — Consumption Rules (see Appendix A)

See Appendix A for operating guidance on consumption and governance (execution order, leadership
updates, ideation, and rollups).

## D) Prepend stakeholders and roles

**For transcripts:** Infer speaker roles from transcript **For stories/specs:** Identify
stakeholders from:

- Story assignee/reporter
- Acceptance criteria owners
- Integration dependencies (other teams/systems mentioned)
- Explicitly mark inferences vs. stated roles

## 2) Evidence-First Protocol (AI Drift Defense & Human Learning) — see Appendix A

### Drift Defense Mechanisms

- **Source anchoring:** Every synthesis claim traces back to specific transcript segments with line
  numbers
- **Attribution clarity:** Distinguish between "Speaker X said Y" vs "Inferred from Speaker X's
  context about Y"
- **Temporal markers:** Include creation timestamps and source file dates to track content aging
- **Verification checkpoints:** Flag any statement that can't be cross-referenced to original source

### Human Learning Amplification

- **Contextual bridging:** When referencing industry patterns, explicitly connect to specific
  meeting moments that triggered the insight
- **Reasoning exposition:** Show the logical path from transcript observation → analysis → broader
  implication
- **Knowledge scaffolding:** Include "Why this matters" sections that help readers understand the
  significance of technical details
- **Pattern highlighting:** When similar themes appear across multiple transcript sections, create
  explicit cross-references

### Learning-Oriented Section Headers

Use learning-focused headers throughout your documents:

- "Key Technical Decisions and Their Implications"
- "Emerging Patterns and What They Reveal"
- "Critical Gaps and Why They Matter"
- "Cross-Reference Insights" (for recurring themes)

### Enhanced Citation Format (canonical)

Use this inline form by default: `[filename:Lstart–Lend — Speaker]` (filename only; avoid absolute
paths in published artifacts). Reserve fenced quotes for >3 lines or contentious claims. For full
guidance, see Appendix A.

## 3) Convert takeaways into action items with evidence

For each action item record:

- Speaker/Owner
- Timestamp range
- Why it matters (impact)
- Relation to other items (dependencies/sequence)
- Supporting quote(s) with line-number citation referencing the source file
- Output: `<TOPIC>-<date>-action-items.md`

### Iteration Policy

- Executive summaries are snapshots. Do not retrofit them with execution details post‑hoc; create a
  new summary per new meeting/event.
- Action items are living. Update status, owners, and acceptance as work progresses; maintain
  `version` in frontmatter.
- Brainstorms are creative derivatives seeded by action items; do not back‑propagate brainstorm
  content into executive summaries.

## 3.5) Analysis and Synthesis

Analysis Levels (pick one before you start)

- **L0 — Skim (≤60s)**: tag signals, surface 1 claim, list top unknown. Use when time is critical.
- **L1 — Triage (≤5 min)**: 2–3 claims, impact triage, contradictions, assumptions/unknowns, cost of
  delay, escalation check. Default.
- **L2 — Mini-argument (≤10 min)**: claim + counter‑claim + reconciliation path; add dependency
  outline and a micro‑scenario. Use for risky or ambiguous topics.

Analysis Quality Checklist (run fast)

- Claim is specific and testable (who/what/when visible).
- Rationale connects claim to evidence or clear inference.
- Evidence cited when stakes high or contentious.
- Unknowns are bounded and owner/timeframe assigned in actions.
- Contradictions are typed and have a resolution path.
- Impact labeled (User/System/Business) and level justified.
- Cost of delay noted with one‑line reason.
- Next test or decision is obvious from the record.

Contradictions & Gaps — Typology

- **Word Play** (same words, different meanings)
- **Time Clash** (conflicting dates or timelines)
- **Who's in Charge?** (two bosses or none)
- **Limits** (rules vs wants; tech vs what's possible)
- **Record type and propose a resolution path or who decides.**

Assumptions & Unknowns — Classification

- **Assumption**: believed true without direct evidence. Tag as [Testable Soon] | [Placeholder] |
  [Policy].
- **Unknown**: information missing. Tag as [Blocking] | [Non‑blocking] and assign a clarifier.

## 3.51) Cognitive Integrity Safeguards

- Pre-Analysis Checkpoint
  - Before beginning synthesis, establish cognitive partitions:

- **Source Partition**: Only facts/quotes directly from transcript with line citations
- **Analysis Partition**: Your interpretations clearly marked as inference
- **Industry Partition**: External knowledge clearly attributed to verified sources

### During Analysis — Grounding Protocols

- **Every claim requires provenance**: Source transcript, verified URL, or explicit "Author
  inference based on..."
- **Quote accuracy verification**: Cross-reference every citation against original line numbers
- **Scope limiting**: Industry connections must tie directly to specific transcript content—no
  orphaned expertise
- **Confidence labeling**: Mark assertions as "Confirmed," "Inferred from context," or "Industry
  pattern (unverified in source)"

#### Anti-Drift Measures

- **Synthesis anchoring**: Every industry insight must reference specific transcript quotes
- **Hallucination tripwires**: If writing about specific tools, companies, or statistics not in
  source material, STOP and verify or clearly mark as external knowledge
- **Context bleeding prevention**: Use section headers to maintain clear boundaries between
  transcript analysis and industry commentary
- **Thread integrity checks**: Periodically verify speaker attributions and timestamps match
  original source

#### Warning Signs to Abort/Revise

- Cannot cite specific line numbers for core claims
- Industry analysis feels disconnected from actual meeting content
- Writing with authority about details not present in transcript
- Speakers' roles or statements becoming unclear in your analysis

- Provide a rich and detailed analysis and synthesis of the topic including main themes, quotes, and
  the general impact of WHY IT MATTERS. Tap into larger security XDR application development themes
  and UX problem spaces. Reference usability, usefulness, delight. Reference larger topics related
  to the state of the industry, trends, and thought leadership. This should be a large,
  extrapolative section that you will need to use deep thinking to create high quality output. It
  will be required to maintain multiple context streams while creating this section of output, so
  plan ahead on how to make it high quality. Hallucinations will not be tolerated, so any references
  need to be backed up with real URLs that you have already verified exist.

## 3.6) Security Domain Traceability Protocol

### Technical Term Flagging

- **Flag all security-specific vocabulary** for review: tool names, frameworks (MITRE ATT&CK, NIST),
  compliance standards, attack techniques
- **Source every technical claim:** "Speaker mentioned X technique" vs "AI inferred X based on
  context"
- **Preserve exact terminology:** Use speaker's exact words in quotes before any interpretation

### Domain Boundary Markers

- **Explicit knowledge limits:** When AI analysis reaches security expertise boundaries, mark
  clearly: "[Analysis limited—requires domain expert validation]"
- **Assumption tagging:** Mark any security-related inferences with "[ASSUMPTION]" tags
- **Tool/vendor specificity:** Always cite exact speaker references when discussing security tools,
  never generalize

### Security Context Preservation

- **Threat model integrity:** Preserve the specific threat landscape discussed, don't generalize to
  "typical" scenarios
- **Compliance context:** Note the specific regulatory/compliance framework mentioned by speakers
- **Environmental constraints:** Capture the specific security architecture context (cloud, on-prem,
  hybrid) as discussed

## 4) Prepend speakers and roles

- Infer roles from transcript; explicitly mark inferences.
- Prepend list to the top of the action-items file for quick context.

## 5) Generate derivative brainstorm (DCRL-driven)

- Seed from the action-items file.
- Use DCRL (Dual‑Channel Recursion Lock): Channel A = creative seeds; Channel B = constraints/tests.
- Include:
  - Big swings (orthogonal ideas)
  - Concrete riffs per key action area
  - 1‑week micro‑sprint (evidence first)
  - Artifacts to ship
  - add any other "6 Thinking Hats" type ideas to the mix if feeling spunky
- Output: `<TOPIC>-<date>-brainstorm.md`

### Frontmatter (required at top of brainstorms)

Note: Set `created` to the seed action‑items’ `created` date unless a new source session is used.

```
---
type: brainstorm
topic: <human-readable title>
seed: </abs/path/to/action-items.md>
created: <YYYY-MM-DD>
scope: <meeting|story|spec>
version: 1
---
```

## 5.5) Role-Play Framework Execution Guidelines

### Failure Mode Prevention

- **Resist solution rush:** Complete all three dimensional choices before proposing any specific
  solutions
- **Input saturation first:** Ensure personas have sufficient context from previous steps
  (takeaways, action items, analysis)
- **Constraint inventory:** Map all creative constraints before entering choice rounds

### Setup Prerequisites

- **Input quality awareness:** Better inputs yield better outputs, but don't let perfect be the
  enemy of good
- **Artifact positioning:** These outputs are one piece of the design puzzle, meant to inform better
  design decisions
- **Persona grounding:** Ensure SAM, REMI, and other personas have clear context from source
  material

### Practicing Right—Success Indicators

- **Careful, considered decisions:** Choices that balance thorough analysis with forward momentum
- **Learning-oriented approach:** Decisions that preserve freedom to learn from and correct failures
- **Adaptive capacity:** Framework flexes and evolves based on project context and feedback
- **Progress enablement:** Outputs actually move design work forward rather than creating analysis
  paralysis

### Quality Check

Ask after each choice round: "Do these decisions help us learn faster?" If no, revisit the
constraint mapping or persona context.

## 6) Optional role‑play prioritization

- Define personas (e.g., Sam = Security Analyst, Remi = Security Incident Responder).
- Use the context from

### Recipe Files — file list

- `recipe.md` (this file)

## 7) Ad‑hoc documentation pattern (worksheet)

- Create a `.md` with structured sections: Context, Options, Pros/Cons, Cost/Benefit, Summary Table.
- Populate with the current problem (e.g., error codes, missing definitions) and 3–5 solution paths.
- Rename with a timestamped, human‑readable title: `Brainstorming Exercise <YYYY-MM-DD>.md`.

## 7.5) Generate Figma design screens inventory (when focus = ux-xdr)

- Seed from action items that require UX work (AI-n items with Focus = UX Design)
- Map user flows based on UX Problem Snapshot and brainstorm insights
- Create comprehensive screen inventory with purpose, elements, actions, and flow connections
- **Assign canonical screen IDs** using pattern `{STORY-ID}-{000n}-{brief-description}` for
  cross-artifact traceability
- Include design constraints, success metrics, and implementation phases
- Trace each screen back to supporting Action Items [AI-n] for clear accountability
- Output: `<TOPIC>-<date>-figma-screens.md`

### Figma Design Screens Template

```
---
type: figma-screens
topic: <Topic — YYYY-MM-DD>
source: <action-items-file.md>
created: <YYYY-MM-DD>
fidelity: low
scope: <story|epic>
version: 1
---

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

### Screen Naming Convention
**Pattern**: `{STORY-ID}-{000n}-{brief-screen-description}`
- **STORY-ID**: Source story/epic identifier (e.g., XDR-30117)
- **000n**: Sequential 4-digit number (0001, 0002, 0003...)
- **brief-screen-description**: Kebab-case, descriptive but concise
- **Total length**: <64 characters for tool compatibility
- **Example**: `XDR-30117-0001-atomic-target-config-panel`

**Description Guidelines**:
- Use kebab-case (lowercase, hyphens)
- Focus on main function/purpose, not UI details
- Keep under 30 characters when possible
- Examples: `target-suggestion-dropdown`, `invalid-warning-state`, `override-modal`

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
```

## 7.6) Generate AI design prompts (when focus = ux-xdr)

- Transform Figma screen specifications into actionable AI tool prompts
- **Use canonical screen IDs** from Figma Design Screens artifact for consistent naming across tools
- **Low-fidelity focus**: "Don't let perfect be the enemy of the good" — prioritize structure and
  flow over polish
- Generate prompts for Figma Make, v0, Cursor, and other AI design tools
- Emphasize rapid iteration and validation over detailed styling
- Maintain traceability from Action Items through screen specs to prompts
- Output: `<TOPIC>-<date>-design-prompts.md`

### AI Design Prompts Template

```
---
type: design-prompts
topic: <Topic — YYYY-MM-DD>
source: <figma-screens-file.md>
created: <YYYY-MM-DD>
target_tools: [figma-make, v0, cursor]
fidelity: low
version: 1
---

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
**Screen Naming**: Use canonical screen IDs from Figma Design Screens artifact for consistency

### Screen Prompts

#### 1. **<Screen Name>** [<Flow Context>] `{STORY-ID}-0001-{brief-screen-description}`
**Purpose**: <What this screen accomplishes - keep it simple>

**Figma Make Prompt**:
```

Create a basic wireframe for <screen purpose>. Focus on layout and user flow, not visual polish.

Screen ID: {STORY-ID}-000n-{brief-description} Key Task: <What user needs to accomplish> Essential
Elements:

- <Must-have element 1>
- <Must-have element 2>
- <Basic navigation>

User Actions: <1-2 primary actions, clearly labeled> Flow: <How user gets here> → <What they do> →
<Where they go next>

Style: Simple, clean wireframe. Emphasize clarity over beauty.

```

**v0 Prompt**:
```

Build a simple React component for <basic screen function>.

Screen ID: {STORY-ID}-000n-{brief-description} Focus on:

- Clear user task completion
- Basic interaction patterns
- Logical information hierarchy

Don't worry about: Perfect styling, complex states, edge cases (yet)

```

**Supports Action Items**: [AI-n]
```

## 8) File hygiene and naming

- Prefer Markdown and ASCII‑safe characters.
- Date‑stamp all files; include source path at top of analyses.
- Keep consistent section headers across files for quick scanning.
- Include YAML frontmatter (see sections above) for type, topic, source, created, scope, and
  versioning.

## 9) Daily governance touch (per directives)

- Surface a rules summary daily if work spans days.
- Enforce terminology corrections (e.g., “module” not “model”; “palette” not “pallet”). Be careful
  and stop to ask the operator if there is ambiguity (like it parsing speech-to-text).
- Provide a todo list for any multi‑step task; ask for preferred granularity each time.

## 10) Deliverables checklist

- Speakers + roles overview
- Top takeaways
- Session output (if selected at runtime)
- Action items with citations
- Brainstorm plan (DCRL)
- Optional role‑play prioritization
- Final worksheet (e.g., "Brainstorming Excercise Output <date>.md")
- Figma design screens inventory (for UX-focused stories: focus = ux-xdr)
- AI design prompts (for UX-focused stories: focus = ux-xdr)

---

## DCRL — Dual‑Channel Recursion Lock (mini‑protocol)

Acceptance test (the lock): buildable ≤20 minutes, ≤3 assets, includes a light + a texture (adapt as
needed), anchored to the motif/problem. Cycle (repeat 2–3 times with adaptive termination):

Channel A: propose 3–5 micro‑specs (image‑first, verbs). Channel B: select 1; add constraints (time,
material, transformation) and a pass/fail test. Channel A: generate 2–3 variants against
constraints. Channel B: converge to a make‑spec and commit.

- Adaptive Termination Criteria Continue next cycle if:

Channel A generated ≥2 meaningfully different variants Channel B constraints revealed new failure
modes Make-spec still feels incomplete or untested

Stop if:

Variants are incremental tweaks only No new constraints discovered Clear winner emerged with solid
make-spec

Quality Gate: After cycle 2, ask: "Would I bet $100 this make-spec works?" If no, run cycle 3. If
yes, stop. DCRL template

Channel A seeds: … Channel B constraints: … Cycle decision: [Continue/Stop + reasoning] Make‑spec:
Title, materials (≤3), steps (≤5), success test.

---

## Role‑play prioritization template

- Personas: Sam (Security Analyst), Remi (Security Incident Responder), You (director/decider).
- Choices:
  - Focus (A/B/C): **\_\_\_\_**
  - First unit/species (A/B/C): **\_\_\_\_**
  - Output v1 (A/B/C): **\_\_\_\_**
- Constraints: timebox, data sources, dependencies.
- Decision notes: …

---

## Section templates

### Speakers and Roles

- Name — Role/Org (explicit or inferred)

### Executive Summary (template)

```
---
type: executive-summary
topic: <Topic — YYYY-MM-DD>
source: <filename.ext>
source created: <YYYY-MM-DD>
scope: <meeting|story|spec>
audience: <me|team|leadership>
polish: <scratch|team-ready|leadership-ready>
version: n
---

## <Topic> — Executive Summary

**Executive Summary Created on:** <YYYY-MM-DD>
**Source**: <filename or path>
**Source Date (optional)**: <YYYY-MM-DD>

### Context
<2–4 lines>

### Top Takeaways
1. <concise outcome or decision> [confidence: Confirmed | Inferred] [TS-1]
2. <concise outcome or decision> [confidence: Confirmed | Inferred] [TS-2]

### Signals
- Owners: <Name(s)> [INFERRED/EXPLICIT] — <lines>
- Timeframes/Dates: <phrase> — <lines>
- Priority: <High/Medium/Low> — <lines>

### Impact Triage (optional)
- User=<H/M/L>, System=<H/M/L>, Business=<H/M/L>

### Cost of Delay (optional)
- <L/M/H> — <why>

### Open Questions
- <…>

### Constraints and Risks
- <…>

### Immediate Next Steps (no owners)
- <…>

<!-- Trace Map removed by policy: do not generate or maintain TS→AI maps. -->
```

### Action Items (template)

```
---
type: action-items
topic: <Topic — YYYY-MM-DD>
source: <filename.ext>
created: <YYYY-MM-DD>
scope: <meeting|story|spec>
version: 1
---

## <Topic> — Action Items

### Action Items — List
1. <Outcome, can be multi‑clause> [AI-1]
   **Owners**: <Full names, not initials>
   **Focus**: <Alignment|Convergence|AI‑Gen|Playbooks|Audit|Research|Agentic‑Now>
   **Acceptance (optional)**: <done looks like>
   **Impact (optional)**: User=<H/M/L>, System=<H/M/L>, Business=<H/M/L>
   **Cost of Delay (optional)**: <L/M/H> — <why>
   **Evidence**: [file:Lstart–Lend — Speaker]

2. <Outcome, can be multi‑clause> [AI-2]
   **Owners**: <Full names, not initials>
   **Focus**: <Alignment|Convergence|AI‑Gen|Playbooks|Audit|Research|Agentic‑Now>
   **Acceptance (optional)**: <done looks like>
   **Impact (optional)**: User=<H/M/L>, System=<H/M/L>, Business=<H/M/L>
   **Cost of Delay (optional)**: <L/M/H> — <why>
   **Evidence**: [file:Lstart–Lend — Speaker]

<!-- Table format removed to reduce drift. Use the list format only. -->
```

### Context

A 2–4 line summary of the problem or meeting objective and the source file path.

### Top Takeaways

1. <concise outcome or decision> [TS-1]
2. <concise outcome or decision> [TS-2]

### Action Items (with citations)

1. <Action outcome> [AI-1] **Owner/Speaker**: …  
   **Timestamp**: …  
   **Why it matters**: …  
   **Relation**: …  
   **Quote**:
   ```startLine:endLine:filename — Speaker Name
   …
   ```

### Brainstorm

- Moonshots
- Big Swings
- Concrete Riffs (mapped to action areas)
- 1‑Week Micro‑Sprint
- Artifacts to Ship

### Worksheet (problem/solution)

- Context
- Options (3–5)
- Pros/Cons (per option)
- Cost/Benefit (per option)
- Summary Table

---

## Example filenames (list format for action items; no table tooling)

- `AI-UX-Guild-20250811-action-items.md`
- `AI-UX-Guild-20250811-brainstorm.md`
- `Brainstorming Exercise 2025-08-11.md`
- `XDR-41258-2025-11-22-executive-summary.md` (from JIRA MCP)
- `XDR-41258-2025-11-22-action-items.md` (from JIRA MCP)

# Add 2 final documents

1. Generate a worksheet doc
2. Roll up multiple sessions into a combined action-items with rollup_of.

## JIRA MCP Workflow Example

### Quick UX Planning from JIRA Story

**Input:**
```
"Find XDR-41258 and create UX approach"
```

**Automated Process:**
1. **Fetch via MCP**: `jira_query XDR-41258`
2. **Run recipe with UX focus**:
   ```
   Focus: ux-xdr (automatic for JIRA stories)
   UX extraction: primary
   ```
3. **Outputs generated**:
   - Executive Summary: UX requirements elevated, tech details backgrounded
   - Action Items: Design tasks first, supporting tech tasks marked clearly
   - Brainstorm: User-centered solutions using DCRL

**Time savings**: 5 minutes vs 30+ minutes manual process
**Cognitive savings**: Stay in design mode throughout

---

## Appendix A — Operating Guidance

### Agent Use Protocol — Consumption Rules

- For execution: read `action-items` first. Treat it as the single source of truth for work/state.
- For leadership updates: read only `executive-summary` snapshots; do not invent new tasks.
- For ideation: seed from `action-items` into `brainstorm`. Do not back‑propagate brainstorm content
  into summaries.
- When discovering a gap (missing AI for a `TS-n`): create a new `AI-n`, cite evidence. Do not add a
  Trace Map section by default. If trace-map mode is explicitly enabled, generate the Trace Map as a
  separate artifact; do not embed it in executive summaries.
- For multi‑meeting topics: use `rollup_of` in `action-items` frontmatter to list covered summary
  dates.

### Lens pack configuration (for portability)

- Prefer configuring a lens pack instead of hardcoding filenames: `--lens-pack xdr|generic|custom:/abs/path`.
- The file list in 1.1a reflects the current XDR corpus (including legacy filenames). Load by directory
  rather than exact names when possible.

### Evidence-First Protocol (AI Drift Defense & Human Learning)

#### Drift Defense Mechanisms

- **Source anchoring:** Every synthesis claim traces back to specific transcript segments with line
  numbers
- **Attribution clarity:** Distinguish between "Speaker X said Y" vs "Inferred from Speaker X's
  context about Y"
- **Temporal markers:** Include creation timestamps and source file dates to track content aging
- **Verification checkpoints:** Flag any statement that can't be cross-referenced to original source

#### Human Learning Amplification

- **Contextual bridging:** When referencing industry patterns, explicitly connect to specific
  meeting moments that triggered the insight
- **Reasoning exposition:** Show the logical path from transcript observation → analysis → broader
  implication
- **Knowledge scaffolding:** Include "Why this matters" sections that help readers understand the
  significance of technical details
- **Pattern highlighting:** When similar themes appear across multiple transcript sections, create
  explicit cross-references

#### Learning-Oriented Section Headers

Use learning-focused headers throughout your documents:

- "Key Technical Decisions and Their Implications"
- "Emerging Patterns and What They Reveal"
- "Critical Gaps and Why They Matter"
- "Cross-Reference Insights" (for recurring themes)

#### Enhanced Citation Format (canonical)

Use this inline form by default: `[filename:Lstart–Lend — Speaker]`. Reserve fenced quotes for >3
lines or contentious claims.

---

## Appendix B — Machine‑enforceable Schema & Lint

### Artifact frontmatter (required keys)

- executive-summary: `type`, `topic`, `source`, `created`, `scope`, `audience`, `polish`, `version`
- action-items: `type`, `topic`, `source`, `created`, `scope`, `version` (optional: `rollup_of`)
- brainstorm: `type`, `topic`, `seed`, `created`, `scope`, `version`
- figma-screens: `type`, `topic`, `source`, `created`, `fidelity`, `scope`, `version`
- design-prompts: `type`, `topic`, `source`, `created`, `target_tools`, `fidelity`, `version`

### TS/AI linkage rules

- Executive Summary: `[TS-n]` tags start at 1 and are contiguous (no gaps).
- Action Items: Each `[AI-n]` must reference ≥1 `[TS-n]` and include ≥1 citation.
- Trace Map: Off by default. If enabled, generate as a separate artifact; never embed in executive summaries.

### Citation format (canonical)

- Inline citations MUST match: `[basename:Lstart–Lend — Speaker]` (en dash between Lstart and Lend).
- Prefer basenames; avoid absolute paths in published artifacts.

### Linter usage

- Run: `python scripts/recipe_lint.py --path <dir>`
- Enable optional Trace Map checks: add `--trace-map`.
