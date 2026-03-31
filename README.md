# Shape Up Skill for Claude Code

A [Claude Code skill](https://code.claude.com/docs/en/skills) that guides you through the [Shape Up](https://basecamp.com/shapeup) product planning methodology. Instead of generating documents, it conducts structured conversations that pull information out of your head, challenge your assumptions, and produce clear artifacts.

Works for solo builders and teams alike.

## What it does

The skill walks you through four phases:

1. **Frame** — Define the real problem, who it affects, and how much time it's worth (appetite)
2. **Shape** — Find the elements of a solution at fat-marker fidelity with explicit boundaries
3. **De-risk** — Stress-test the concept for rabbit holes, unknowns, and scope bombs
4. **Pitch** — Synthesize everything into a decision document for the build phase

Each phase produces a markdown artifact in your project's `shaping/` directory. The skill tracks progress via YAML frontmatter, so you can resume across sessions.

## Install

Copy or symlink the `shapeup/` directory into your Claude Code skills location:

```bash
# Personal (available across all your projects)
cp -r shapeup ~/.claude/skills/shapeup

# Project-specific
cp -r shapeup .claude/skills/shapeup
```

## Usage

The skill triggers automatically when you mention shaping, framing, pitching, appetite, or related concepts. You can also invoke it directly:

```
/shapeup
```

Or start at a specific phase:

```
Frame this problem for me
Help me shape a solution
De-risk this concept
Write a pitch
```

The skill detects prior work in `shaping/` and picks up where you left off.

## Skill structure

```
shapeup/
├── SKILL.md                    # Entrypoint — routing logic and core behavior
├── references/
│   ├── frame.md                # Framing conversation protocol
│   ├── shape.md                # Shaping conversation protocol
│   ├── derisking.md            # De-risking conversation protocol
│   └── pitch.md                # Pitch assembly protocol
└── templates/
    └── pitch.md                # Output template for the final pitch document
```

## Output

Artifacts are written to `shaping/{project-slug}/` in your project root:

```
shaping/
└── invoice-autopay/
    ├── frame.md                # Problem, appetite, success criteria
    ├── shape.md                # Elements, boundaries, flow
    ├── risks.md                # Rabbit holes, patches, cut order
    └── pitch.md                # Final pitch / kickoff document
```

## Credits

Based on [Shape Up](https://basecamp.com/shapeup) by Ryan Singer.
