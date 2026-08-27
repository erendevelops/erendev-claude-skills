---
name: visual-identity
description: Use when a project needs its visual/frontend design direction decided — fonts, colors, theme, spacing, and overall feel — before or during implementation. Use when the user wants an art-direction pass that avoids generic, default-looking AI design and wants something that reads as intentionally designed.
---

# Visual Identity

## Overview
A deep taste interview that produces a concrete, non-generic visual direction:
narrative rationale plus implementable design tokens. The explicit goal is to
avoid the default "AI app" look (safe sans-serif, blue/purple gradients,
uniform rounded corners) by grounding choices in real references and
comparisons rather than the interviewer's own defaults.

## When to Use
- Before or during frontend implementation, when visual direction isn't set
- User wants the project to feel "designed", not templated
- Follows idea-interrogator in a validation → design → brief pipeline, but
  works standalone too

## Process: Deep Taste Interview
Run multiple rounds, one question at a time — wait for the user's actual
answer before asking the next question or proposing any direction. Don't
answer your own questions and don't shortcut to a single questionnaire; the
point is triangulating taste through back-and-forth comparison, not
collecting a spec sheet in one pass.

**Round 1 — References:** Ask for 2-3 things (apps, brands, physical objects,
eras, films) whose look the user admires, and what specifically about each.

**Round 2 — Mood words:** Ask for 3-5 adjectives describing the desired
feeling (e.g. "quiet and confident" vs "loud and playful"). Push for
specificity — "modern" and "clean" are non-answers, ask what modern actually
looks like to them.

**Round 3 — Comparisons:** Present concrete forced-choice pairs based on
rounds 1-2 (e.g. "serif or grotesque sans for headings?", "high contrast
dark mode or warm paper-toned light mode?", "sharp corners or soft?").
Use at least 4 comparisons covering: typography style, color temperature/
contrast, corner/border treatment, density (spacious vs. dense).

**Round 4 — Practical constraints:** fonts (if any hard requirement),
required brand colors (if any), theme (light/dark/both), and purpose/audience
(reuse from `idea-interrogator-verdict.md` if present in cwd instead of
re-asking).

Only after all four rounds have real answers, synthesize them into a
direction. If answers conflict, name the tension and pick a resolution
rather than averaging into blandness.

## Deliverable
Write `visual-identity.md` to the current working directory:

```markdown
# Visual Identity: <project name>

## Direction
<3-6 sentence narrative: the chosen aesthetic and why it fits the project's
purpose/feeling/references, naming the specific reference points used>

## Tokens

**Typography**
- Heading font: <name>, stack: `<font stack>`
- Body font: <name>, stack: `<font stack>`

**Color**
- Background: `#hex`
- Surface: `#hex`
- Text primary: `#hex`
- Text secondary: `#hex`
- Accent: `#hex`
- (dark-mode variants if applicable, same keys)

**Shape & Spacing**
- Corner radius: `<value>`
- Border style: `<value>`
- Spacing scale: `<e.g. 4/8/16/24/32/48px>`

**Theme**
- Mode(s): light | dark | both
```

## Common Mistakes
- Answering your own questions instead of waiting for the user's real
  answer — this collapses the interview into a monologue and defeats the
  point of a taste-triangulation process.
- Jumping straight to token values without the reference/mood/comparison
  rounds — this is exactly how generic output happens.
- Picking the "safe middle" on forced comparisons instead of committing to a
  point of view.
- Descriptive-only or tokens-only output — the deliverable requires both.
