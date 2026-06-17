# Subagent Dispatch

Use subagents only when they reduce risk or elapsed time. The main agent still owns scope, edits, verification, and the final answer.

## Dispatch Gate

Dispatch subagents only after the main agent has read the relevant skill or workflow, inspected the needed files, and identified independent work.

Dispatch when at least one condition is true:

1. A selected skill explicitly requires subagents.
2. A written plan has two or more independent tasks with separate file boundaries.
3. Multiple failures live in different test files, subsystems, or workflows.
4. A complex bug needs an independent reproduction test before the main fix.
5. A design task needs parallel alternatives.
6. A non-trivial implementation needs fresh review against the spec.

Do not dispatch when:

- The task is trivial or a one-file edit.
- Requirements are unclear.
- Subagents would edit the same files at the same time.
- The task needs one coherent end-to-end judgment.
- The only reason is "maybe faster".

## Dispatch Brief

Use `templates/subagent-brief-template.md` for each subagent. Keep the brief narrow and self-contained.

Each brief must name:

- Goal
- Allowed files
- Forbidden files
- Context to read
- Expected output
- Verification or evidence
- Stop condition

## Status Handling

Subagents report one status:

| Status | Meaning | Main agent response |
|---|---|---|
| `DONE` | Work completed with evidence | Review output, check conflicts, run the smallest useful verification |
| `DONE_WITH_CONCERNS` | Work completed but has doubts or risks | Read concerns before accepting; fix or record residual risk |
| `NEEDS_CONTEXT` | Missing required information | Provide only the missing context, then redispatch |
| `BLOCKED` | Cannot complete with current scope | Change scope, choose a stronger approach, split the task, or ask the user |

Do not mark a task complete from a subagent report alone. Completion requires main-agent verification.

## File Handoff

Prefer files over pasted context for large handoffs.

- Briefs live in the relevant `changes/YYYY-MM-DD-task-slug/` folder when the task is tracked.
- Reports should be written beside the brief, named after the task or subagent.
- Diff or review packages should be files when they are too large to summarize safely.
- The subagent returns only status, touched files, verification summary, and concerns.

This keeps the main context small and makes resume checkpoints auditable.

## Integration

After subagents return:

1. Check whether outputs conflict.
2. Apply or review changes in the main workspace.
3. Run the smallest verification that proves the combined result.
4. Record subagent status and verification in `05-progress.md` and `06-verification.md` for tracked tasks.
