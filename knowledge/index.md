---
type: system-component
component: knowledge-index
name: Knowledge Resources Index
version: 1.0.0
dependencies: []
related: [recipe.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Index of knowledge resources used by the signal-to-action system
---

# Knowledge Resources Index

This index maps to knowledge resources in `/Users/caantone/Documents/Cisco/capturebox/knowledge/` that provide domain context for recipe execution.

## Core Knowledge Files

These files are loaded by default when running recipes:

### Security Domain Knowledge
- `XDR_AUT_optimized_minimal.md` - Minimal XDR automation reference
- `coa_object_schema_reference.md` - Common Objects and Attributes schema
- `XDR_automation_overview.md` - High-level automation concepts
- `XDR_contextual_guidance_ux_principles.md` - UX principles for XDR

### Personas
- `XDR_Secure_Personas.json` - Complete persona definitions
- `persona-data.md` - Persona summary data
- Individual persona files in `persona markdown/`:
  - `sam-security_analyst.md` - Security Analyst (primary)
  - `remi-incident_responder.md` - Incident Responder
  - `alex-architect.md` - Security Architect
  - `kit-it-system-professional.md` - IT Administrator
  - `nik-network_professional.md` - Network Administrator

### Reference Documents
- `soc_foundations_brief.pdf` - Security Operations Center foundations
- `XDR Positioning_Messaging_Brief_April 2023.pdf` - Product positioning

### Technical Catalogs (JSON)
- `XDR_atomic-groups.compact.json` - Atomic action groups
- `XDR_atomics.sample.3pct.json` - Sample atomic actions
- `XDR_exchange_category_list.json` - Integration categories
- `XDR_exchange_workflow_catalog.json` - Workflow catalog
- `XDR_sample_incident_data.json.json` - Sample incident structures
- `XDR_security_integrations_catalog.json.json` - Available integrations
- `XDR_workflows.selected.json` - Curated workflow examples

### Creative Resources
- `creative_exercises_and_generators.md` - Brainstorming tools
- `brainstorming_protocol.md` - DCRL and other protocols
- `brainstorming_techniques_matrix.md` - Technique reference

## Lens Pack Configuration

Different recipe variants can use different knowledge subsets:

### UX-XDR Lens Pack
Primary files for UX-focused work:
- All persona files
- `XDR_contextual_guidance_ux_principles.md`
- `creative_exercises_and_generators.md`
- `XDR_sample_incident_data.json.json` (for scenarios)

### Security-Tech Lens Pack
Primary files for technical architecture:
- `coa_object_schema_reference.md`
- `XDR_atomic-groups.compact.json`
- `XDR_atomics.sample.3pct.json`
- Technical catalogs (all JSON files)

### Full Context Lens Pack
All files listed above - use when domain is unclear or comprehensive context needed.

## Usage in Recipes

### Default Loading
The main recipe (`recipe.md`) loads these files in section 1.1a:
```markdown
- use the knowledge docs found in `/Users/caantone/Documents/Cisco/capturebox/knowledge`
```

### Selective Loading
For faster execution, load only needed files based on Focus Gate results:
- `focus = ux-xdr` → Load UX-XDR Lens Pack
- `focus = security-tech` → Load Security-Tech Lens Pack
- `focus = other` → Skip knowledge loading or load minimal set

## Adding New Knowledge Resources

To add new knowledge files:

1. Place file in appropriate `/knowledge/` subdirectory
2. Update this index with:
   - Filename and brief description
   - Which lens packs should include it
   - Any special loading conditions
3. Update recipe.md section 1.1a if it's a core file

## Knowledge File Standards

Knowledge files should:
- Include clear headers and structure
- Provide examples where applicable
- Maintain consistent formatting
- Include update dates/versions
- Focus on reusable reference content

## Special Directories

### `/knowledge/xdr-docs/`
Contains parsed XDR documentation for deep technical reference. Not loaded by default due to size.

### `/knowledge/special-projects/`
Project-specific knowledge that may require special handling or permissions.
