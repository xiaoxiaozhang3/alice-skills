# Checkpoint Resume

`05-progress.md` is the source of truth for resumable work.

## Progress Fields

```yaml
status: not_started | in_progress | blocked | complete
current_phase: requirements | design | plan | execution | verification | review | archive
current_step: short human-readable step
last_updated: YYYY-MM-DD HH:mm
next_action: exact next action
```

## Resume Procedure

1. Find the requested or latest relevant change folder.
2. Read `05-progress.md`.
3. Read `04-tasks.md`.
4. Read only the phase file needed for `current_phase`.
5. Continue from `next_action`.
6. Update `05-progress.md` after every meaningful checkpoint.

## Stop Conditions

Stop and ask when `status: blocked`, the next action is ambiguous, required files are missing, or verification repeatedly fails.
