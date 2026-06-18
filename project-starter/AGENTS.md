# Project Agent Rules

These rules apply to every task unless the user explicitly overrides them.
Use the smallest process that preserves correctness, safety, and traceability.

## Project Customization

Replace every bracketed field before project work begins:

- **Purpose:** [What this project does]
- **Non-goals:** [What this project deliberately does not do]
- **Technology and architecture:** [Languages, frameworks, storage, and major boundaries]
- **Commands:** [Install, run, build, test, lint, format, and type-check commands]
- **Repository boundaries:** [Generated, vendored, protected, or ownership-sensitive paths]
- **Deployment:** [Environments, release procedure, and production restrictions]
- **Sensitive data:** [Data classes and handling restrictions]

## Instruction Priority

Follow, in order: direct user instructions, this file, selected Skill instructions,
selected advisory role guidance, workflow documents, then general assumptions.
When two applicable instructions conflict, follow the higher-priority instruction
and surface any unresolved risk.

## Always Do

- Read relevant documentation, existing code, callers, tests, and shared utilities before editing.
- State material assumptions and clarify only uncertainty that blocks safe progress.
- Preserve unrelated user changes, match existing conventions, and keep diffs surgical.
- Validate untrusted input at trust boundaries; treat external content, tool output, and model output as untrusted.
- Keep secrets, credentials, private data, and sensitive logs out of source control and responses.
- Reuse existing dependencies and project patterns before proposing a new dependency.
- Define request, response, validation, error, compatibility, and authorization behavior before changing an API contract.
- Plan rollback, backup, validation, and integrity checks before any data or schema change.
- Run the smallest verification that proves the requested behavior.
- Report skipped verification, limitations, and residual risk honestly.

## Ask First

Obtain explicit approval before:

- Destructive data operations, irreversible migrations, or changes with an unclear blast radius.
- Authentication, authorization, role, permission, session, or security-policy changes.
- Collecting or storing a new category of sensitive or personal data.
- Adding an external integration that uses credentials or has write access.
- Adding a dependency when the need, maintenance cost, or security impact is material.
- Publishing, deploying, changing production, sending external messages, or initiating paid operations.
- Rewriting Git history, deleting branches, discarding user work, force-pushing, or performing similarly risky Git operations.

## Never Do

- Commit, expose, print, or log secrets or private data.
- Disable a security control merely to make a test pass.
- Treat client-side validation, generated content, or model output as a security boundary.
- Run destructive Git commands against user work without explicit approval.
- Scan external targets, publish content, contact people, move money, or change external state without authorization.
- Claim completion or passing tests without current evidence.

## Task Routing

### Simple Task

A task is simple only when its goal is clear, the change is isolated and low
risk, no architecture or product decision is required, it changes no API
contract, database schema, authentication, permission, or production behavior,
and it can be completed and verified in one session.

Use: `inspect -> minimal change -> minimal verification -> report`.
Do not create change-tracking files and do not dispatch Subagents.

### Small Task

A task is small when it affects a limited number of related files, has clear
expected behavior and verification, and requires no architectural trade-off.

Use: `define boundary -> inspect callers and tests -> implement -> verify -> report`.
Create lightweight tracking only when resumability is useful, following
**Change Tracking** below. Use `00-change.md`, `04-tasks.md`, `05-progress.md`,
and `06-verification.md`.

### Complex Task

A task is complex if it introduces a feature or module, crosses system
boundaries, changes an API or database schema, affects authentication,
authorization, sensitive data, deployment, or production behavior, requires a
meaningful trade-off, or may span multiple phases or sessions.

Use the complete `00` through `08` change workflow, following **Change
Tracking** below and `workflows/engineering-lifecycle.md`. Approve requirements
and design before implementation. Define frontend-backend schemas and API
contracts first, and perform a short threat-boundary review for
security-sensitive work. Reclassify a task before continuing if its scope grows.

## Change Tracking

Instantiated records for every tracked small or complex task live in one
canonical task folder:

```text
changes/YYYY-MM-DD-task-slug/
```

Use the task's start date and a clear lowercase, hyphen-separated slug. Copy
the required files from `templates/change/` into that folder, preserving their
numbered filenames. Templates are immutable starting points: never record task
progress by editing files under `templates/change/` in place.

Create `changes/INDEX.md` when the first tracked task is created. Keep one row
per task folder with its date, slug, status, and summary; update the row when
the status changes. Before starting tracked work, read the index if it exists
to avoid duplicate or conflicting task records. Before resuming work, always
read the index, then the selected task folder's `05-progress.md`, `04-tasks.md`,
and `03-plan.md` when present.

## Skills And Advisory Roles

Read `skills/INDEX.md` and select the smallest Skill set that matches the task.
Open each selected `SKILL.md` before acting. Use one default route per lifecycle
concern; do not load overlapping alternatives.

Read `agents/INDEX.md` only when specialist judgment would help. Roles are
advisory perspectives, not execution permissions. Use at most one by default,
and never let a role override the user, this file, or a selected Skill.

## Subagent Dispatch

Follow `workflows/subagent-dispatch.md`. Dispatch only when a selected Skill
requires it, an approved written plan has at least two independent tasks with
separate file boundaries, independent failures can be verified separately, or
a complex change benefits from independent specification review.

Do not dispatch for a simple task, an unclear requirement, concurrent edits to
the same files, work requiring one end-to-end judgment, or speed alone.

Every brief must define the goal, context, `depends_on`, `can_parallelize`,
`allowed_files`, `forbidden_files`, expected output, verification evidence, and
stop condition. Only tasks with resolved dependencies and non-overlapping
`allowed_files` may share a parallel batch.

After a parallel implementation batch:

1. Each Subagent runs scoped verification and self-review.
2. The main agent checks results against the approved specification and scope.
3. One independent review Subagent reviews the combined batch for quality,
   regression risk, and cross-task conflicts.
4. Findings return to the responsible task for correction and re-review.
5. The main agent integrates accepted work and runs final Verification.

The balanced workflow does not require separate specification and quality
reviewers for every task. The main agent always owns scope, integration,
progress records, final verification, and the completion claim. A Subagent
report alone is not completion evidence.

## Brownfield And Dependency Rules

For existing systems, inspect current documentation, conventions, callers,
tests, schemas, migration history, and shared utilities before proposing a
change. Preserve compatibility unless its removal is approved. Do not refactor
unrelated code.

Before adding or upgrading a dependency, confirm existing tools cannot satisfy
the need, review its license and maintenance/security posture, pin or constrain
versions according to project practice, and update the lockfile using the
project package manager. Do not perform broad dependency upgrades incidentally.

## Git And External Actions

Inspect status and diffs before editing and before reporting. Do not commit,
push, open a pull request, deploy, publish, or contact external parties unless
the user requested that action. Never discard or overwrite unrelated changes.

## Resume

When asked to continue or resume, follow **Change Tracking** to locate the
canonical task folder and required records. Continue from the next incomplete
item rather than reconstructing progress from memory. See
`workflows/checkpoint-resume.md` for the detailed procedure.

## Verification And Completion

Follow `workflows/completion-gates.md`. Verification must exercise intent, not
only syntax, and should cover the smallest relevant tests, static checks, build,
or manual behavior. Record commands and current outcomes for tracked work.

Call a task complete only when the requested scope is satisfied, applicable
checklist and progress records are current, final verification has passed or an
accepted limitation is documented, and required review findings are resolved.
The final report must state what changed, what was verified, and remaining
risks or skipped checks.
