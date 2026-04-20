---
status: Complete
phase: Pitch
created: 2026-04-17
updated: 2026-04-17
appetite: 2-3 days
---

# Pitch: Access Profile Copy

## Problem

Admins at enterprise accounts repeatedly recreate the same access setup during onboarding by comparing one user screen against another and re-entering the same permissions manually. This is slow, error-prone, and especially painful when multiple hires share the same role profile.

## Appetite

**2-3 days** — enough to eliminate repetitive onboarding clicks, not enough to redesign permissions management.

## Solution

Add a "copy access from existing user" action within the current user-edit flow.

### Elements

#### Source User Picker

Choose an existing user in the same tenant as the source profile.

#### Prefilled Access Form

Populate supported permission and scope fields into the current draft user.

#### Review Step

Show the source user and copied fields clearly before save.

### Flow

Admin starts onboarding a new user, chooses an existing user as the source, reviews the copied access settings, adjusts anything needed, and saves.

## Rabbit Holes

- **Template drift**: this is not a reusable template system
- **Bulk-onboarding drift**: one-user copy only
- **Unsafe permission copying**: support only explicit safe categories in v1

## No-Gos

- Cross-tenant copying: out because it complicates scope and safety immediately
- Bulk onboarding: out because it is a separate workflow with different failure modes
- Rich permission-diff explorer: out because the wedge is onboarding speed, not permissions education

---

## Kickoff Context

### Where to Start

Start by defining the copyable permission set and wiring it into the existing user-edit flow before designing any richer review treatment.

### Scope Hammer (Cut Order)

If time runs short, cut in this order (bottom up):

1. **Must ship**: source picker, safe permission copy, review before save
2. **Should ship**: copied-field annotations
3. **Nice to have**: richer diff display

### Open Questions for Builders

- How should invalid copied permissions be surfaced during review?
- What visual treatment best signals "copied from {user}" without adding a full diff mode?

## Open Questions

- Which permissions stay manual in v1?
- Does the review step need to be separate, or can the existing form carry the signal?
- How much customer messaging is needed so this feature is not misunderstood as a role-template system?

## Next Best Question

What exact safe-copy boundary preserves most onboarding value while keeping the implementation and trust model simple?
