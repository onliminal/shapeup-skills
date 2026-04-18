---
status: Complete
phase: Shape
created: 2026-04-17
updated: 2026-04-17
---

# Shaping: Handoff Brief Agent

## Concept Summary

A draft-and-review workflow that turns transcript + ticket context into a structured engineering handoff brief with fixed sections and source links.

## Elements

### Input Bundle

A constrained input step that accepts a transcript and linked support ticket context for one escalation.

### Draft Brief

A generated brief with fixed sections such as summary, customer impact, reproduction clues, attempted workarounds, and open risks.

### Review Workspace

A lightweight editor where the human reviews the draft, sees source links, edits content, and finalizes the handoff.

## Flow

User selects or uploads the source bundle, generates the draft, reviews and edits it in place, then copies or pushes the final brief into the existing engineering handoff destination.

## Boundaries

### In Scope
- One escalation at a time
- Transcript + ticket input
- Structured brief draft
- Human review before handoff

### Out of Scope
- Autonomous severity decisions
- Automatic follow-up email generation
- Multi-step agent chains
- Direct auto-send to engineering without review

## Open Questions
- What exact source-link treatment is enough to build trust without cluttering the editor?
- Should the product require both transcript and ticket, or allow a transcript-only fallback?
- Is copy-out enough for v1, or does pushing into the existing handoff destination matter immediately?

## Next Best Question
Which trust and reliability risks could most easily make the workflow feel like a demo instead of a usable handoff tool?

---

## Conversation Log

The concept got stronger as it got narrower. The user initially wanted an "AI agent," but the shaped solution became a fixed draft-and-review workflow around one recognizable artifact.
