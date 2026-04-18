---
status: Complete
phase: Shape
created: 2026-04-17
updated: 2026-04-17
---

# Shaping: Lead Thread

## Concept Summary

A lightweight pre-booking lead inbox that combines email and SMS into one lead timeline and pairs it with a simple follow-up queue.

## Elements

### Lead Inbox

A list of active leads showing name, latest message source, latest activity time, and follow-up state.

### Lead Timeline

A combined thread view showing forwarded emails, captured SMS messages, and simple notes in chronological order.

### Follow-Up Queue

A lightweight state marker for `new`, `waiting`, `follow up today`, and `overdue`, with manual snooze to tomorrow or later this week.

## Flow

The operator lands in the inbox, opens a lead, reads the combined thread, then updates the follow-up state before returning to the queue. The product is not trying to book jobs, write quotes, or manage crews.

## Boundaries

### In Scope
- Email forwarding ingestion
- One SMS capture path
- Combined thread view
- Manual follow-up states and snooze

### Out of Scope
- Full CRM records
- Quoting or dispatching
- Social DMs and voicemail ingestion
- Automated follow-up sequences

## Open Questions
- Is one inbox list enough, or does the concept need separate views for `new` and `overdue`?
- How much duplicate merging can be deferred without making the concept feel broken?
- Does the first SMS capture path require a dedicated number, or can it start with forwarding/copying?

## Next Best Question
Which technical and scope risks could quietly turn this one-week wedge into an accidental multi-channel CRM build?

---

## Conversation Log

The concept got simpler as the conversation progressed. A separate pipeline board, quote reminders, and team assignment were all cut. The shaped solution stayed close to the framed story: one thread and one queue.
