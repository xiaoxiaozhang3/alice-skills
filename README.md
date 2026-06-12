# Alice Skills

A curated personal skill directory made from existing mature Agent Skills.

This repository is not a rewritten aggregate pack. The `skills/` directory contains selected upstream `SKILL.md` folders copied directly from the local Obsidian skill collections because they fit the current AI coding workflow.

## Current Shape

```text
alice-skills/
  AGENTS.md
  README.md
  skills/
  workflows/
  changes/
  templates/
  evals/
```

## Skills Policy

- `skills/` contains executable, mature skill folders copied from existing sources.
- Do not add hand-written aggregate skills unless the user explicitly asks.
- Workflow notes, checkpoints, and OpenSpec-style change tracking live outside `skills/`.
- If a source skill needs customization, copy it first, then edit the copied version in place with a change record.

## Included Skill Groups

### Matt Pocock Engineering Skills

- `to-prd`
- `to-issues`
- `tdd`
- `diagnose`
- `grill-with-docs`
- `zoom-out`
- `improve-codebase-architecture`
- `prototype`
- `triage`
- `setup-matt-pocock-skills`

### Addy Osmani Agent Skills

- `spec-driven-development`
- `planning-and-task-breakdown`
- `incremental-implementation`
- `test-driven-development`
- `debugging-and-error-recovery`
- `code-review-and-quality`
- `code-simplification`
- `security-and-hardening`
- `source-driven-development`
- `browser-testing-with-devtools`
- `shipping-and-launch`
- `documentation-and-adrs`

### PM / Shipping Skills

- `create-prd`
- `test-scenarios`
- `pre-mortem`
- `strategy-red-team`
- `intended-vs-implemented`
- `shipping-artifacts`

## Notes

Use `workflows/` and `templates/` for your additional process rules: fixed change folders, checklists, resume checkpoints, completion gates, and schema-first API planning.
