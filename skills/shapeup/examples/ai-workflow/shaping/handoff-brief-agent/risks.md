---
status: Complete
phase: De-risking
created: 2026-04-17
updated: 2026-04-17
---

# De-risking: Handoff Brief Agent

## Technical Unknowns
| Risk | Severity | Mitigation |
|------|----------|------------|
| Model output invents details not supported by source material | high | Require fixed sections and source-linked review |
| Transcript quality varies too much for consistent drafts | medium | Support only one transcript source format in v1 and rely on ticket context as backup |
| Token/cost spikes on long escalations | medium | Limit source size and summarize in fixed passes if needed |

## Rabbit Holes
| Hole | Patch |
|------|-------|
| Building an autonomous escalation agent | Human review required before any handoff |
| Supporting every source type immediately | Start with transcript + ticket only |
| Expanding into prioritization and routing | Explicitly out of scope for this bet |

## Design Risks

Users may distrust the draft if it looks too polished but hides weak grounding. Mitigation: emphasize editable sections and clear source references rather than polished prose.

## Scope Priority (cut order)
1. **Must ship**: input bundle, draft brief, human review
2. **Should ship**: source links in the editor
3. **Nice to have**: push into downstream tool instead of copy-out

## Dependencies

Reliable access to transcript and ticket data for one internal escalation workflow. No dependency on full cross-system automation in v1.

## Biggest Risk

The workflow feels clever but untrustworthy, so users still rewrite from scratch. The patch is to design for reviewability, not automation theater.

## Open Questions
- What minimum citation pattern actually increases trust?
- How long can the input bundle get before performance or cost changes the shape of the bet?
- Is copy-out operationally acceptable, or is direct push required for real adoption?

## Next Best Question
What is the smallest trust-building mechanism that makes users willing to edit the draft instead of discarding it?

---

## Conversation Log

Every major risk was tied to overreach: too much autonomy, too many source types, or too much implied trust. The de-risking work kept the concept anchored to draft quality and reviewability.
