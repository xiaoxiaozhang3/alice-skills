# Skill Selection Rules

Start here when deciding what to load.

## Decision Tree

```text
Need to resume prior work?
  yes -> resume-change
  no -> continue

Requirements unclear?
  yes -> clarify-requirements
  no -> continue

Non-trivial change without written spec?
  yes -> write-spec
  no -> continue

Written spec but no task plan?
  yes -> plan-implementation
  no -> continue

Executing a plan?
  yes -> execute-tasks
  no -> continue

Bug, failing test, broken behavior, performance regression?
  yes -> diagnose-bug
  no -> continue

External library/API correctness matters?
  yes -> source-grounded-implementation

Browser/UI behavior matters?
  yes -> browser-verify

Before claiming done?
  yes -> code-review and completion-gates
```

## Small Task Exception

For trivial work, do not force the full lifecycle. Still inspect the relevant file, make the smallest change, verify, and record what was done if a change folder exists.
