# Engineering Lifecycle

Use the lightest route defined in `AGENTS.md` that still protects correctness.
If scope grows, preserve completed work, reclassify the task, and update its
tracking before continuing.

## Simple Task

A task is simple only when the goal and expected result are clear, the change
is isolated and low risk, no architecture or product decision is required, it
changes no API contract, database schema, authentication, permission, or
production behavior, and it can be completed and verified in one session.

```text
inspect -> minimal change -> minimal verification -> report
```

Do not create change-tracking files or dispatch Subagents.

## Small Task

A task is small when it affects a limited number of related files, has clear
expected behavior and verification, and requires no architectural trade-off.

```text
define boundary -> inspect callers and tests -> implement -> verify -> report
```

Create lightweight tracking only when resumability is useful:

- `00-change.md`
- `04-tasks.md`
- `05-progress.md`
- `06-verification.md`

## Complex Task

A task is complex when it introduces a feature or module, crosses system
boundaries, changes an API or database schema, affects authentication,
authorization, sensitive data, deployment, or production behavior, requires a
meaningful trade-off, or may span multiple phases or sessions.

Use the complete templates under `templates/change/`:

```text
change -> requirements -> design -> plan -> tasks -> implementation
-> progress -> verification -> review -> archive
```

Approve requirements and design before implementation. Record ordered tasks,
dependencies, file boundaries, expected outputs, verification, and stop
conditions before dispatch or coding begins.

## Schema-First API Rule

For frontend-backend data exchange, define the contract before implementation:

1. Domain model or data schema
2. Request fields and validation
3. Response, error, pagination, nullable, and enum shapes
4. Authorization and compatibility behavior
5. Shared or aligned frontend and backend types
6. Backend handler and service logic
7. Frontend client and interface integration
8. Contract fixture or test proving alignment

Do not let production logic depend on undocumented mock-only fields.

## Related Workflows

- Existing codebase changes: `brownfield-guardrails.md`
- Interrupted tracked work: `checkpoint-resume.md`
- Eligible independent plan tasks: `subagent-dispatch.md`
- Evidence and completion claims: `completion-gates.md`
