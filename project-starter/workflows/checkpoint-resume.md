# Checkpoint Resume

For tracked work, `AGENTS.md` defines the canonical storage and creation policy.
Each task's records live under:

```text
changes/YYYY-MM-DD-task-slug/
```

Copy the applicable numbered files from `templates/change/` into that task
folder; never edit the templates in place. Create `changes/INDEX.md` when the
first tracked task is created, then keep its task row current. The selected
task folder is the source of truth for detailed progress. Do not reconstruct
task state from memory.

## Progress Fields

`05-progress.md` should record at least:

```yaml
status: not_started | in_progress | blocked | complete
current_phase: requirements | design | plan | execution | verification | review | archive
current_step: short human-readable step
last_updated: YYYY-MM-DD HH:mm
next_action: exact next action
changed_files: []
subagent_status: none | active | returned | reviewed
blockers: []
verification_state: not_run | partial | passing | failing
```

## Resume Procedure

1. Read `changes/INDEX.md` before selecting a task folder.
2. Identify the requested or latest relevant `changes/YYYY-MM-DD-task-slug/` folder from the index.
3. Read `05-progress.md` and `04-tasks.md`.
4. Read `03-plan.md` when it exists, plus only the phase documents needed for the current step.
5. Check the current worktree and changed files against the recorded boundary.
6. Continue from the next incomplete task or recorded `next_action`.
7. Update `04-tasks.md` and `05-progress.md` after every meaningful checkpoint.
8. Run and record current verification before making any completion claim.

## Stop Conditions

Stop and request the missing decision or context when:

- `status` is `blocked` and the blocker still exists.
- The next action or relevant change folder is ambiguous.
- Required files, approvals, or dependencies are missing.
- The actual worktree conflicts with the recorded file boundary.
- Verification repeatedly fails or reveals a scope change.

When scope changes, update the applicable requirements, design, plan, and task
records before continuing. Do not silently skip or rewrite failed steps.
