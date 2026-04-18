# Transcript — Internal Tool

An abridged sample run showing a direct path when the problem is already concrete.

## Frame

**User:** Our finance ops team keeps asking for a dashboard for billing import failures.

**Assistant:** What's actually broken today? Give me a real recent story, not the requested dashboard.

**User:** Nightly billing imports create 10-30 exceptions. They get dumped in a Slack channel. Whoever notices first tries to fix them, but ownership is unclear and the same issue gets investigated twice.

**Assistant:** Who is affected?

**User:** Three finance ops analysts and one engineering-on-call person when the issue looks like a system bug.

**Assistant:** What's the workaround?

**User:** Slack, screenshots, a spreadsheet when things are especially bad, and checking the admin panel by hand.

**Assistant:** Appetite?

**User:** Three days. We need something operational, not polished.

## Shape

**Assistant:** Walk me through the minimum useful flow.

**User:** Analyst opens the queue, sees new exceptions, claims one, opens details, adds a resolution note, and marks it resolved or escalates it.

**Assistant:** What's out?

**User:** No analytics, no custom filters, no workflow automation, no bulk actions.

## De-risk

**Assistant:** Where could three days disappear?

**User:** Building a flexible workflow system, permissions, and trying to sync comment threads back to Slack.

**Assistant:** Patch them.

**User:** Fixed statuses only, existing employee auth only, and Slack links out instead of comment sync.

## Pitch

**Assistant:** Read this like the analyst using it Monday morning. Is the first job clear?

**User:** Yes. Open queue, claim exception, resolve or escalate. That's enough.
