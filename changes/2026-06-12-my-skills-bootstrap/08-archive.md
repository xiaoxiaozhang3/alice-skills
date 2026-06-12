# Archive

## Outcome

Created `/Users/mac/Documents/obsidian/my-skills` as a personal Agent Skill source repository.

## What Worked

- Combining standard `skills/<name>/SKILL.md` with OpenSpec-style `changes/` gives both reusable capability and resumable task history.
- Keeping schema-first API as a planning rule avoids creating an unnecessary extra skill.
- A small engineering lifecycle set is easier to maintain than a full copy of 151 upstream skills.

## What To Improve Next

- Add `references/` only for skills that prove too dense after real use.
- Add scripts only for deterministic repeated checks.
- Pressure-test `use-engineering-skills`, `plan-implementation`, and `resume-change` first.

## Reusable Lessons

- Put universal process constraints in `AGENTS.md`, `workflows/`, and templates.
- Put task-specific execution state in `changes/`.
- Put reusable behavior guidance in `skills/`.

## Skill Improvements To Consider

- Add a tiny `scripts/check-my-skills` validator later if manual checks become repetitive.
- Add trigger examples per skill after first real usage.
