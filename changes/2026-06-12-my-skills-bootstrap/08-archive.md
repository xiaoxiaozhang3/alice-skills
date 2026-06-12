# Archive

## Outcome

`alice-skills/skills` was corrected to contain mature upstream skills copied directly from existing local skill collections, rather than custom aggregate rewrites.

## Current Included Count

- 28 copied `SKILL.md` files

## What Changed After Review

- Removed the custom aggregate skill folders from `alice-skills/skills`.
- Removed the misunderstood `vendor` source-copy approach from `alice-skills`.
- Copied mature executable skills directly into `alice-skills/skills`, including `to-prd`, `to-issues`, `tdd`, `diagnose`, and related engineering workflow skills.
- Updated README and skill index to describe the actual copied-skill model.

## Lesson

When the user asks to build a personal skill directory from existing skills, prefer copying mature source skills directly first. Add custom workflow/rules outside `skills/` unless explicitly asked to create new skills.
