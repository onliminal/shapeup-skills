---
status: Complete
phase: Frame
created: 2026-04-17
updated: 2026-04-17
---

# Framing: Ops Exception Queue

## Problem

Billing import exceptions are currently triaged through Slack and memory, so ownership is unclear, duplicate investigation happens, and unresolved issues are easy to miss.

## Who's Affected

Three finance operations analysts who clean up import exceptions every morning, plus an engineering-on-call teammate when an issue may be systemic.

## Current Workaround

Slack alerts, screenshots, ad hoc spreadsheets, and checking the admin panel manually.

## Why Now

Exception volume has grown enough that Slack is no longer a trustworthy queue, and duplicated investigation time is starting to affect morning close tasks.

## Appetite

3 days. This is worth a practical internal fix, not a generalized ops platform.

## Success Criteria

An analyst can see new exceptions, claim one, review key details, leave a resolution note, and clearly mark it resolved or escalated.

## Open Questions
- Should the queue show only unclaimed exceptions first, or all open exceptions sorted by age?
- Is one freeform resolution-note field enough for v1?
- What minimum detail belongs in the exception view before analysts still need to bounce into the admin panel?

## Next Best Question
What is the simplest shaped flow that creates clear ownership and resolution without turning this into a workflow engine?

---

## Conversation Log

The conversation began as a dashboard request and got reframed into an ownership-and-resolution problem. Analytics and reporting were explicitly deferred.
