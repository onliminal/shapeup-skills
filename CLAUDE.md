# Shape Up Skills

An [Agent Skill](https://agentskills.io) for structured product planning using the Basecamp Shape Up methodology.

## Installation

### As a plugin (recommended)

```bash
# Add the marketplace and install
/plugin marketplace add onliminal/shapeup-skills
/plugin install shapeup@shapeup-skills
```

### Manual (standalone skill)

Copy or symlink the skill directory:

```bash
# Personal (available across all projects)
cp -r skills/shapeup ~/.claude/skills/shapeup

# Or project-specific
cp -r skills/shapeup .claude/skills/shapeup
```

## Project Structure

```
shapeup-skills/                     # Plugin root
├── .claude-plugin/
│   ├── plugin.json                 # Plugin manifest
│   └── marketplace.json            # Marketplace catalog
├── skills/
│   └── shapeup/                    # Skill directory
│       ├── SKILL.md                # Entrypoint (skill definition + routing logic)
│       ├── references/
│       │   ├── explore.md          # Explore conversation protocol
│       │   ├── frame.md            # Framing phase conversation protocol
│       │   ├── shape.md            # Shaping phase conversation protocol
│       │   ├── derisking.md        # De-risking phase conversation protocol
│       │   └── pitch.md            # Pitch assembly protocol
│       └── templates/
│           └── pitch.md            # Pitch output template with YAML frontmatter
├── CLAUDE.md
└── README.md
```

## How the Skill Works

The skill turns the agent into a structured interviewer that guides users through four sequential phases:

1. **Frame** — Interrogate the problem (not the solution). Push for specifics, stories, appetite.
2. **Shape** — Collaboratively find solution elements at fat-marker fidelity. Breadboard flows, set boundaries.
3. **De-risk** — Adversarially stress-test the concept for rabbit holes, unknowns, and scope bombs.
4. **Pitch** — Synthesize everything into a single betting document.

The core behavioral rule: ask one question at a time, don't generate artifacts until the conversation is complete. The agent is an interviewer, not a document generator.

## Key Design Decisions

- Each phase has its own reference doc with a complete conversation protocol (question flow, checkpoint patterns, failure modes)
- SKILL.md is the entrypoint that routes to the correct phase based on prior work in `shaping/`
- Supporting files are referenced via `${CLAUDE_SKILL_DIR}` so paths resolve regardless of install location
- Artifacts use YAML frontmatter with `status: in-progress | complete` for resumability
- Appetite scales are adjusted for agentic tooling (shorter windows, same ambition)
- The pitch template includes a "Scope Hammer" cut order for time pressure

## Editing Guidelines

- Reference docs (references/*.md) are conversation protocols, not templates. They define how the agent should behave in each phase.
- templates/pitch.md is the only template file — it defines the output format for the final artifact.
- SKILL.md ties everything together and should stay in sync with the reference docs if phase structure changes.
- All file references in SKILL.md use `${CLAUDE_SKILL_DIR}` — keep this convention when adding new files.
