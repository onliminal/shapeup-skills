---
status: Complete
phase: Pitch
created: 2026-04-17
updated: 2026-04-17
appetite: 1 week
---

# Pitch: Handoff Brief Agent

## Problem

After an escalation call, customer-facing owners spend 30-45 minutes assembling an engineering handoff brief from transcript snippets, ticket comments, and personal notes. The result is slow to produce, inconsistent in quality, and often missing context that engineering then has to ask for again.

## Appetite

**1 week** — enough to create a useful draft-and-review workflow, not enough to justify an autonomous escalation assistant.

## Solution

Build a workflow that takes a transcript plus ticket context, generates a structured draft handoff brief, and requires a human review before the brief is handed to engineering.

### Elements

#### Input Bundle

One transcript and one support ticket context source for a single escalation.

#### Draft Brief

Fixed sections for summary, customer impact, reproduction clues, attempted workarounds, and open risks.

#### Review Workspace

An editable draft with source references so the owner can confirm, revise, and finalize the handoff.

### Flow

User selects the escalation sources, generates a draft, reviews and edits it, then copies or pushes the final brief into the existing engineering handoff path.

## Rabbit Holes

- **Automation theater**: no autonomous routing or handoff without review
- **Source sprawl**: transcript + ticket only in v1
- **Trust collapse**: show clear source grounding and design for editing, not blind acceptance

## No-Gos

- Severity recommendation: out because it changes the trust and decision surface
- Follow-up email drafting: out because it is a separate artifact for a different audience
- Multi-step agent workflow: out because it adds orchestration complexity before the core brief is proven

---

## Kickoff Context

### Where to Start

Start with one internal escalation format and produce the fixed-section draft before solving downstream integrations.

### Scope Hammer (Cut Order)

If time runs short, cut in this order (bottom up):

1. **Must ship**: source input, draft brief, human review
2. **Should ship**: source links
3. **Nice to have**: push into downstream tool

### Open Questions for Builders

- What source-link pattern best supports review without clutter?
- Is copy-out sufficient for the first internal users, or do they need direct push into the ticketing workflow?

## Open Questions

- Which source fields are mandatory for a trustworthy first draft?
- How much prompt or model variance can the team tolerate before the draft feels unreliable?
- What editor constraints keep users reviewing instead of over-trusting?

## Next Best Question

What single trust-building design choice most increases the chance that users will edit-and-send instead of rewrite from scratch?
