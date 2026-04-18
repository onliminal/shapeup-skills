---
status: Complete
phase: Frame
created: 2026-04-17
updated: 2026-04-17
---

# Framing: Handoff Brief Agent

## Problem

After an escalation call, the owner spends 30-45 minutes assembling an engineering handoff brief from transcript snippets, ticket comments, and personal notes. The result is inconsistent and often missing context, which creates follow-up churn with engineering.

## Who's Affected

Customer success managers and support leads who own urgent escalations and must hand them off cleanly to engineering.

## Current Workaround

Copy/paste from transcript, ticket thread, Slack, and notes into a shared doc or ticket comment, then revise manually.

## Why Now

Escalation volume is high enough that this repeatable writing step is now visible operational drag, and recent evidence suggests a narrow AI draft workflow can help without requiring broad autonomy.

## Appetite

1 week. This is worth a constrained workflow bet, not a generalized escalation assistant.

## Success Criteria

A user can generate a structured draft brief from transcript + ticket context, review it, edit it, and hand off a better brief in meaningfully less time than starting from scratch.

## Open Questions
- What mandatory source inputs make the draft trustworthy enough to use?
- How much source citation is required before users trust the output?
- Should the v1 output live inside an existing ticket/comment workflow or in a standalone draft page?

## Next Best Question
What is the simplest concept that creates a draft users trust enough to edit, without pretending the model can autonomously own escalation decisions?

---

## Conversation Log

The framed problem stayed about one costly repetitive step: writing the handoff brief. Automatic prioritization and routing were explicitly pushed out of scope.
