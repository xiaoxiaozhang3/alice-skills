# Subagent Brief

## Goal

[One narrow, independently verifiable task.]

## Brief Source

`[change folder, plan file, and task number]`

## Dependency And Parallelization

- **depends_on:** [none or task identifiers]
- **can_parallelize:** [yes or no]

## Allowed Files

- `[path or pattern]`

## Forbidden Files

- `[path or pattern]`

## Context To Read

- `[file, workflow, or requirement]`

## Expected Output

- [Concrete artifact, finding, or behavior]
- Status: `DONE`, `DONE_WITH_CONCERNS`, `NEEDS_CONTEXT`, or `BLOCKED`

## Verification Or Evidence

- `[scoped command, check, or evidence requirement]`

## Report Path

`[changes/YYYY-MM-DD-task-slug/task-name-report.md]`

## Report Handoff

Write the detailed report to the report path. Return only status, touched files, verification summary, and concerns. The main agent owns integration and final verification.

## Stop Condition

Stop and report `[NEEDS_CONTEXT or BLOCKED]` if [specific dependency, boundary, conflict, or verification condition].
