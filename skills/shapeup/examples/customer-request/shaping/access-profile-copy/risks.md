---
status: Complete
phase: De-risking
created: 2026-04-17
updated: 2026-04-17
---

# De-risking: Access Profile Copy

## Technical Unknowns
| Risk | Severity | Mitigation |
|------|----------|------------|
| Some permission types cannot safely copy 1:1 | high | Support a limited set of copyable categories in v1 |
| Tenant or scope rules could create invalid copied states | medium | Restrict copying to same-tenant users and revalidate on save |

## Rabbit Holes
| Hole | Patch |
|------|-------|
| Building reusable role templates | Keep the feature as one-user-to-another copy only |
| Adding bulk onboarding | Explicitly out of scope |
| Explaining every copied permission in a new diff UI | Use a lightweight review state only |

## Design Risks

Admins may not trust silent copying. Mitigation: show the source user clearly and highlight copied fields before save.

## Scope Priority (cut order)
1. **Must ship**: source picker, supported permission copy, review before save
2. **Should ship**: clear annotations for copied fields
3. **Nice to have**: richer diff/explanation view

## Dependencies

Access to existing permission-validation logic and agreement on which permission categories are safe to copy in v1.

## Biggest Risk

The feature becomes the first step toward generalized RBAC redesign. The patch is to hold the line at onboarding acceleration for repeated user profiles.

## Open Questions
- Which permission categories are explicitly safe for v1?
- Is copied-form highlighting enough to build trust?
- What validation message appears when a copied setting is no longer valid?

## Next Best Question
What minimum copyable-permission set delivers most of the onboarding value without triggering unsafe edge cases?

---

## Conversation Log

The main risk work was policy and product-boundary related, not implementation novelty. Nearly every rabbit hole came from trying to turn one repeated onboarding action into a general permissions product.
