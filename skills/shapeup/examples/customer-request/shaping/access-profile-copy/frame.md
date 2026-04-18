---
status: Complete
phase: Frame
created: 2026-04-17
updated: 2026-04-17
---

# Framing: Access Profile Copy

## Problem

Enterprise admins repeatedly rebuild the same access profile by hand when onboarding new users with similar responsibilities. A hospital-network admin had to recreate the same regional-manager access package six times by comparing screens side by side.

## Who's Affected

Customer admins managing complex role and scope combinations for repeated job types.

## Current Workaround

Open an existing user in one tab, compare permissions manually, re-enter the same settings on the new user, then re-check for mistakes.

## Why Now

The request is recurring across multiple enterprise accounts, and the current workaround is slow enough to show up during onboarding spikes.

## Appetite

2-3 days. This is worth a focused productivity improvement, not a permissions-system redesign.

## Success Criteria

An admin creating or editing a user can copy supported access settings from an existing user, review the result, and save without recreating the same setup manually.

## Open Questions
- Which permission categories are safe to copy in v1?
- Does the review step need a visible diff, or is populated form state enough?
- Where should the action live so it feels obvious during onboarding?

## Next Best Question
What is the simplest concept that removes repetitive re-entry without introducing a generalized template system?

---

## Conversation Log

The conversation repeatedly returned from "customers want clone permissions" to the onboarding repetition story. Bulk onboarding and reusable templates were both treated as adjacent problems, not part of this bet.
