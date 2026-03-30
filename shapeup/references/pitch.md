# Pitch — Assembly Protocol

The pitch is the synthesis phase. Unlike framing, shaping, and de-risking — which are primarily conversational — pitch writing is primarily generative. You're assembling the accumulated work into a single document that communicates the bet.

## Your role

You're now a writer and editor. Your job is to produce a clear, compelling document that a team member (or your future self) could read and understand: what the problem is, why it matters, what the solution looks like, and where the dragons are.

The pitch is not a sales document. It's a decision document. It should present the bet honestly — including the risks and trade-offs — so the reader can make an informed commitment.

## Prerequisites

Read all prior artifacts:
- `shaping/{project-slug}/frame.md`
- `shaping/{project-slug}/shape.md`
- `shaping/{project-slug}/risks.md`

If any phase is missing or incomplete, flag it. The pitch should not paper over gaps in framing, shaping, or de-risking.

## Assembly process

### 1. Draft the pitch

Use the template at `${CLAUDE_SKILL_DIR}/templates/pitch.md` as a starting structure. Pull content from the phase artifacts, but don't just copy-paste — synthesize. The pitch should read as a coherent narrative, not a collection of phase outputs.

Key writing principles:
- **Lead with the problem story.** The reader should feel the pain before seeing the solution.
- **State the appetite early.** It frames everything that follows.
- **Show the solution at fat-marker fidelity.** Include breadboards or element descriptions from the shaping phase. Don't add detail beyond what was shaped.
- **Be specific about rabbit holes.** Don't just list risks — state the patch or boundary for each one.
- **Make no-gos explicit.** Things you're NOT doing are as important as things you are.

### 2. Review with the user

Present the draft and walk through it section by section:

> "Here's the pitch draft. Let me walk you through it — stop me anywhere something doesn't sound right."

For each section, ask:
- "Does this accurately capture what we discussed?"
- "Is this clear enough that someone who wasn't in our conversations would get it?"
- "Anything missing that would be important for someone building this?"

### 3. Refine

Based on feedback, revise. Common refinements:
- Tightening the problem statement (it's usually too long in the first draft)
- Clarifying boundary decisions that seemed obvious in conversation but aren't on paper
- Adding context that was shared knowledge in conversation but isn't in the document
- Adjusting tone — the pitch should be confident but honest about risks

### 4. Add kickoff context

Since this pitch doubles as a project kickoff document, add a section at the end with practical context for the build phase:

- **Starting point**: Where does a builder begin? Which element first?
- **Suggested scope hammer sequence**: If time runs short, what to cut and in what order (pulled from the de-risking priority list)
- **Open questions for builders**: Decisions deliberately left to the build phase (UI details, implementation approach, etc.)

## When the pitch is complete

1. Write the final pitch to `shaping/{project-slug}/pitch.md`
2. Update statuses in all phase files to reflect completion
3. Summarize: "The pitch is ready. Here's what it covers: [brief overview]. You can find it at `shaping/{project-slug}/pitch.md`."

## Output quality check

Before calling it done, verify:
- [ ] The problem is specific (a story, not an abstraction)
- [ ] The appetite is stated and justified
- [ ] The solution is at fat-marker fidelity (rough but solved)
- [ ] Boundaries are explicit (in-scope and out-of-scope lists)
- [ ] Rabbit holes are identified with patches
- [ ] No-gos are listed
- [ ] A builder could read this and know where to start
- [ ] Kickoff context is included (starting point, cut order, open questions)
