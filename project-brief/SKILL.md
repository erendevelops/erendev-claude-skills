---
name: project-brief
description: Use when the user wants a formal project requirements document (PRD) written for an app, feature, or product idea. Use when they say "write a PRD", "create a project brief", "document my idea", or "let's write up the requirements" — including as the final step after an idea-interrogator and/or visual-identity session.
---

# Project Brief

## Overview
Produces a PRD-style document. Standalone-capable: reuses
`idea-interrogator-verdict.md` and `visual-identity.md` from the current
working directory when present instead of re-asking that ground, and asks
the relevant questions directly when either file is missing. Never requires
either file to run.

## Process

1. Check the current working directory for `idea-interrogator-verdict.md`
   and `visual-identity.md`.
2. For whichever file IS present, read it and reuse its content instead of
   asking the user to repeat themselves.
3. For whichever file is MISSING, ask the user directly:
   - No `idea-interrogator-verdict.md`: ask about scope, doability, time
     estimate, purpose, and MVP features before drafting the Validation
     Summary section.
   - No `visual-identity.md`: ask about fonts, colors, theme, and desired
     feeling before drafting the Design Direction section.
4. Ask about anything the PRD still needs that neither file covers: target
   users, success metrics, explicit out-of-scope items.
5. Draft the full document (structure below) and confirm it with the user
   before treating it as final.

The Validation Summary and Design Direction sections below are REQUIRED in
every output document — never drop them, and never fold their content into
other sections instead. If a source file is missing, fill the section from
direct questions rather than omitting it.

## Deliverable
Write `<project-name>-brief.md` to the current working directory:

```markdown
# Project Brief: <project name>

## Overview
<what this is, in 2-4 sentences>

## Validation Summary
<pulled from idea-interrogator-verdict.md if present: verdict, key risk,
scope/time caveats — otherwise drafted from direct questions>

## Goals
- ...

## Target Users
- ...

## Design Direction
<pulled from visual-identity.md if present: condensed narrative + key tokens
(fonts, primary colors, theme) — otherwise drafted from direct questions>

## Features
### MVP
- ...
### Later / Explicitly Deferred
- ...

## Success Metrics
- ...

## Out of Scope
- ...
```

Keep tone practical — no marketing language, no filler adjectives.

## Common Mistakes
- Re-asking questions already answered in `idea-interrogator-verdict.md` or
  `visual-identity.md` — check for and read those files first.
- Dropping the Validation Summary or Design Direction sections, or folding
  their content into other sections instead of keeping them as their own
  labeled headers — both are required sections in every output document.
- Ignoring `visual-identity.md` even when present in cwd — every color/font/
  token detail it contains belongs in the Design Direction section.
- Treating a NO-GO verdict from `idea-interrogator-verdict.md` as a reason to
  refuse writing the brief — it's context for the Validation Summary, not a
  gate.
