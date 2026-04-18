---
status: Complete
phase: Shape
created: 2026-04-17
updated: 2026-04-17
---

# Shaping: Ops Exception Queue

## Concept Summary

A small internal queue where analysts can claim billing exceptions, inspect the relevant context, leave a resolution note, and mark the item resolved or escalated.

## Elements

### Exception Queue

A table of open exceptions with age, source job, account identifier, and owner status.

### Exception Detail Panel

A focused detail view with the failing record, error reason, latest import attempt, and links to the admin panel and Slack thread.

### Resolution Action Bar

Fixed actions for `claim`, `resolve`, and `escalate`, plus a short note field.

## Flow

Analyst opens the queue, claims an exception, reviews the detail panel, adds a note, then resolves or escalates it. Escalated items remain visible with a clear status until picked up.

## Boundaries

### In Scope
- Queue of open exceptions
- Claim/owner status
- Resolution and escalation actions
- Short resolution notes

### Out of Scope
- Analytics dashboards
- Custom workflow configuration
- Bulk editing
- Slack comment sync

## Open Questions
- Should resolved items remain searchable in this tool or only in the source system?
- Does escalation require a dedicated owner, or is status enough?
- How much error payload detail can the panel show without becoming unreadable?

## Next Best Question
Which risks would most likely turn this focused queue into a more expensive workflow system?

---

## Conversation Log

The shape stayed intentionally operational. A reporting tab, flexible statuses, and bulk actions were all cut to preserve the three-day appetite.
