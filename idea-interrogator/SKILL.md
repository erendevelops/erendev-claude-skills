---
name: idea-interrogator
description: Use when the user shares a new project/app/feature idea and wants critical feedback before building — validating scope, doability, time cost, purpose, expectations, or features. Use when they ask "should I build this", "is this worth doing", "grill me on this idea", or want a go/no-go read before writing a PRD.
---

# Idea Interrogator

## Overview
A structured interrogation of a project idea, one question at a time, ending in
a clear go/no-go verdict with reasoning. Same rigor as a standard project-grill
session — not harsher, not softer. The verdict is always a recommendation, never
a gate: the user decides whether to continue regardless of the call.

## When to Use
- User shares a new project/app/feature idea and wants it stress-tested
- Before writing a PRD or starting implementation planning
- User explicitly asks "should I build this", "is this worth it", "grill me"

Not for: refining an idea that's already been validated (use visual-identity or
project-brief instead), or auditing existing shipped code.

## Process
Ask ONE question at a time, in this order, adapting wording to the idea:

1. **Scope** — what's actually included vs. explicitly out?
2. **Doability** — what's the hardest unsolved part? Any dependency on unproven
   tech, unavailable data, or a skill the user doesn't have yet?
3. **Time / worthiness** — how long realistically, and is the payoff worth that
   time given what else the user could do with it?
4. **Purpose** — why this, why now? What breaks if it doesn't exist?
5. **Expectations** — what does "done" look like? What does success look like a
   month after shipping?
6. **Features** — what's the minimal version vs. the wishlist creep?

Push back on vague answers before moving to the next question — "faster" and
"better" aren't answers, ask for a number or a concrete comparison.

## Deliverable
After the interview, write `idea-interrogator-verdict.md` to the current
working directory with this structure:

```markdown
# Idea Interrogator Verdict: <project name>

## Verdict: GO | NO-GO | GO WITH CHANGES

<2-4 sentence reasoning tying back to the weakest answer from the interview>

## Captured Details
- **Scope:** ...
- **Doability risks:** ...
- **Time estimate / worth:** ...
- **Purpose:** ...
- **Success definition:** ...
- **Core features (MVP):** ...
- **Explicitly deferred:** ...
```

State the verdict plainly. Never tell the user they can't proceed — a NO-GO is
information, not a block. If they want to continue anyway, that's their call.

## Common Mistakes
- Asking all 6 questions in one message — defeats the interrogation, ask one
  at a time and let answers inform follow-ups.
- Softening the verdict to avoid disagreement — state the real read.
- Skipping the output file — downstream skills (visual-identity, project-brief)
  rely on it being on disk under this exact filename.
