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
├── CHANGELOG.md                   # Release notes by plugin version
├── .claude-plugin/
│   ├── plugin.json                 # Plugin manifest
│   └── marketplace.json            # Marketplace catalog
├── skills/
│   └── shapeup/                    # Skill directory
│       ├── SKILL.md                # Entrypoint (skill definition + routing logic)
│       ├── examples/
│       │   ├── README.md           # Example index and usage notes
│       │   ├── new-product/        # Sample run: new product idea
│       │   ├── internal-tool/      # Sample run: internal ops tool
│       │   ├── customer-request/   # Sample run: customer request reframed
│       │   └── ai-workflow/        # Sample run: AI/workflow concept
│       ├── references/
│       │   ├── explore.md          # Explore conversation protocol
│       │   ├── evidence.md         # Lightweight evidence / experiment protocol
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

The skill turns the agent into a structured interviewer that guides users through the core Shape Up phases plus optional upstream phases:

- **Explore** — Diverge across the idea space and surface candidate wedges.
- **Evidence** — Run lightweight experiments when a promising wedge still needs real-world signal before it deserves appetite.
- **Frame** — Interrogate the problem (not the solution). Push for specifics, stories, appetite.
- **Shape** — Collaboratively find solution elements at fat-marker fidelity. Breadboard flows, set boundaries.
- **De-risk** — Adversarially stress-test the concept for rabbit holes, unknowns, and scope bombs.
- **Pitch** — Synthesize everything into a single betting document.

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
- Examples (examples/*) are illustrative sample runs. They should teach tone, pacing, and artifact quality, but they are not normative protocol docs.
- templates/pitch.md is the only template file — it defines the output format for the final artifact.
- SKILL.md ties everything together and should stay in sync with the reference docs if phase structure changes.
- All file references in SKILL.md use `${CLAUDE_SKILL_DIR}` — keep this convention when adding new files.

## Versioning Rules

- Treat `.claude-plugin/plugin.json` as the canonical release version for the installable plugin.
- Treat `CHANGELOG.md` as the canonical release-note history for shipped versions.
- If a change affects what an installed user gets or how the skill behaves, bump the version in `.claude-plugin/plugin.json` in the same change set.
- If `.claude-plugin/plugin.json` changes, `CHANGELOG.md` must be updated in the same change set. Do not defer release-note updates to a follow-up commit.
- Use semantic versioning:
  - Patch (`1.0.0` -> `1.0.1`): Backward-compatible fixes or refinements to existing behavior. Examples: tightening prompts in `SKILL.md` or `references/*.md`, template improvements, metadata fixes, or other changes that improve the current workflow without expanding scope.
  - Minor (`1.0.0` -> `1.1.0`): Backward-compatible capability additions or meaningful expansions. Examples: adding a new subskill/reference/template, expanding artifact structure, adding a new optional workflow, or materially broadening routing/phase behavior.
  - Major (`1.0.0` -> `2.0.0`): Breaking changes that invalidate prior expectations or require migration. Examples: renaming/removing phases or artifact files, changing output conventions or frontmatter schema incompatibly, changing directory/layout expectations, or altering the methodology in a way that makes prior artifacts or instructions no longer line up.
- Format changelog entries in reverse chronological order using version headings like `## [1.2.1] - 2026-04-18` and concise user-facing sections such as `Added`, `Changed`, and `Fixed`.
- Changelog entries should summarize shipped behavior and user-visible capability changes, not reproduce raw commit messages.
- If you are still working on an unreleased version already reflected in `.claude-plugin/plugin.json`, keep updating that version's changelog entry instead of creating another version bump just for docs.
- Do not skip version bumps for shipped behavior changes just because the change is "only docs." In this repo, `SKILL.md`, `references/*.md`, and `templates/*.md` define product behavior.
- Do not bump the plugin version for repo-only maintenance that does not affect installed behavior. Examples: edits limited to `AGENTS.md`, `CLAUDE.md`, `CHANGELOG.md` backfills, CI, local tooling, or contributor notes.
- Repo-only maintenance that does not bump the version also does not require a changelog update unless it improves the entry for an already-unreleased version.
- When in doubt between patch and minor, prefer minor. When in doubt between minor and major, call out the migration risk explicitly and decide deliberately.
