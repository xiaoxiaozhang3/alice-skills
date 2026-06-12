# My Skills Agent Rules

This directory is a personal Agent Skill source repository. Treat it as a skill design workspace, not as a dump of upstream skills.

## Operating Rules

1. Keep changes inside this repository unless the user explicitly asks to install skills elsewhere.
2. Reuse existing patterns from this repository before inventing new ones.
3. Do not mechanically copy upstream skills. Extract the reusable rule, decision tree, checklist, or template, then rewrite it for this repository.
4. Keep `SKILL.md` concise. Move long examples, rubrics, and source notes into `references/` when a skill grows large.
5. Every skill must have clear trigger conditions, non-use cases, a decision tree when branching is non-obvious, anti-patterns with alternatives, and a self-check checklist.
6. Every task run must live under `changes/YYYY-MM-DD-task-slug/`. Do not scatter design, plan, progress, verification, or review files.
7. If a user says continue, resume, or pick up from last time, first read the latest relevant `changes/*/05-progress.md` and `changes/*/04-tasks.md`.
8. Do not claim completion without fresh verification evidence recorded in `06-verification.md`.
9. For frontend-backend data exchange, plan schema and API contract before implementation logic.
10. For brownfield work, inspect existing docs, patterns, callers, tests, and shared utilities before proposing changes.

## Required Change Files

Each change folder should contain:

- `00-change.md` - scope, source, and constraints
- `01-requirements.md` - requirements and acceptance criteria
- `02-design.md` - design and trade-offs
- `03-plan.md` - ordered implementation plan
- `04-tasks.md` - executable checklist
- `05-progress.md` - resumable status and checkpoint
- `06-verification.md` - verification commands and evidence
- `07-review.md` - review findings and decisions
- `08-archive.md` - lessons and follow-up skill improvements

## Source Inspiration

This repository intentionally borrows from:

- `/Users/mac/Documents/obsidian/skills`
- Superpowers skills: brainstorming, writing-plans, executing-plans, subagent-driven-development, verification-before-completion, writing-skills
- OpenSpec-style change folders: propose, apply, archive
- Flow-kit notes: fixed artifacts, brownfield guardrails, checklist execution, and resumable progress
