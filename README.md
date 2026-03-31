# Shape Up Skills

An [agent skill](https://agentskills.io/home) that guides you through the [Shape Up](https://basecamp.com/shapeup) product planning methodology. Instead of generating documents, it conducts structured conversations that pull information out of your head, challenge your assumptions, and produce clear artifacts.

Works with any [compatible agent](https://agentskills.io/home) and for solo builders and teams alike.

## What it does

The skill walks you through four phases:

1. **Frame** — Define the real problem, who it affects, and how much time it's worth (appetite)
2. **Shape** — Find the elements of a solution at fat-marker fidelity with explicit boundaries
3. **De-risk** — Stress-test the concept for rabbit holes, unknowns, and scope bombs
4. **Pitch** — Synthesize everything into a decision document for the build phase

And an optional upstream phase:

0. **Explore** — For product-level ideas that aren't yet a specific feature or problem. Map the problem space, find the people, understand the landscape, and identify the sharpest wedge to pursue. Output: candidate problems ready for framing.

Each phase produces a markdown artifact in your project's `shaping/` directory. The skill tracks progress via YAML frontmatter, so you can resume across sessions.

## Install

### Claude Code plugin (recommended)

```bash
# Add the marketplace and install
/plugin marketplace add onliminal/shapeup-skills
/plugin install shapeup@shapeup-skills
```

Or test locally:

```bash
claude --plugin-dir ./path/to/shapeup-skills
```

### Claude Code standalone skill

Copy or symlink the skill directory:

```bash
# Personal (available across all projects)
cp -r skills/shapeup ~/.claude/skills/shapeup

# Project-specific
cp -r skills/shapeup .claude/skills/shapeup
```

See the [Claude Code skills documentation](https://code.claude.com/docs/en/skills) for more details.

### Codex CLI

```bash
cp -r skills/shapeup ~/.codex/skills/shapeup
```

See the [Agent Skills specification](https://agentskills.io/specification) for the standard skill format.

### OpenCode

Clone the repo into the OpenCode skills directory:

```bash
git clone https://github.com/onliminal/shapeup-skills.git ~/.opencode/skills/shapeup-skills
```

OpenCode auto-discovers all `SKILL.md` files under `~/.opencode/skills/`. No config changes needed — restart OpenCode to activate.

### Other agents

Any agent that supports the [Agent Skills format](https://agentskills.io/specification) (Cursor, Gemini CLI, VS Code Copilot, Goose, Roo Code, etc.) can use this skill — consult your agent's documentation for the skills directory path.

## Usage

The skill triggers automatically when you mention shaping, framing, pitching, appetite, or related concepts. You can also start at a specific phase:

```
I have a product idea I want to explore
Frame this problem for me
Help me shape a solution
De-risk this concept
Write a pitch
```

The skill detects prior work in `shaping/` and picks up where you left off.

## Project structure

```
shapeup-skills/                     # Plugin root
├── .claude-plugin/
│   ├── plugin.json                 # Plugin manifest
│   └── marketplace.json            # Marketplace catalog
├── skills/
│   └── shapeup/                    # Skill directory
│       ├── SKILL.md                # Entrypoint — routing logic and core behavior
│       ├── references/
│       │   ├── explore.md          # Explore conversation protocol
│       │   ├── frame.md            # Framing conversation protocol
│       │   ├── shape.md            # Shaping conversation protocol
│       │   ├── derisking.md        # De-risking conversation protocol
│       │   └── pitch.md            # Pitch assembly protocol
│       └── templates/
│           └── pitch.md            # Output template for the final pitch document
├── CLAUDE.md
└── README.md
```

## Output

Artifacts are written to `shaping/{project-slug}/` in your project root:

```
shaping/
└── invoice-autopay/
    ├── explore.md              # Problem space, people, wedges (optional)
    ├── frame.md                # Problem, appetite, success criteria
    ├── shape.md                # Elements, boundaries, flow
    ├── risks.md                # Rabbit holes, patches, cut order
    └── pitch.md                # Final pitch / kickoff document
```

## Credits

Based on [Shape Up](https://basecamp.com/shapeup) by Ryan Singer.
