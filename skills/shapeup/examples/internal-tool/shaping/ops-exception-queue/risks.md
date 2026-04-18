---
status: Complete
phase: Derisking
created: 2026-04-17
updated: 2026-04-17
---

# De-risking: Ops Exception Queue

## Technical Unknowns
| Risk | Severity | Mitigation |
|------|----------|------------|
| Exception payloads are inconsistent across import jobs | medium | Normalize a minimal shared detail schema for the queue |
| Ownership updates race when two analysts click at once | medium | Use optimistic locking and a visible "claimed by" state |

## Rabbit Holes
| Hole | Patch |
|------|-------|
| Building flexible workflow states | Fixed statuses only: open, claimed, resolved, escalated |
| Turning the tool into reporting | No charts or trend views in this bet |
| Syncing full discussion threads with Slack | Link out to Slack instead of syncing comments |

## Design Risks

The detail panel could become overwhelming if it exposes raw import payloads. Mitigation: show only the fields analysts need to decide whether to resolve or escalate.

## Scope Priority (cut order)
1. **Must ship**: queue, claim ownership, resolve/escalate actions
2. **Should ship**: short resolution notes
3. **Nice to have**: saved filters and history views

## Dependencies

Read access to import logs and the existing employee auth system. No external team dependency beyond confirming the escalation destination.

## Biggest Risk

The team starts asking for generic case-management features. The patch is to hold the boundary at exception ownership and resolution only.

## Open Questions
- What exact fields belong in the shared exception detail schema?
- Does the team need a resolved-item history immediately, or can that stay in the source system?
- Should claimed items auto-expire back to open after inactivity?

## Next Best Question
What is the minimum claim-and-resolve model that prevents duplicate work without adding workflow complexity?

---

## Conversation Log

Most risks traced back to over-generalization. The concept stayed safe once the scope was pinned to ownership, detail, and resolution.
