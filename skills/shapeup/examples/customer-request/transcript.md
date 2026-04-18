# Transcript — Customer Request

An abridged sample run showing how a feature request gets reframed.

## Frame

**User:** Customers keep asking for "copy permissions from another user." I think we should just build that.

**Assistant:** That sounds like a solution. What's the problem it solves? Tell me a real story.

**User:** An admin at a hospital network onboarded six regional managers last month. She had to recreate the same access package six times by clicking through multiple screens.

**Assistant:** How does she do it today?

**User:** She opens an existing manager in one tab, compares permissions manually, then repeats the setup on the new user.

**Assistant:** Appetite?

**User:** Two to three days. This should be sharp.

## Shape

**Assistant:** What's the minimum useful flow?

**User:** While editing a user, choose an existing user as the source, copy role and scope settings into the draft, review differences, then save.

**Assistant:** What's out?

**User:** No template library, no bulk onboarding, no full permission diff explorer.

## De-risk

**Assistant:** What could blow this up?

**User:** Hidden permissions that shouldn't copy, cross-tenant scope issues, and trying to make every permission type cloneable on day one.

**Assistant:** Patch them.

**User:** Only copy supported permission categories, require review before save, and keep the action inside the existing tenant boundary.

## Pitch

**Assistant:** Does this still feel like "copy one user's access profile during onboarding," not "redesign permissions management"?

**User:** Yes. That's exactly the boundary we need.
