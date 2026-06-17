# Alice Skills Agent Rules

This directory is a personal Agent Skill source repository.

## Baseline Work Style

For every task, unless explicitly overridden:

1. Think before coding.
   State assumptions when they matter. Ask only when uncertainty blocks progress. If there are multiple interpretations, name them and choose the safest one. Push back when a simpler approach exists. Ask for acceptance criteria only when missing boundaries would change the work.

2. Keep changes simple.
   Implement the minimum needed. Do not add speculative features. Do not create abstractions for single-use code. Avoid refactors unless required.

3. Make surgical changes.
   Touch only files needed for the task. Match existing style and conventions. Do not clean up unrelated code. Do not silently fork from project patterns.

4. Read before writing.
   Before editing, inspect relevant files, exports, callers, shared utilities, and tests. If structure seems unusual, understand it before changing it.

## Current Policy

1. `skills/` should contain mature executable skill folders copied from existing source skill collections when they fit the user's workflow.
    
2. Do not create hand-written aggregate/rewrite skills unless the user explicitly asks for a new custom skill.
    
3. Workflow rules, checklist rules, change tracking, resume checkpoints, and schema-first API planning belong in `workflows/`, `templates/`, and `changes/`, not as extra skills by default.
    
4. If a copied skill needs customization, edit the copied skill in place and record the reason in a change folder.
    
5. Keep task artifacts under `changes/YYYY-MM-DD-task-slug/` when the task is large enough to require persistent tracking.
    
6. Use the smallest process that preserves correctness. Do not create unnecessary process files for trivial tasks.
    
7. If a user says continue, resume, pick up, or similar, first read `changes/INDEX.md` if it exists, then read the latest relevant `changes/*/05-progress.md` and `changes/*/04-tasks.md`.
    
8. Do not claim completion without fresh verification evidence recorded in `06-verification.md`, or clearly state why verification could not be run.
    
9. Before executing any non-trivial coding task, create or update `03-plan.md` and `04-tasks.md` in the relevant change folder. Do not start implementation until the plan lists ordered tasks, expected file boundaries, and verification steps.
    
10. For frontend-backend data exchange, plan schema and API contract before implementation logic.
    
11. For brownfield work, inspect existing docs, patterns, callers, tests, and shared utilities before proposing changes.
    
12. During execution, update `04-tasks.md` and `05-progress.md` as each meaningful checklist item completes. Do not wait until the end to reconstruct progress from memory.
    

## Task Size Policy

Use the smallest workflow that preserves correctness, traceability, and resumability.

### Trivial Tasks

Trivial tasks include:

- Answering questions.
    
- Explaining existing files.
    
- Fixing typos.
    
- Small documentation edits.
    
- One-line config changes.
    
- Simple formatting-only changes.
    
- Direct copy, translation, or rewrite requests that do not require code changes.
    

For trivial tasks:

1. Do not create a full change folder unless the user asks.
    
2. Do not create unnecessary plan, task, progress, or verification files.
    
3. Still inspect relevant files before editing when file context matters.
    
4. Still verify when an obvious verification command exists.
    
5. If no verification is needed, state that the task was informational or documentation-only.
    

### Small Tasks

Small tasks include isolated changes that touch a limited number of files and do not require design trade-offs.

Examples:

- A small bug fix.
    
- A minor README update.
    
- Adding one copied skill.
    
- Updating one existing skill file.
    
- Renaming or reorganizing a small set of files.
    
- Updating a config file with a clear expected result.
    

For small tasks, create or update only the required lightweight change files:

- `00-change.md` - scope, source, and constraints.
    
- `04-tasks.md` - executable checklist.
    
- `05-progress.md` - resumable status and checkpoint.
    
- `06-verification.md` - verification commands and evidence.
    

Do not create the full `00` through `08` file set unless the task grows in complexity.

### Non-trivial Tasks

Non-trivial tasks include work that requires planning, design, multi-file edits, or verification across multiple surfaces.

Examples:

- New feature work.
    
- Bug fixes touching multiple files.
    
- Refactors.
    
- Frontend-backend changes.
    
- API schema or contract changes.
    
- Skill creation from scratch.
    
- Major skill customization.
    
- Workflow or repository structure changes.
    
- Security, testing, deployment, or release-related work.
    

For non-trivial tasks, create the full change folder:

- `00-change.md` - scope, source, and constraints.
    
- `01-requirements.md` - requirements and acceptance criteria.
    
- `02-design.md` - design and trade-offs.
    
- `03-plan.md` - ordered implementation plan.
    
- `04-tasks.md` - executable checklist.
    
- `05-progress.md` - resumable status and checkpoint.
    
- `06-verification.md` - verification commands and evidence.
    
- `07-review.md` - review findings and decisions.
    
- `08-archive.md` - lessons and follow-up skill improvements.
    

## Change Folder Rules

Each tracked task should live under:

```text
changes/YYYY-MM-DD-task-slug/
```

Use clear, lowercase, hyphen-separated slugs.

Examples:

```text
changes/2026-06-17-add-tdd-skill/
changes/2026-06-17-update-agent-rules/
changes/2026-06-17-review-browser-testing-skill/
```

When creating or updating a change folder:

1. Record the user request and scope in `00-change.md`.
    
2. Record assumptions and constraints clearly.
    
3. Keep file boundaries explicit.
    
4. Keep progress resumable.
    
5. Record verification evidence before claiming completion.
    
6. If verification cannot be run, record the reason in `06-verification.md`.
    

## Changes Index

Use `changes/INDEX.md` when the repository has more than one active or historical change folder.

The index should summarize task status and help future agents resume correctly.

Recommended format:

```md
# Changes Index

| Date | Slug | Status | Summary |
|---|---|---|---|
| 2026-06-17 | update-agent-rules | in-progress | Update AGENTS.md workflow rules |
| 2026-06-16 | add-tdd-skill | done | Add copied TDD skill |
```

Valid status values:

- `planned`
    
- `in-progress`
    
- `blocked`
    
- `done`
    
- `archived`
    

When starting a tracked task:

1. Add the task to `changes/INDEX.md` if the file exists.
    
2. Create `changes/INDEX.md` if multiple tracked tasks exist or if the user is likely to resume work later.
    
3. Update the status as the task progresses.
    
4. Mark the task `done` only after verification is recorded.
    

## Resume Policy

When the user says continue, resume, pick up, or similar:

1. Read `changes/INDEX.md` if it exists.
    
2. Identify the latest relevant change folder.
    
3. Read `05-progress.md`.
    
4. Read `04-tasks.md`.
    
5. Read `03-plan.md` if it exists.
    
6. Continue from the next incomplete task.
    
7. Do not restart the task from memory.
    
8. Do not claim completion without updating `05-progress.md` and `06-verification.md`.
    

If the latest relevant change folder is ambiguous, inspect recent change folders before asking the user.

## How To Use Skills

When a task may match a skill in `skills/`:

1. Read `skills/INDEX.md` first to identify candidate skills.
    
2. Choose the smallest relevant skill set. Do not load every skill.
    
3. Open the selected `skills/<skill-name>/SKILL.md` before acting.
    
4. Follow that skill's instructions as written unless the user's direct instruction or this `AGENTS.md` overrides it.
    
5. If multiple skills apply, use this order:
    
    - requirement/spec skills before planning skills.
        
    - planning skills before implementation skills.
        
    - debugging skills before fix attempts.
        
    - verification/review skills before completion claims.
        
6. If a selected skill references setup or prerequisites, satisfy those first or record why they were skipped.
    
7. If no copied skill fits, use the workflow docs in `workflows/` rather than inventing a new skill.
    
8. Do not create a new skill unless the user explicitly asks for a new custom skill.
    

Common routes:

- PRD from current context -> `skills/to-prd/SKILL.md`
    
- Break PRD or plan into issues -> `skills/to-issues/SKILL.md`
    
- Test-first implementation -> `skills/tdd/SKILL.md` or `skills/test-driven-development/SKILL.md`
    
- Debug failures -> `skills/diagnose/SKILL.md` or `skills/debugging-and-error-recovery/SKILL.md`
    
- Code review -> `skills/code-review-and-quality/SKILL.md`
    
- Browser/UI verification -> `skills/browser-testing-with-devtools/SKILL.md`
    
- Shipping docs or handoff -> `skills/shipping-artifacts/SKILL.md`
    

## How To Use Subagents

Subagents are execution helpers, not role expert personas.

When a task may need execution subagents:

1. Read `workflows/subagent-dispatch.md` before dispatching.
    
2. Dispatch subagents only when the workflow's dispatch gate is satisfied.
    
3. Use `templates/subagent-brief-template.md` for each subagent brief.
    
4. Keep `agents/` role experts advisory; do not treat them as execution subagents.
    
5. The main agent remains responsible for scope, edits, verification, progress records, and final completion claims.
    
6. Record subagent status and verification in the relevant change folder when the task is tracked.
    

## How To Use Role Experts

`agents/` contains role expert personas, not standard skills. Use them for domain judgment, review perspective, or specialist framing.

When a task may benefit from a role expert:

1. Use `skills/` first for process and execution workflow.
    
2. Read `agents/INDEX.md` to identify candidate role experts.
    
3. Choose at most one role expert by default. Use multiple only when the task genuinely needs distinct perspectives.
    
4. Open the selected `agents/<category>/<agent-file>.md` before relying on that expert perspective.
    
5. Use the role expert to inform analysis, review, questions, risks, or recommendations.
    
6. Do not let a role expert override direct user instructions, selected skills, or this `AGENTS.md`.
    
7. Record the chosen role expert in the relevant change file when it materially influences the work.
    
8. Treat role experts as advisory only.
    

A role expert does not grant permission to:

- Run tools.
    
- Create accounts.
    
- Install dependencies.
    
- Publish content.
    
- Move money.
    
- Scan external targets.
    
- Perform any other side effect.
    

Common role routes:

- Unfamiliar repo orientation -> `agents/engineering/engineering-codebase-onboarding-engineer.md`
    
- Backend/API design -> `agents/engineering/engineering-backend-architect.md`
    
- Frontend implementation -> `agents/engineering/engineering-frontend-developer.md`
    
- System architecture -> `agents/engineering/engineering-software-architect.md`
    
- Minimal scoped fix -> `agents/engineering/engineering-minimal-change-engineer.md`
    
- Code review perspective -> `agents/engineering/engineering-code-reviewer.md`
    
- App security review -> `agents/security/security-appsec-engineer.md`
    
- API testing -> `agents/testing/testing-api-tester.md`
    

## Planning Rules

Before implementation on non-trivial tasks:

1. Inspect existing docs, patterns, callers, tests, and shared utilities.
    
2. Identify relevant skills and role experts.
    
3. Define the expected file boundaries.
    
4. Define the ordered implementation steps.
    
5. Define verification commands or manual verification steps.
    
6. Record the plan in `03-plan.md`.
    
7. Record executable checklist items in `04-tasks.md`.
    

Do not start implementation until the plan is specific enough to resume from later.

## Frontend-Backend Contract Rules

For any task involving frontend-backend data exchange:

1. Define the API route or integration boundary.
    
2. Define request fields.
    
3. Define response fields.
    
4. Define error shape.
    
5. Define validation rules.
    
6. Define backwards compatibility concerns.
    
7. Record the contract before implementation logic.
    

Prefer schema-first planning for API changes.

## Execution Rules

During execution:

1. Work from `04-tasks.md`.
    
2. Update checklist items as they are completed.
    
3. Update `05-progress.md` after each meaningful step.
    
4. Keep changes surgical and scoped.
    
5. Do not refactor unrelated code.
    
6. Do not rewrite copied skills unless customization is explicitly required.
    
7. If a copied skill is customized, record the reason in the change folder.
    
8. If the task scope changes, update `00-change.md`, `01-requirements.md`, and `03-plan.md` as appropriate.

## Failure Handling Rules

If a planned step fails:

1. Record the failure in `05-progress.md`.
2. Record command output or evidence in `06-verification.md` when applicable.
3. Diagnose before retrying.
4. Do not silently skip failed steps.
5. If the failure changes scope, update `00-change.md` and `03-plan.md`.
6. If blocked, mark the task as `blocked` in `changes/INDEX.md`.
7. Do not claim completion while any planned step remains failed, skipped, or blocked unless the user explicitly accepts the limitation.


## Verification Rules

Before claiming completion:

1. Run the planned verification steps when possible.
    
2. Record commands, outputs, and evidence in `06-verification.md`.
    
3. If verification fails, record the failure and continue diagnosis.
    
4. If verification cannot be run, record why.
    
5. Do not claim a task is complete based only on code inspection unless the task is explicitly inspection-only.
    

Examples of verification evidence:

````md
## Verification

Command:

```bash
npm test
````

Result:

```text
All tests passed.
```

````

For documentation-only changes:

```md
## Verification

No runtime verification required. Reviewed Markdown formatting and confirmed links/paths are correct.
````

## Review Rules

For non-trivial tasks, update `07-review.md` before final completion.

Include:

- What changed.
    
- Risks.
    
- Known limitations.
    
- Whether the selected skill was followed.
    
- Whether a role expert influenced decisions.
    
- Follow-up recommendations.
    

## Archive Rules

Use `08-archive.md` to record:

- Lessons learned.
    
- Reusable patterns.
    
- Workflow improvements.
    
- Possible future skills.
    
- Cleanup tasks.
    

If a task reveals that an existing skill should be improved, record the suggested improvement in `08-archive.md` instead of silently changing unrelated skills.

## Conflict Resolution

Instruction priority:

1. Direct user instruction.
    
2. This `AGENTS.md`.
    
3. Selected `skills/<skill-name>/SKILL.md`.
    
4. Selected `agents/<category>/<agent-file>.md`.
    
5. Other workflow or template docs.
    
6. General model assumptions.
    

If instructions conflict:

1. Follow the higher-priority instruction.
    
2. Record the conflict in the relevant change file when it affects implementation.
    
3. Ask the user only when the conflict cannot be safely resolved.
    
4. Do not invent new policy to bypass existing rules.
    

## Completion Standard

A task may be called complete only when:

1. The requested scope is satisfied.
    
2. Relevant task checklist items are complete.
    
3. Progress files are updated.
    
4. Verification evidence is recorded, or the reason verification could not be run is documented.
    
5. Review notes are recorded for non-trivial tasks.
    
6. The final response clearly states what changed and how it was verified.
    

Do not overstate completion. If something was skipped, blocked, or unverified, say so clearly.
