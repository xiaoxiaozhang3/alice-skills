# Subagent Dispatch

Use Subagents as scoped execution helpers for eligible planned work. The main
agent always owns requirements, scope, integration, progress records, final
verification, and the completion claim.

## Dispatch Gate

Dispatch only when at least one condition is true:

1. A selected Skill explicitly requires Subagents.
2. An approved written plan contains two or more independent tasks with separate file boundaries.
3. Separate failures or investigations can be verified independently.
4. A complex change benefits from independent review against the approved specification.

Do not dispatch for a simple task, unclear requirements, concurrent edits to
the same files, work requiring one end-to-end judgment, or speed alone.

Requirements and design must be approved before implementation tasks are
batched. The main agent first writes an implementation plan with dependencies,
file boundaries, outputs, verification, and stop conditions.

## Required Task Fields

Every planned Subagent task and dispatch brief must define:

- `goal`
- `context`
- `depends_on`
- `can_parallelize`
- `allowed_files`
- `forbidden_files`
- `expected_output`
- `verification_evidence`
- `stop_condition`
- `report_path`

Use `templates/subagent-brief.md` when available. Briefs must be narrow and
self-contained. Subagents may edit only `allowed_files` and must stop rather
than invent policy when the stop condition is reached.

## Batch Construction

1. Resolve each task's `depends_on` entries.
2. Select only tasks with `can_parallelize: true` and no unresolved dependency.
3. Compare every pair of `allowed_files` boundaries.
4. Put tasks in the same batch only when their write boundaries do not overlap.
5. Run dependent tasks in order and form a later batch after prerequisites pass.
6. Record each dispatch and returned status in the tracked progress files.

No two active implementation Subagents may edit the same file. Shared-file or
integration edits remain with the main agent unless a later, exclusive task has
an explicit boundary.

## Subagent Responsibilities

Each implementation Subagent must:

1. Read the brief and required context.
2. Stay within its file boundary.
3. Perform the requested implementation.
4. Run its scoped verification evidence.
5. Self-review the diff for scope, correctness, and risks.
6. Write the requested report and return only status, touched files, verification, and concerns.

Allowed return statuses are `DONE`, `DONE_WITH_CONCERNS`, `NEEDS_CONTEXT`, and
`BLOCKED`. A returned status is a handoff, not completion evidence.

## Balanced Plan-Driven Review Gates

After an implementation batch returns:

1. **Main-agent specification review:** Compare every result with the approved requirements, design, task scope, expected output, and file boundary. Reject out-of-scope or incomplete work.
2. **Independent batch quality review:** One review Subagent examines the combined accepted batch for correctness, maintainability, regressions, security issues, and cross-task conflicts. This is one review for the batch, not a mandatory reviewer for every task.
3. **Correction loop:** Route each finding to the responsible implementation task. The correcting Subagent reruns scoped verification and self-review; the main agent repeats specification review, and the independent reviewer rechecks affected findings when needed.
4. **Main-agent integration:** Integrate accepted outputs, resolve navigation or shared-boundary changes, and inspect the combined diff.
5. **Main-agent final verification:** Run the combined verification that proves the integrated behavior and record current evidence before any completion claim.

```text
approved design
-> implementation plan
-> tasks with dependencies and file boundaries
-> parallel implementation batch
-> main-agent specification review
-> independent batch quality review
-> correction and re-review loop
-> main-agent integration and final verification
```

Separate specification and quality-review Subagents are not required for every
individual task. The main agent performs the specification gate, while one
independent reviewer covers the combined batch.

## Status Handling

| Status | Main-agent response |
|---|---|
| `DONE` | Review scope and evidence, then admit the result to the batch gates. |
| `DONE_WITH_CONCERNS` | Resolve or explicitly record concerns before acceptance. |
| `NEEDS_CONTEXT` | Supply only the missing context, then redispatch. |
| `BLOCKED` | Re-plan, change scope with approval, split the task, or ask the user. |

Do not mark a task complete from a Subagent report alone. Update progress and
verification records only from reviewed output and current evidence.
