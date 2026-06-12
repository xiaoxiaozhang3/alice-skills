# My Skills

A personal Agent Skill source repository for AI coding work.

This first version is an engineering workflow pack. It is not a full copy of the upstream skill collections. It selects useful patterns from local skill repositories, Superpowers, and OpenSpec-style workflows, then rewrites them into a small personal system.

## Shape

```text
my-skills/
  AGENTS.md
  README.md
  workflows/
  changes/
  skills/
  templates/
  evals/
```

## Core Flow

```text
clarify -> spec -> plan -> execute -> verify -> review -> release -> document
```

## First Skill Set

- `use-engineering-skills` - choose the right workflow and skill
- `clarify-requirements` - clarify ambiguous work before planning
- `write-spec` - create focused specs and design docs
- `plan-implementation` - turn specs into ordered tasks
- `tdd-implementation` - implement behavior with red-green-refactor
- `execute-tasks` - execute a written plan with checklist checkpoints
- `resume-change` - continue from a saved progress checkpoint
- `diagnose-bug` - debug from evidence instead of guessing
- `source-grounded-implementation` - use official docs when libraries or APIs matter
- `code-review` - review changes for correctness, tests, maintainability, and risk
- `simplify-code` - reduce complexity without changing behavior
- `security-review` - check auth, data, input, secrets, and trust boundaries
- `browser-verify` - verify browser/UI behavior in a real runtime
- `release-check` - prepare release, rollback, monitoring, and risk notes
- `document-decisions` - archive decisions, evidence, and lessons

## Changes

Every real task should create a folder under `changes/`. This follows an OpenSpec-inspired flow: one change, one folder, one auditable trail.

## Installing Elsewhere

This repository is the source workspace. Copy or sync selected `skills/<name>/` folders into Codex or another agent runtime only after they have useful trigger cases and a self-check.
