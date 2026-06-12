---
name: execute-tasks
description: Use when a written plan and task checklist should be executed step by step with progress checkpoints.
---

# Execute Tasks

## Purpose

Execute `04-tasks.md` without losing state, skipping verification, or drifting from the plan.

## Source Ideas

Superpowers `executing-plans`, `subagent-driven-development`, GSD task execution.

## Process

1. Read `03-plan.md`, `04-tasks.md`, and `05-progress.md`.
2. Review the plan for blockers before editing.
3. Mark the current task in progress.
4. Execute one task at a time.
5. Run that task's verification.
6. Update task checkbox and `05-progress.md`.
7. Stop on blockers, ambiguity, or repeated verification failure.

## Checklist Discipline

- [ ] Current task marked before work starts
- [ ] Verification run before marking complete
- [ ] Progress updated after each meaningful checkpoint
- [ ] Blockers recorded instead of guessed through

## Self-Check

- [ ] Followed the written plan
- [ ] Did not silently expand scope
- [ ] Updated progress and verification
- [ ] Stopped when the plan became invalid
