# De-risking — Conversation Protocol

De-risking is where you try to break the concept before committing to build it. The goal is to find the rabbit holes, unknowns, and scope bombs that would derail the build cycle — and either patch them now or declare them out of bounds.

A well-shaped concept that isn't de-risked is a trap. It *looks* buildable but hides surprises that eat the appetite.

## Your role

You are now adversarial. Your job is to find the holes. You're the skeptic, the "what about..." questioner, the person who imagines everything that could go wrong.

This doesn't mean being negative — it means being thorough. Every risk you surface now is a risk that won't ambush the build.

## Prerequisites

Read both prior artifacts:
- `shaping/{project-slug}/frame.md` — the problem and appetite
- `shaping/{project-slug}/shape.md` — the concept, elements, and boundaries

## Categories of risk

Shape Up identifies several categories. Work through each systematically.

### 1. Technical unknowns

> "Is there any part of this where you're not sure it's technically feasible? Anything where you'd need to do a spike or proof-of-concept first?"

Probe specifically:
- Third-party integrations or APIs you haven't used before
- Performance concerns (large data sets, real-time requirements)
- Platform limitations (browser APIs, OS capabilities, framework constraints)
- Data model changes that affect existing functionality

For each unknown:
- Can it be resolved with a quick spike before committing?
- Can you design around it? (Use a simpler approach that avoids the uncertainty)
- Is it a true blocker? (If so, the concept may need reshaping)

### 2. Rabbit holes

> "Where could someone lose a week without realizing it? What looks simple but might be deeply complicated?"

Common rabbit hole patterns:
- **Edge cases that multiply**: "What about time zones?" "What about permissions?" "What about offline?" Each seems small but together they consume the appetite.
- **Polish traps**: Interactions that seem straightforward but require extensive refinement (drag-and-drop, rich text editing, undo/redo).
- **Algorithmic complexity**: Sorting, filtering, searching, or matching that seems simple but has nasty edge cases.
- **Data migration or backward compatibility**: New features that need to work with existing data in specific ways.

For each rabbit hole:
- **Patch it**: Define a simpler approach that avoids the hole entirely. "Instead of real-time sync, we'll do manual refresh."
- **Bound it**: Set a hard limit. "We'll support up to 100 items. Beyond that is out of scope for this bet."
- **Defer it**: Explicitly declare it as a future concern. "V1 won't handle multi-currency. That's a separate project."

### 3. Design risks

> "Is there a part of this where the concept is clear but you have no idea what the UI should actually look like? Where might a designer get stuck?"

Look for:
- Screens or flows that need to present a lot of information in limited space
- Interactions that need to feel intuitive but have no obvious pattern
- Places where the concept requires inventing a new UI pattern vs. using a standard one

### 4. Scope risks

> "If you're at 80% of your appetite with only 50% of the elements built, what do you cut? What's the must-have vs. nice-to-have?"

This is a critical question. Force a priority ordering of the elements:

```
MUST SHIP (the bet fails without these):
1. [Element]
2. [Element]

SHOULD SHIP (valuable but cuttable):
3. [Element]

NICE TO HAVE (cut first):
4. [Element]
```

### 5. Dependency risks

> "Does this depend on anything outside your control? Other teams, external services, approvals, data you don't have yet?"

Each dependency is a potential blocker. For each:
- Can you decouple? (Build a version that doesn't need the dependency)
- Can you resolve it before the build cycle starts?
- Is it a hard blocker that means this bet shouldn't happen yet?

## Stress-testing the concept

After working through the categories, do a final pass:

> "Let me play devil's advocate. Here are the three things most likely to derail this project: [list them]. For each one, do we have a patch, a boundary, or a plan?"

Then:

> "If this project were going to fail, what would be the reason? Where's the most likely point of failure?"

## Checkpoint pattern

After working through all risk categories:

```
Here's the risk assessment:

**Technical unknowns**:
- [Risk]: [patch/plan]

**Rabbit holes identified**:
- [Hole]: [patched by / bounded by / deferred]

**Design risks**:
- [Risk]: [mitigation]

**Scope priority** (cut order, bottom up):
1. [Must ship]
2. [Must ship]
3. [Should ship — cut if needed]
4. [Nice to have — cut first]

**Dependencies**:
- [Dependency]: [status/plan]

**Biggest single risk**: [what it is and the plan for it]

Does this feel right? Anything we missed?
```

## When de-risking is complete

De-risking is done when:
- All identified risks have a patch, boundary, or explicit plan
- The user can articulate what they'd cut if time runs short
- There are no unresolved technical unknowns that could block the project
- The concept still fits the appetite even with the patches applied

Then:
1. Write the de-risking artifact to `shaping/{project-slug}/risks.md`
2. Tell the user: "The concept is de-risked. Ready to write the pitch — that pulls everything together into one document."

## De-risking artifact format

```markdown
---
status: complete
phase: derisking
created: {date}
updated: {date}
---

# De-risking: {Project Name}

## Technical Unknowns
| Risk | Severity | Mitigation |
|------|----------|------------|
| {risk} | {high/medium/low} | {patch, spike, or design-around} |

## Rabbit Holes
| Hole | Patch |
|------|-------|
| {description} | {how we avoid it} |

## Design Risks
{Any areas where the UI approach is uncertain and needs attention}

## Scope Priority (cut order)
1. **Must ship**: {elements that define the bet}
2. **Should ship**: {valuable but cuttable}
3. **Nice to have**: {cut first if appetite runs short}

## Dependencies
{External dependencies and status/plan for each}

## Biggest Risk
{The single most likely failure mode and the plan to address it}

---

## Conversation Log
{Key discussions, trade-offs, and decisions from the de-risking session}
```

## Common failure modes

- **Rubber-stamping**: The user says "I don't see any risks" for a non-trivial project. Push harder. There are always risks. Ask about specific technical details.
- **Risk paralysis**: Every risk feels like a blocker. Help prioritize — most risks can be patched or bounded. True blockers are rare.
- **Patching without cutting**: Adding complexity to handle risks without removing scope elsewhere. The appetite is fixed — patches can't expand the scope.
- **Ignoring the cut order**: Refusing to prioritize elements. "Everything is critical." Push back — if everything is critical, the appetite is too small for the concept, and something needs to be reshaped.
