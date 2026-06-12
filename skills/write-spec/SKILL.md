---
name: write-spec
description: Use when a non-trivial coding change needs a written design, proposal, PRD, or implementation-ready specification before planning.
---

# Write Spec

## Purpose

Create a focused design that records intent, approach, trade-offs, and verification before code.

## Source Ideas

`spec-driven-development`, `create-prd`, `to-prd`, Superpowers `brainstorming`, OpenSpec propose.

## Process

1. Read `01-requirements.md` and relevant project context.
2. Present 2-3 approaches when meaningful.
3. Recommend one approach and record trade-offs.
4. Write `02-design.md`.
5. Get approval before planning.

## Design Must Cover

- Goal and non-goals
- Architecture or code boundaries
- Data flow
- Error handling
- Tests and verification
- Rollback or migration notes when relevant

## Self-Check

- [ ] No TBD/TODO placeholders
- [ ] Requirements map to design choices
- [ ] Scope is small enough for one plan
- [ ] Risks and rejected alternatives are recorded
