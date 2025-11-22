---
type: system-component
component: command
name: Command Registry Index  
version: 1.0.0
dependencies: []
related: [run-recipe.md]
parent: signal-to-action-system
created: 2025-11-22
updated: 2025-11-22
maintainer: capturebox-team
description: Registry of commands related to the signal-to-action system
---

# Signal-to-Action Command Registry

Central registry for discovering and understanding commands related to the signal-to-action system.

## Primary Commands

### `/run-recipe`
**Location**: `commands/run-recipe.md`  
**Purpose**: Execute the main signal-to-action recipe workflow
**Status**: Active

Transforms unstructured inputs (transcripts, stories, specs) into structured artifacts:
- Executive summaries with evidence citations
- Action items linked to takeaways  
- DCRL-driven brainstorms
- Optional: Figma screens, AI prompts

**Usage**:
```
/run-recipe
```

## Related System Commands

These commands live in their own systems but integrate with signal-to-action workflows:

### UX Writer System
**Location**: `/projects/systems/ux-writer-system/`
**Command**: `/ux-writer`

- `/ux-writer tooltip` - Generate context-aware tooltips
- `/ux-writer error` - Create user-friendly error messages  
- `/ux-writer empty-state` - Design empty state messages
- `/ux-writer review` - Analyze and improve existing copy

### Performance Writer System  
**Location**: `/projects/systems/perf-writer-system/`
**Command**: `/perf-writer`

- `/perf-writer --init` - Initialize performance review  
- `/perf-writer --phase N` - Jump to specific phase
- `/perf-writer --status` - Check progress

## Utility Commands

These commands support signal-to-action workflows:

### Content Management
- `/compress-context` - Reduce token usage while preserving meaning
- `/enhance-prompt` - Improve prompt clarity and specificity
- `/make-prompt` - Generate prompts from requirements

### Quality Control
- `/check-emojis` - Verify no emojis in output (per memory.md)
- `/remove-emojis` - Clean emojis from content
- `/verify` - Validate artifact compliance

### Search and Discovery
- `/search-files` - Find files by pattern or content
- `/jira-query` - Query JIRA for stories/epics

### Version Control
- `/checkpoint` - Create workflow checkpoint
- `/backup-repo` - Backup repository state
- `/cosmetic-commits` - Clean up commit history

## Command Patterns

### Recipe Variants

Future recipe variants will follow this pattern:
```
/run-recipe-{variant}
```

Planned variants:
- `/run-recipe-quick` - 5-minute simplified version
- `/run-recipe-technical` - Security architecture focus
- `/run-recipe-design` - UX/design emphasis

### Pipeline Commands

Commands that work with recipe outputs:
```
/recipe-to-{destination}
```

Examples:
- `/recipe-to-jira` - Convert action items to JIRA tickets
- `/recipe-to-figma` - Push screens to Figma
- `/recipe-to-slack` - Share summaries in Slack

## Adding New Commands

To add a command to the signal-to-action system:

1. **Create Command File**
   ```yaml
   ---
   type: system-component
   component: command
   name: Your Command Name
   version: 1.0.0
   dependencies: [<required components>]
   related: [<related commands>]
   parent: signal-to-action-system
   ---
   ```

2. **Define Command Structure**
   ```markdown
   /SLASH-COMMAND: /your-command
   
   DESCRIPTION:
   What the command does
   
   ACTION:
   1. Step one
   2. Step two
   
   BEHAVIOR:
   - Key behavior notes
   ```

3. **Update This Registry**
   Add entry in appropriate section with:
   - Command name and location
   - Brief purpose description
   - Usage examples
   - Integration notes

## Command Discovery

### By Workflow Stage
- **Input**: `/jira-query`, `/search-files`
- **Processing**: `/run-recipe`, `/compress-context`
- **Output**: `/recipe-to-*` commands
- **Quality**: `/verify`, `/check-emojis`

### By System  
- **Signal-to-Action**: This registry
- **UX Writer**: `/projects/systems/ux-writer-system/`
- **Perf Writer**: `/projects/systems/perf-writer-system/`
- **Persona Agent**: `/projects/persona-as-agent/`

### By Frequency
Most used with recipes:
1. `/run-recipe` - Primary workflow
2. `/search-files` - Find source materials
3. `/compress-context` - Manage token limits
4. `/verify` - Validate output

## Integration Examples

### Full Workflow
```bash
# 1. Find relevant materials
/search-files pattern="meeting.*2025-11"

# 2. Run recipe on transcript  
/run-recipe

# 3. Enhance action items
/enhance-prompt

# 4. Generate UX copy
/ux-writer tooltip
```

### Quick Analysis
```bash
# Simplified flow for time constraints
/run-recipe-quick  # Coming soon
/compress-context
```

## Command Metadata

Each command should specify:
- **Purpose**: One-line description
- **Scope**: What it operates on
- **Audience**: Who should use it
- **Version**: For compatibility tracking
- **Dependencies**: Required systems/files

## Future Enhancements

### Planned Commands
- `/recipe-lint` - Validate recipe compliance
- `/recipe-stats` - Analytics on recipe usage
- `/recipe-diff` - Compare recipe outputs
- `/recipe-merge` - Combine multiple summaries

### Command Chaining
Future support for piping commands:
```
/run-recipe | /recipe-to-jira | /notify-team
```

### Command Aliases
Shorter alternatives for common commands:
```
/rr → /run-recipe
/ux → /ux-writer
/pf → /perf-writer
```
