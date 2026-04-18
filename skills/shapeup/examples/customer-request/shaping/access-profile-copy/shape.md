---
status: Complete
phase: Shape
created: 2026-04-17
updated: 2026-04-17
---

# Shaping: Access Profile Copy

## Concept Summary

Add a "copy access from existing user" action to the existing user-edit flow so admins can prefill supported permissions from a source user, review them, and save.

## Elements

### Source User Picker

A searchable selector for choosing an existing user in the same tenant as the copy source.

### Prefilled Access Form

The existing access form populated with supported copied values rather than forcing manual re-entry.

### Review State

A lightweight review step that shows what was copied and requires the admin to confirm before saving.

## Flow

Admin begins creating or editing a user, chooses "copy access from existing user," selects a source user, reviews the populated permissions and scopes, makes any needed adjustments, then saves.

## Boundaries

### In Scope
- Copy supported permissions from an existing user
- Keep the action inside the current tenant
- Require review before save

### Out of Scope
- Permission templates
- Bulk onboarding
- Cross-tenant copying
- Full diff/explanation tooling for every permission field

## Open Questions
- Which copied fields need explicit badges or annotations in the review state?
- Is the review state a separate step or just highlighted form state?
- What unsupported permission types should remain manual in v1?

## Next Best Question
Which technical and policy constraints decide the safe boundary of what can be copied automatically?

---

## Conversation Log

The concept stayed inside the existing user-edit flow to avoid template-system drift. The main shaping work was finding a minimal review step that still felt safe.
