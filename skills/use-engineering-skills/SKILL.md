---
name: use-engineering-skills
description: Use when starting, routing, resuming, or governing an AI coding task in this personal skill repository.
---

# Use Engineering Skills

## Purpose

Choose the lightest safe workflow and keep all work in the fixed change structure.

## Source Ideas

Superpowers `using-superpowers`, flow-kit GO, OpenSpec change routing.

## Decision Tree

```text
Resuming prior work?
  yes -> use resume-change
  no -> continue

Task is trivial and clear?
  yes -> inspect -> edit -> verify
  no -> continue

Requirements unclear?
  yes -> clarify-requirements
  no -> continue

No written design/spec?
  yes -> write-spec
  no -> continue

No executable plan?
  yes -> plan-implementation
  no -> execute-tasks
```

## Required Rules

- Put every non-trivial task under `changes/YYYY-MM-DD-slug/`.
- Use `05-progress.md` for checkpoints.
- Use `06-verification.md` before any completion claim.
- For frontend-backend data exchange, require schema and API contract before logic.

## Self-Check

- [ ] Chose the lightest safe route
- [ ] Created or identified the change folder
- [ ] Did not skip resume state
- [ ] Did not claim completion without verification
