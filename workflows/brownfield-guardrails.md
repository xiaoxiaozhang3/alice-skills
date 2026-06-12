# Brownfield Guardrails

Use when changing an existing codebase.

## Before Design

- [ ] Read local rules such as AGENTS.md, CLAUDE.md, README, architecture docs
- [ ] Inspect relevant files and callers
- [ ] Identify existing abstractions to reuse
- [ ] Identify tests or verification commands
- [ ] State what will not be touched

## Write Boundaries

In `03-plan.md`, each task should list:

- `read_files`
- `write_files`
- `verification`
- `rollback_notes` when risk is meaningful

## Destructive Change Gate

Before deleting code, changing public interfaces, migrating data, or altering auth/security behavior:

- [ ] Search callers/usages
- [ ] Record impact in `02-design.md` or `03-plan.md`
- [ ] Add verification covering the old and new behavior
- [ ] Ask for approval if blast radius is unclear

## Schema-First API Gate

For frontend-backend data exchange, do not begin implementation tasks until schema and API contract are explicit in the plan.
