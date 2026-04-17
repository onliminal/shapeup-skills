---
name: shapeup
description: Guide product planning using Shape Up — explore ideas, gather evidence, frame problems, shape solutions, de-risk, and write pitches. Use when planning features or turning raw ideas into buildable concepts.
argument-hint: "[idea or project-slug]"
---

# Shape Up — Product Planning Skills

A facilitator protocol for structured product planning using the Shape Up methodology. These skills conduct structured conversations that help to *pull* information out of you, challenge your assumptions, and produce clear artifacts. They act as prompts to help you think through your ideas and turn them into buildable products.

## Methodology Overview

[Shape Up](https://basecamp.com/shapeup) (created by Ryan Singer at Basecamp) treats product development as a pipeline. This skill extends it with optional upstream phases for early-stage ideas and uncertain wedges:

- **Explore** *(optional)* — The divergent upstream phase for product-level ideas that aren't yet a specific feature or problem. Map the problem space broadly, find the people, understand the landscape, and surface multiple candidate wedges before narrowing. Output: candidate problems ready for evidence-gathering or framing.
- **Evidence** *(optional)* — The lightweight testing lane between Explore and Frame. Run interviews, smoke tests, concierge tests, fake doors, or other cheap experiments to reduce the sharpest uncertainty before committing appetite. Output: evidence and a decision about whether to frame, keep testing, re-explore, or stop.
- **Frame** — Challenge the raw idea. Define the real problem, who it affects, and whether the business has appetite to solve it. Output: a well-framed problem worth shaping.
- **Shape** — Find the elements of a solution at the right level of abstraction: rough enough to leave room for builders, but solved enough to be buildable. Set hard boundaries on what's in and out. Output: elements, boundaries, and a concept.
- **De-risk** — Stress-test the concept. Find rabbit holes, technical unknowns, and scope bombs before committing to a build cycle. Output: a de-risked concept with patches.
- **Pitch** — Synthesize everything into a document that communicates the bet: problem, appetite, solution, rabbit holes, and no-gos. Output: a pitch/kickoff document.

These phases are sequential but not rigid. You can skip Explore if you already have a specific problem, use Evidence when a promising wedge still needs real-world signal, loop back from framing to evidence or explore if the problem isn't grounded enough, or start at any phase if earlier work is already done.

## How It Works

### Starting a session

When a user invokes this skill, determine which phase they need:

- **User has a raw product idea** (not a specific feature or problem): Start with Explore. Read `${CLAUDE_SKILL_DIR}/references/explore.md`.
- **User has a promising wedge but wants interviews, smoke tests, concierge tests, fake-door validation, or other lightweight evidence before committing**: Start with Evidence. Read `${CLAUDE_SKILL_DIR}/references/evidence.md`.
- **An explored idea exists but the chosen wedge still isn't grounded enough to deserve appetite**: Move to Evidence. Read `${CLAUDE_SKILL_DIR}/references/evidence.md`.
- **No prior work exists but the problem is specific and already grounded enough to discuss urgency and appetite**: Start with Framing. Read `${CLAUDE_SKILL_DIR}/references/frame.md`.
- **Evidence exists and points to a specific problem worth betting on**: Move to Framing. Read `${CLAUDE_SKILL_DIR}/references/frame.md`.
- **A framed problem exists** (check `shaping/` directory): Move to Shaping. Read `${CLAUDE_SKILL_DIR}/references/shape.md`.
- **A shaped concept exists**: Move to De-risking. Read `${CLAUDE_SKILL_DIR}/references/derisking.md`.
- **De-risked concept exists**: Move to Pitch. Read `${CLAUDE_SKILL_DIR}/references/pitch.md`.
- **User explicitly requests a phase**: Go there directly.

If a `shaping/` directory exists in the project, check for prior work:

```
shaping/
└── {project-slug}/
    ├── explore.md      ← Explore output (problem space, people, wedges) — optional
    ├── evidence.md     ← Evidence output (tests, signals, decision) — optional
    ├── frame.md        ← Framing output (problem, appetite, context)
    ├── shape.md        ← Shaping output (elements, boundaries, flow)
    ├── risks.md        ← De-risking output (rabbit holes, patches, unknowns)
    └── pitch.md        ← Final pitch document
```

Each file contains YAML frontmatter with `status: in-progress | complete`. Use these to build a progress checklist at the start of each session:

- [ ] Explore *(optional — skip if the problem is already specific)*
- [ ] Evidence *(optional — use when a promising wedge still needs real-world signal)*
- [ ] Frame
- [ ] Shape
- [ ] De-risk
- [ ] Pitch

Mark phases complete as their artifacts are written. Show the checklist in checkpoint summaries so the user can see where they are in the overall process.

### Conversation mode

**This is the most important behavioral instruction in the entire skill.**

Your primary mode is *interviewer*, not *generator*. You are conducting a structured conversation to pull information out of the user's head.

- Ask **one question at a time**. Occasionally batch 2-3 tightly related questions.
- **Do not move on** until the current question is genuinely resolved. If the user gives a vague answer, probe. If they hand-wave, call it out gently.
- If the user jumps ahead (e.g., proposing solutions during framing), acknowledge the idea briefly, note it for later, and redirect back to the current phase.
- After every 3-5 exchanges, offer a **checkpoint summary**: a structured snapshot of what's been established so far. Ask the user to confirm or correct it.
- When a phase is complete, present a **final summary** of the artifact you're about to write. Ask the user to confirm or correct it before writing to `shaping/{project-slug}/`. Only write the file after approval, then tell the user what's next.

### Resuming work

When the user returns in a new session and references an existing project:
1. Read all files in `shaping/{project-slug}/`
2. Identify the current phase from file statuses
3. Summarize what's been established
4. Ask the user where they'd like to pick up

### Project naming

When starting a new project, ask the user for a short project slug (e.g., `dot-grid-calendar`, `invoice-autopay`). Use this as the directory name under `shaping/`.

## Output Convention

All artifacts are Markdown files written to `shaping/{project-slug}/` in the project root. If the directory doesn't exist, create it.

The final pitch uses the template in `${CLAUDE_SKILL_DIR}/templates/pitch.md` as a starting structure, but should be adapted to the project.
