# Signal-to-Action System

> A force multiplier for overwhelmed UX professionals - transform unstructured inputs into structured, evidence-backed artifacts using natural language recipes.

## Overview

The Signal-to-Action system was born out of necessity. As the sole UX resource on an immensely large and complex project with hundreds of engineers across the platform, I needed a way to do more with less. This framework converts meeting transcripts, JIRA stories, specifications, and other unstructured inputs into actionable outputs at scale.

Built with a "natural language first" philosophy, it enables a single person (with minimal help from time-constrained colleagues) to systematically process information while maintaining full traceability. It's not just about organization - it's about survival and effectiveness in enterprise-scale environments.

## Key Features

- **Evidence-First Architecture**: Every claim traces back to source material
- **Natural Language Processing**: All instructions are human and LLM readable
- **UX-Centric Hierarchy**: Keeps design decisions primary, technical details secondary
- **Modular Components**: Mix and match protocols, templates, and gates
- **Built-in Quality Controls**: Prevent hallucination and maintain accuracy
- **Noise Filtering**: Separates UX signal from implementation complexity
- **Extensible Design**: Easy to add new workflows and variants

## What You Get

Running the signal-to-action recipe produces **UX-focused outputs** from any input:

1. **Executive Summary** - Key takeaways with UX decisions highlighted, evidence citations `[TS-n]`
2. **Action Items** - UX work prioritized, technical tasks clearly marked as supporting `[AI-n]`
3. **Brainstorm** - Design-centric creative expansions using DCRL protocol
4. **Figma Screens** - UI inventory with user flows and interaction patterns
5. **AI Design Prompts** - Tool-ready prompts for rapid prototyping

Each artifact maintains the hierarchy: UX decisions → supporting technical context → implementation details

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

## The Challenge This Solves

As a sole UX resource supporting hundreds of engineers:

- **Information Overload**: Multiple meetings daily, each generating hours of discussion
- **Context Switching**: Jumping between numerous projects and teams
- **Documentation Debt**: No time to properly document decisions and rationale
- **Scalability Crisis**: Being asked to cover more features with the same (or less) time
- **Evidence Gaps**: Decisions questioned months later with no clear trail
- **Collaboration Barriers**: Team members equally overwhelmed, minimal bandwidth to help
- **Signal vs Noise**: UX decisions buried under layers of technical implementation details

## Maintaining UX Focus in Technical Complexity

This system actively maintains a **UX-centric hierarchy** where:

### Primary Focus (Signal)
- User needs and pain points
- Design decisions and rationale
- Interaction patterns and flows
- Usability considerations
- Accessibility requirements
- User journey mapping

### Supporting Context (Filtered Noise)
- Implementation details (backend, APIs, data structures)
- Framework constraints (React, Angular, etc.)
- Technical architecture discussions
- Performance optimization debates
- Database schema decisions

The system filters conversations to **highlight, elevate, and focus** UX work, allowing you to:
- **Stay in design mode** while processing technical meetings
- **Extract UX-relevant decisions** from implementation discussions
- **Maintain perspective** on user impact amidst technical complexity
- **Prioritize the right UX work** at the right time
- **Avoid drowning** in cross-functional decision details

## Use Cases

- **Meeting to Actions**: Transform transcripts into concrete next steps without manual note-taking
- **Story to Design**: Convert JIRA stories into design specifications in minutes, not hours
- **Spec to Technical Plan**: Extract implementation tasks from PRDs systematically
- **Brainstorming**: Generate creative solutions from constraints when you're the only designer
- **Stakeholder Alignment**: Create evidence-backed summaries for leadership in standardized formats
- **Design Rationale**: Maintain decision trails for when "why did we do it this way?" comes up

## Philosophy

This system embraces several key principles born from real-world pressure:

1. **Natural Language First**: No time to learn complex syntax - instructions must be readable by humans, not just machines
2. **UX Signal Over Technical Noise**: Design decisions stay primary; implementation details are supporting context only
3. **Evidence-Based**: When you're outnumbered 100:1, every design decision needs bulletproof citations
4. **Modular Design**: Reuse everything possible - build once, apply everywhere
5. **Speed WITH Quality**: Can't afford to be slow OR wrong when supporting hundreds of engineers
6. **Human + AI**: AI as a force multiplier, not replacement - augment one person to do the work of a team
7. **Cognitive Protection**: Shield your design thinking from overwhelming technical complexity
8. **Minimal Dependencies**: Works with limited help from time-constrained colleagues
9. **Scale Through Systems**: If it's not systematic, it won't scale

## Documentation

- [README.md](README.md) - Detailed system documentation
- [STRUCTURE.md](STRUCTURE.md) - Complete architecture guide
- [Reference Docs](reference/) - Specifications and standards

## Impact for Solo UX Practitioners

Using this system, a single UX resource can:

- **Process 5-10x more meetings**: Turn hour-long transcripts into actionable outputs in ~20 minutes
- **Stay in UX mode**: System filters technical noise, keeping design decisions primary
- **Maintain consistency**: Every output follows the same high-quality structure
- **Build institutional memory**: Decisions are documented with evidence, not lost in chat
- **Scale influence**: Cover more teams by systematizing common workflows
- **Protect cognitive bandwidth**: Focus on design while system handles technical context
- **Reduce cognitive load**: Let the system handle structure while you focus on user needs
- **Defend decisions**: Every recommendation traces to source material
- **Avoid technical rabbit holes**: Stay focused on UX impact, not implementation debates

## Contributing

This system is designed to be extended by busy practitioners:

1. **New Recipes**: Add variants in `core/recipes/` for your specific workflows
2. **New Protocols**: Create processing rules in `components/protocols/` for your domain
3. **New Templates**: Design output formats in `components/templates/` for your deliverables
4. **New Gates**: Add decision logic in `components/gates/` for your context

Remember: Every improvement helps another overwhelmed UX professional do more with less.

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
