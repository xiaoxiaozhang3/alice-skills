# Skill Selection Rules

Start here when deciding what to load.

## Decision Tree

```text
Need to resume prior work?
  yes -> workflows/checkpoint-resume.md
  no -> continue

Requirements unclear?
  yes -> to-prd or create-prd
  no -> continue

Non-trivial change without written spec?
  yes -> spec-driven-development
  no -> continue

Written spec but no task plan?
  yes -> planning-and-task-breakdown
  no -> continue

Executing a plan?
  yes -> incremental-implementation
  no -> continue

Independent workstreams or selected skill requires subagents?
  yes -> workflows/subagent-dispatch.md
  no -> continue

Bug, failing test, broken behavior, performance regression?
  yes -> diagnose or debugging-and-error-recovery
  no -> continue

External library/API correctness matters?
  yes -> source-driven-development

Browser/UI behavior matters?
  yes -> browser-testing-with-devtools

Before claiming done?
  yes -> code-review-and-quality and workflows/completion-gates.md
```

## Small Task Exception

For trivial work, do not force the full lifecycle. Still inspect the relevant file, make the smallest change, verify, and record what was done if a change folder exists.
