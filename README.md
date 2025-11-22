# Signal-to-Action System

> Transform unstructured inputs into structured, evidence-backed artifacts using natural language recipes.

## Overview

The Signal-to-Action system is a comprehensive framework for converting meeting transcripts, JIRA stories, specifications, and other unstructured inputs into actionable outputs. Built with a "natural language first" philosophy, it enables both humans and LLMs to process information systematically while maintaining full traceability.

## Key Features

- **Evidence-First Architecture**: Every claim traces back to source material
- **Natural Language Processing**: All instructions are human and LLM readable
- **Modular Components**: Mix and match protocols, templates, and gates
- **Built-in Quality Controls**: Prevent hallucination and maintain accuracy
- **Extensible Design**: Easy to add new workflows and variants

## What You Get

Running the signal-to-action recipe produces:

1. **Executive Summary** - Key takeaways with evidence citations `[TS-n]`
2. **Action Items** - Assignable work items linked to takeaways `[AI-n]`
3. **Brainstorm** - Creative expansions using DCRL protocol
4. **Figma Screens** - UI inventory (when applicable)
5. **AI Design Prompts** - Tool-ready prompts for rapid prototyping

## Quick Start

```bash
# Clone the repository
git clone https://github.com/cantone/signal-to-action.git

# Navigate to the system
cd signal-to-action

# Run the main recipe
/run-recipe
```

## System Structure

```
signal-to-action/
├── core/                   # Main recipes
├── components/             # Modular building blocks
│   ├── protocols/         # Processing rules
│   ├── templates/         # Output templates
│   ├── gates/            # Decision points
│   └── extensions/       # Optional features
├── commands/              # Slash commands
├── knowledge/             # Domain knowledge
└── reference/            # Specifications
```

## Use Cases

- **Meeting to Actions**: Transform transcripts into concrete next steps
- **Story to Design**: Convert JIRA stories into design specifications
- **Spec to Technical Plan**: Extract implementation tasks from PRDs
- **Brainstorming**: Generate creative solutions from constraints

## Philosophy

This system embraces several key principles:

1. **Natural Language First**: Instructions should be readable by humans, not just machines
2. **Evidence-Based**: No claims without citations
3. **Modular Design**: Components should be reusable and composable
4. **Quality Over Speed**: Better to be accurate than fast
5. **Human + AI**: Designed for collaboration, not replacement

## Documentation

- [README.md](README.md) - Detailed system documentation
- [STRUCTURE.md](STRUCTURE.md) - Complete architecture guide
- [Reference Docs](reference/) - Specifications and standards

## Contributing

This system is designed to be extended. To add new capabilities:

1. **New Recipes**: Add variants in `core/recipes/`
2. **New Protocols**: Create processing rules in `components/protocols/`
3. **New Templates**: Design output formats in `components/templates/`
4. **New Gates**: Add decision logic in `components/gates/`

## Related Systems

The Signal-to-Action system is part of a larger ecosystem:

- **UX Writer System**: For generating interface copy
- **Performance Writer System**: For performance reviews
- **Persona-as-Agent**: For persona-based validation

## License

This project is part of the Capturebox workspace. See LICENSE for details.

## Acknowledgments

Built with insights from security professionals, UX designers, and the Cisco XDR team.

---

**Note**: This is a living system. Components evolve based on real-world usage and feedback.
