# Transcript — AI Workflow

An abridged sample run showing how an AI idea gets grounded before it earns appetite.

## Explore

**User:** I think there should be an AI agent that turns customer escalation chaos into a clean engineering brief.

**Assistant:** That's a solution shape. Back up. Who is drowning in what kind of chaos, and when does it hurt?

**User:** Customer success managers and support leads after a big escalation call. They leave Zoom with notes in three places, a support thread, and no clean handoff to engineering.

**Assistant:** What are all the problems in that territory?

**User:** Slow handoff, incomplete context, inconsistent priority signals, duplicate questions from engineering, and huge variance in write-up quality.

**Assistant:** What are the candidate wedges?

**User:** Meeting summarization, handoff-brief drafting, escalation-priority recommendation, and follow-up email drafting.

**Assistant:** Which one feels sharpest?

**User:** Handoff-brief drafting. It's painful, frequent, and already has a recognizable artifact.

## Evidence

**Assistant:** Good. What decision are we trying to unlock?

**User:** Whether "AI draft for escalation handoff brief" is grounded enough to frame.

**Assistant:** What's the riskiest assumption?

**User:** That the pain is real enough that people will trust and adopt a draft brief, not just say it's neat.

**Assistant:** What's the lightest credible test?

**User:** Five interviews with CSMs/support leads plus a concierge workflow where I manually assemble one AI-assisted draft from a transcript and ticket thread.

**User:** The strongest signal was that people didn't want auto-send. They wanted a draft they could edit in a familiar format.

**Assistant:** That's valuable. It gives us a wedge and a boundary.

## Frame

**Assistant:** State the exact problem.

**User:** After an escalation call, the owner spends 30-45 minutes writing the engineering handoff brief because context is scattered across transcript, support ticket, and call notes.

**Assistant:** Appetite?

**User:** One week. We only need the first useful draft-and-review workflow.

## Shape

**Assistant:** Walk me through the minimum useful path.

**User:** Upload or select transcript + ticket thread, generate a draft brief with fixed sections, let the human edit it, then copy or push it into the existing engineering handoff doc/ticket.

**Assistant:** What's out?

**User:** No autonomous prioritization, no reply drafting, no multi-step agent chains, no direct auto-send to engineering.

## De-risk

**Assistant:** Biggest rabbit hole?

**User:** Trying to infer too much from weak source material and over-trusting the model.

**Assistant:** Patch?

**User:** Require human review, fixed sections, explicit source links, and only support one escalation format in v1.

## Pitch

**Assistant:** Does this still read like "draft the handoff brief faster," not "install an AI teammate everywhere"?

**User:** Yes. That boundary is doing a lot of work.
