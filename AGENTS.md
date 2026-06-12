# Alice Skills Agent Rules

This directory is a personal Agent Skill source repository.

## Current Policy

1. `skills/` should contain mature executable skill folders copied from existing source skill collections when they fit the user's workflow.
2. Do not create hand-written aggregate/rewrite skills unless the user explicitly asks for a new custom skill.
3. Workflow rules, checklist rules, change tracking, resume checkpoints, and schema-first API planning belong in `workflows/`, `templates/`, and `changes/`, not as extra skills by default.
4. If a copied skill needs customization, edit the copied skill in place and record the reason in a change folder.
5. Keep all task artifacts under `changes/YYYY-MM-DD-task-slug/`.
6. If a user says continue, resume, or pick up from last time, first read the latest relevant `changes/*/05-progress.md` and `changes/*/04-tasks.md`.
7. Do not claim completion without fresh verification evidence recorded in `06-verification.md`.
8. Before executing any non-trivial coding task, create or update `03-plan.md` and `04-tasks.md` in the relevant change folder. Do not start implementation until the plan lists ordered tasks, expected file boundaries, and verification steps.
9. For frontend-backend data exchange, plan schema and API contract before implementation logic.
10. For brownfield work, inspect existing docs, patterns, callers, tests, and shared utilities before proposing changes.

## How To Use Skills

When a task may match a skill in `skills/`:

1. Read `skills/INDEX.md` first to identify candidate skills.
2. Choose the smallest relevant skill set. Do not load every skill.
3. Open the selected `skills/<skill-name>/SKILL.md` before acting.
4. Follow that skill's instructions as written unless the user's direct instruction or this `AGENTS.md` overrides it.
5. If multiple skills apply, use this order:
   - requirement/spec skills before planning skills
   - planning skills before implementation skills
   - debugging skills before fix attempts
   - verification/review skills before completion claims
6. If a selected skill references setup or prerequisites, satisfy those first or record why they were skipped.
7. If no copied skill fits, use the workflow docs in `workflows/` rather than inventing a new skill.

Common routes:

- PRD from current context -> `skills/to-prd/SKILL.md`
- Break PRD or plan into issues -> `skills/to-issues/SKILL.md`
- Test-first implementation -> `skills/tdd/SKILL.md` or `skills/test-driven-development/SKILL.md`
- Debug failures -> `skills/diagnose/SKILL.md` or `skills/debugging-and-error-recovery/SKILL.md`
- Code review -> `skills/code-review-and-quality/SKILL.md`
- Browser/UI verification -> `skills/browser-testing-with-devtools/SKILL.md`
- Shipping docs or handoff -> `skills/shipping-artifacts/SKILL.md`

## Required Change Files

Each change folder should contain:

- `00-change.md` - scope, source, and constraints
- `01-requirements.md` - requirements and acceptance criteria
- `02-design.md` - design and trade-offs
- `03-plan.md` - ordered implementation plan
- `04-tasks.md` - executable checklist
- `05-progress.md` - resumable status and checkpoint
- `06-verification.md` - verification commands and evidence
- `07-review.md` - review findings and decisions
- `08-archive.md` - lessons and follow-up skill improvements
