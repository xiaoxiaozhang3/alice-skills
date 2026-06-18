# Brownfield Guardrails

Use these guardrails when changing an existing codebase. Task size remains
defined by `AGENTS.md` and `engineering-lifecycle.md`.

## Before Design Or Editing

- [ ] Read project rules, README files, architecture records, and relevant design documentation.
- [ ] Inspect the current implementation, callers, tests, schemas, migrations, and shared utilities.
- [ ] Identify existing abstractions and dependencies to reuse.
- [ ] Identify the smallest verification that proves the intended behavior.
- [ ] State the file boundary and what will not be touched.
- [ ] Preserve unrelated user changes and existing compatibility unless removal is approved.

## Planned Write Boundaries

For tracked work, each implementation task should record:

- `read_files`
- `allowed_files`
- `forbidden_files`
- `verification`
- `rollback_notes` when risk is meaningful

## Destructive Change Gate

Before deleting code, changing public interfaces, migrating or deleting data,
or altering authentication, authorization, or other security behavior:

- [ ] Search all relevant callers and usages.
- [ ] Record impact, compatibility, recovery, and rollback considerations in the design or plan.
- [ ] Add verification for affected old and new behavior.
- [ ] Plan backups and integrity checks for data changes.
- [ ] Obtain explicit approval when the operation is irreversible or the blast radius is unclear.

Do not disable a security control to make verification pass.

## Schema-First API Gate

For frontend-backend data exchange, do not begin implementation until the plan
defines request, response, validation, error, authorization, compatibility, and
data-shape behavior. Keep frontend and backend types aligned and include a
contract-level fixture or test.
