---
status: complete
phase: pitch
created: 2026-04-17
updated: 2026-04-17
appetite: 1 week
---

# Pitch: Lead Thread

## Problem

Small home-service owner-operators lose real revenue before jobs are ever booked because inbound customer context is scattered across email and SMS, and there is no lightweight queue showing who needs a response next. One plumber in the interviews replied by text, received photos by email, and then forgot the customer entirely when the next response arrived two days later.

This matters because these operators do not need a full CRM to solve the immediate pain. They need the pre-booking thread to stop breaking.

## Appetite

**1 week** — enough time to build a sharp wedge that proves the problem is worth solving, but not enough time to accidentally create a contractor CRM.

## Solution

Lead Thread is a lightweight pre-booking inbox for owner-operators. It combines email and SMS into one lead timeline and gives each lead a manual follow-up state.

### Elements

#### Lead Inbox

A list of active leads showing latest touchpoint, latest activity time, and follow-up state.

#### Lead Timeline

A combined chronological thread of forwarded emails, captured SMS messages, and simple notes.

#### Follow-Up Queue

Manual states for `new`, `waiting`, `follow up today`, and `overdue`, with a simple snooze action.

### Flow

The operator opens the inbox, reviews a lead, reads the combined context, sets the next follow-up state, and returns to the queue. No quoting, dispatching, or job records are involved.

## Rabbit Holes

- **Channel sprawl**: We only support email and one SMS path in v1.
- **CRM drift**: We do not add pipeline stages, customer records, or quoting.
- **Automation creep**: Follow-up is manual; no sequence builder or auto-reminders beyond manual snooze.

## No-Gos

- Social DMs: out because they expand integration and identity complexity too early
- Voicemail ingestion: out because the wedge is already proven with email + SMS
- Team assignment and permissions: out because the first wedge is for the operator who still owns intake personally

---

## Kickoff Context

### Where to Start

Build the inbox and lead timeline around one constrained ingestion path first, then add follow-up state on top.

### Scope Hammer (Cut Order)

If time runs short, cut in this order (bottom up):

1. **Must ship**: inbox, combined thread, manual follow-up state
2. **Should ship**: overdue highlighting
3. **Nice to have**: filters and merge helpers

### Open Questions for Builders

- Should the inbox surface overdue state inline, or is a separate queue enough?
- What is the least-complex SMS ingestion option that users will still trust?

## Open Questions

- Is the initial wedge better for strictly solo operators, or for operator + helper teams?
- How much duplicate handling is necessary to keep the thread believable?
- Does the product need a separate `new` queue, or is one list with state enough?

## Next Best Question

Which single ingestion path should the builder choose first so the thread feels real quickly without opening broad integration scope?
