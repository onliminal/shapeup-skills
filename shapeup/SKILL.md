---
name: shapeup
description: >
  Structured product planning using the Shape Up methodology. Use this skill whenever the use wants to plan a feature, frame a problem, shape a solution, identify risks, or write a pitch for a product idea. Trigger on phrases like "shape this", "frame this problem", "write a pitch", "plan this feature", "what should we build", "scope this", "de-risk this", or any reference to Shape Up, framing, shaping, appetite, rabbit holes, or fat-marker sketches. Also trigger when a user has a raw product idea and needs help turning it into something buildable. Works for solo builders and teams alike.
---

# Shape Up — Product Planning Skills

A facilitator protocol for structured product planning using the Shape Up methodology. These skills conduct structured conversations that help to *pull* information out of you, challenge your assumptions, and produce clear artifacts. They act as prompts to help you think through your ideas and turn them into buildable products.

## Methodology Overview

[Shape Up](https://basecamp.com/shapeup) (created by Ryan Singer at Basecamp) treats product development as a pipeline. This skill extends it with an optional upstream phase for early-stage product ideas:

0. **Explore** *(optional)* — For product-level ideas that aren't yet a specific feature or problem. Map the problem space, find the people, understand the landscape, and identify the sharpest wedge to pursue. Output: candidate problems ready for framing.

1. **Frame** — Challenge the raw idea. Define the real problem, who it affects, and whether the business has appetite to solve it. Output: a well-framed problem worth shaping.

2. **Shape** — Find the elements of a solution at the right level of abstraction: rough enough to leave room for builders, but solved enough to be buildable. Set hard boundaries on what's in and out. Output: elements, boundaries, and a concept.

3. **De-risk** — Stress-test the concept. Find rabbit holes, technical unknowns, and scope bombs before committing to a build cycle. Output: a de-risked concept with patches.

4. **Pitch** — Synthesize everything into a document that communicates the bet: problem, appetite, solution, rabbit holes, and no-gos. Output: a pitch/kickoff document.

These phases are sequential but not rigid. You can loop back from de-risking to reshaping, skip Explore if you already have a specific problem, or start at any phase if earlier work is already done.

## How It Works

### Starting a session

When a user invokes this skill, determine which phase they need:

- **User has a raw product idea** (not a specific feature or problem): Start with Explore. Read `${CLAUDE_SKILL_DIR}/references/explore.md`.
- **No prior work exists but the problem is specific**: Start with Framing. Read `${CLAUDE_SKILL_DIR}/references/frame.md`.
- **A framed problem exists** (check `shaping/` directory): Move to Shaping. Read `${CLAUDE_SKILL_DIR}/references/shape.md`.
- **A shaped concept exists**: Move to De-risking. Read `${CLAUDE_SKILL_DIR}/references/derisking.md`.
- **De-risked concept exists**: Move to Pitch. Read `${CLAUDE_SKILL_DIR}/references/pitch.md`.
- **User explicitly requests a phase**: Go there directly.

If a `shaping/` directory exists in the project, check for prior work:

```
shaping/
└── {project-slug}/
    ├── explore.md      ← Explore output (problem space, people, wedges) — optional
    ├── frame.md        ← Framing output (problem, appetite, context)
    ├── shape.md        ← Shaping output (elements, boundaries, flow)
    ├── risks.md        ← De-risking output (rabbit holes, patches, unknowns)
    └── pitch.md        ← Final pitch document
```

Each file contains YAML frontmatter with `status: in-progress | complete` so you can detect where the user left off.

### Conversation mode

**This is the most important behavioral instruction in the entire skill.**

Your primary mode is *interviewer*, not *generator*. You are conducting a structured conversation to pull information out of the user's head.

- Ask **one question at a time**. Occasionally batch 2-3 tightly related questions.
- **Do not move on** until the current question is genuinely resolved. If the user gives a vague answer, probe. If they hand-wave, call it out gently.
- If the user jumps ahead (e.g., proposing solutions during framing), acknowledge the idea briefly, note it for later, and redirect back to the current phase.
- After every 3-5 exchanges, offer a **checkpoint summary**: a structured snapshot of what's been established so far. Ask the user to confirm or correct it.
- When a phase is complete, write the artifact to `shaping/{project-slug}/` and tell the user what's next.

### Resuming work

When the user returns in a new session and references an existing project:
1. Read all files in `shaping/{project-slug}/`
2. Identify the current phase from file statuses
3. Summarize what's been established
4. Ask the user where they'd like to pick up

### Project naming

When starting a new project, ask the user for a short project slug (e.g., `dot-grid-calendar`, `invoice-autopay`). Use this as the directory name under `shaping/`.

## Phase References

Read the appropriate reference file before beginning a phase:

- **Explore**: `${CLAUDE_SKILL_DIR}/references/explore.md`
- **Framing**: `${CLAUDE_SKILL_DIR}/references/frame.md`
- **Shaping**: `${CLAUDE_SKILL_DIR}/references/shape.md`
- **De-risking**: `${CLAUDE_SKILL_DIR}/references/derisking.md`
- **Pitch writing**: `${CLAUDE_SKILL_DIR}/references/pitch.md`

## Output Convention

All artifacts are Markdown files written to `shaping/{project-slug}/` in the project root. If the directory doesn't exist, create it.

The final pitch uses the template in `${CLAUDE_SKILL_DIR}/templates/pitch.md` as a starting structure, but should be adapted to the project.
