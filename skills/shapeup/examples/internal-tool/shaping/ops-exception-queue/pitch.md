---
status: complete
phase: pitch
created: 2026-04-17
updated: 2026-04-17
appetite: 3 days
---

# Pitch: Ops Exception Queue

## Problem

Finance ops analysts currently triage billing import exceptions in Slack, which means ownership is ambiguous, investigation gets duplicated, and unresolved issues disappear under new alerts. The current workaround is a mix of screenshots, memory, and occasional spreadsheets.

## Appetite

**3 days** — enough to create a trustworthy queue and ownership flow, but not enough to build an internal workflow platform.

## Solution

Build a small internal exception queue with clear ownership and fixed resolution actions.

### Elements

#### Exception Queue

A list of open exceptions showing age, import source, account identifier, and current owner.

#### Detail Panel

A focused view of the failing record, error reason, latest attempt metadata, and links to source systems.

#### Resolution Actions

Claim, resolve, or escalate, plus a short note field for handoff context.

### Flow

Analyst opens queue, claims one exception, inspects details, leaves a note if needed, then resolves or escalates. The queue makes ownership visible so the same issue is not investigated twice.

## Rabbit Holes

- **Workflow creep**: fixed statuses only
- **Reporting creep**: no charts, history dashboards, or analytics
- **Slack sync complexity**: link out to Slack instead of syncing comments

## No-Gos

- Bulk actions: out because they are not needed to prove the ownership fix
- Custom statuses: out because they create workflow-system complexity
- Trend reporting: out because this bet is about operations, not analysis

---

## Kickoff Context

### Where to Start

Start with the queue table and ownership model, then wire the detail panel and resolution actions.

### Scope Hammer (Cut Order)

If time runs short, cut in this order (bottom up):

1. **Must ship**: queue, claim ownership, resolve/escalate
2. **Should ship**: short resolution notes
3. **Nice to have**: filters and history

### Open Questions for Builders

- How should optimistic locking behave if two analysts claim the same exception nearly simultaneously?
- Which minimal exception fields need normalization before the UI can rely on them?

## Open Questions

- Should claimed items auto-expire if left untouched?
- Is a resolved history view needed immediately for auditing?
- What amount of raw payload detail is still usable in the detail panel?

## Next Best Question

What ownership model is simplest to implement while still preventing duplicate investigation from day one?
