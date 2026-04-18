# Transcript — New Product

An abridged sample run showing tone, checkpoints, and handoffs.

## Explore

**User:** I keep hearing from local contractors that good leads fall through the cracks. I think there might be a product there, but I don't know what the actual wedge is yet.

**Assistant:** Tell me the rough version. What do you think is going wrong, and who do you think it's happening to?

**User:** Small plumbing and HVAC shops. The owner gets leads from text, email, voicemail, web forms, sometimes Instagram. They respond late, lose context, or forget to follow up.

**Assistant:** Describe one real person, not the segment. What's their day like when this goes wrong?

**User:** A plumber who still runs jobs himself. He's driving, taking calls, texting customers, and quoting work between appointments.

**Assistant:** What are all the problems around that lead flow, not just the first product idea that comes to mind?

**User:** Missed callbacks, forgetting to follow up on estimates, losing the thread between spouse/office manager and owner, and not knowing which inquiries are still active.

**Assistant:** How are they handling this today?

**User:** Mostly iMessage, Gmail, a notes app, and memory. Some try Jobber or Housecall Pro, but those kick in after the job is booked.

### Checkpoint

**Assistant:** Here's what we've mapped so far:

- **The idea**: help small home-service operators stop losing inbound leads
- **The people**: owner-operators juggling field work and intake themselves
- **The problem space**: missed responses, broken follow-up, scattered context, no active pipeline view
- **Interesting branches**: solo owner-operators vs office-managed shops, pre-booking lead capture vs post-quote follow-up
- **Existing landscape**: personal inboxes plus job-management tools that start too late
- **Candidate wedges**: unified lead inbox, quote follow-up reminders, missed-call responder

Does that capture it?

**User:** Yes. The unified inbox feels strongest, but I still don't know if they'd trust it enough to connect their channels.

## Evidence

**Assistant:** Good. That's no longer an Explore problem. That's an Evidence problem. What decision are we trying to unlock?

**User:** Whether this wedge is real enough to frame and build a first version around.

**Assistant:** What's the riskiest assumption?

**User:** That owner-operators feel enough pain to connect their real communications instead of just saying "yeah, that's annoying."

**Assistant:** What's the lightest credible test?

**User:** Six interviews with operators who personally handle intake, plus a concierge mockup where I manually unify one day's messages for two of them.

**Assistant:** What result would strengthen the case?

**User:** If at least four tell a specific missed-lead story from the last month, and two are willing to try the concierge version using real messages.

**User:** That's exactly what happened. The two concierge tests were messy, but both owners said the unified thread plus follow-up queue would save them.

**Assistant:** Then we have enough signal to frame one wedge.

## Frame

**Assistant:** Which wedge are we framing?

**User:** A unified inbound lead inbox for owner-operators with fewer than ten employees.

**Assistant:** Tell me the concrete pain story.

**User:** A plumber replied to an estimate request by text, then got the photo attachments by email, then forgot to follow up after the customer replied two days later because the thread was split across apps.

**Assistant:** How are they dealing with it today?

**User:** Personal phone, personal inbox, flagging messages, and memory.

**Assistant:** Why now?

**User:** More leads now start in text and DMs, response expectations are faster, and lightweight AI/automation makes a tiny team product feasible.

**Assistant:** What's the appetite?

**User:** One week. I want a sharp first bet, not a CRM.

## Shape

**Assistant:** Walk me through the minimum useful experience.

**User:** New leads land in one inbox. Clicking a lead shows the combined timeline and the latest follow-up state. I can snooze a lead until tomorrow morning and see an overdue queue.

**Assistant:** What's out?

**User:** No quoting, no dispatching, no automations beyond manual snooze, no social DMs in v1.

### Checkpoint

**Assistant:** Concept so far:

- **Core flow**: review new lead, read unified context, mark next follow-up, return to queue
- **Elements**: inbox, lead timeline, follow-up queue
- **In scope**: email forwarding + SMS capture, manual follow-up state
- **Out of scope**: CRM, quoting, dispatch, Instagram

Does that hold?

**User:** Yes.

## De-risk

**Assistant:** Where could a week disappear?

**User:** Full two-way sync and duplicate merging.

**Assistant:** Patch them.

**User:** Email forwarding plus one captured SMS line, not full multi-channel sync. Duplicate merge is manual in v1.

**Assistant:** What gets cut first if time runs short?

**User:** Overdue queue styling first, then manual merge, then inbox filters.

## Pitch

**Assistant:** I pulled the bet into one pitch. Read this as if you were the builder starting tomorrow: do you know the problem, the constraints, and the first cut order?

**User:** Yes. This feels like a real small bet instead of "let's build a CRM."
