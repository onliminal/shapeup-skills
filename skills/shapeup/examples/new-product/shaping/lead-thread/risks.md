---
status: Complete
phase: Derisking
created: 2026-04-17
updated: 2026-04-17
---

# De-risking: Lead Thread

## Technical Unknowns
| Risk | Severity | Mitigation |
|------|----------|------------|
| SMS ingestion setup is slower than expected | high | Start with one constrained capture path, not generic multi-provider support |
| Duplicate lead merging becomes messy | medium | Make merge manual in v1 |
| Email parsing is inconsistent | medium | Accept forwarded-thread formatting limits and support only simple ingestion patterns |

## Rabbit Holes
| Hole | Patch |
|------|-------|
| Trying to support every inbound channel | Start with email + one SMS path only |
| Building CRM fields and deal stages | Keep only lead timeline + follow-up state |
| Designing automation rules | Manual snooze only in v1 |

## Design Risks

The inbox could become too dense if it tries to show too much channel detail. Mitigation: emphasize latest touchpoint, next follow-up state, and name only.

## Scope Priority (cut order)
1. **Must ship**: inbox, timeline, manual follow-up state
2. **Should ship**: overdue highlighting
3. **Nice to have**: inbox filtering and manual duplicate merge helpers

## Dependencies

One working SMS capture path and one simple email-forwarding ingestion path. Both can be narrowed before the build starts.

## Biggest Risk

The wedge drifts into "general CRM for contractors." The plan is to patch that by defending the boundary: pre-booking thread and follow-up queue only.

## Open Questions
- Which SMS setup path is fastest to ship without killing trust?
- Is overdue highlighting necessary in the first release, or can it ship as a plain state list?
- What exact duplicate pattern is common enough to deserve manual merge?

## Next Best Question
What is the first implementation choice that most reduces platform risk while preserving the one-thread, one-queue experience?

---

## Conversation Log

The biggest risk was not technical novelty; it was scope drift. Each risk discussion that pulled toward automation, CRM records, or broad integrations was patched back down to a one-week wedge.
