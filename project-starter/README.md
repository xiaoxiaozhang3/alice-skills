# General-Purpose Project Starter

This directory is a self-contained guidance package for a new software project.
It combines always-on project rules, optional advisory roles, lifecycle Skills,
adaptive workflows, and resumable change templates without requiring the source
library at runtime.

## Copy Into A Project

From the directory that contains `project-starter/`, run:

```bash
mkdir -p path/to/new-project
cp -R project-starter/. path/to/new-project/
cd path/to/new-project
```

Copy the contents, including all subdirectories, into the project root. Review
the resulting diff before combining it with an existing repository; do not
overwrite project-specific guidance without comparing it first.

## Customize Before Use

Open `AGENTS.md` and replace its bracketed fields with:

- Project purpose and non-goals.
- Technology stack and architecture notes.
- Install, run, build, test, lint, format, and type-check commands.
- Repository-specific generated, vendored, protected, or ownership boundaries.
- Deployment environments, release process, and production restrictions.
- Sensitive-data handling requirements.

Add roles or Skills only when the project genuinely requires them. Keep one
default Skill per lifecycle concern to avoid ambiguous routing.

## Primary Entry Points

- `AGENTS.md` — always-on safety, task routing, execution, Git, verification,
  and completion rules.
- `DESIGN.md` — durable visual and interaction contract for UI projects.
- `agents/INDEX.md` — bundled advisory roles and when to consult them.
- `skills/INDEX.md` — bundled lifecycle Skills and deterministic routing.
- `workflows/` — detailed procedures referenced by `AGENTS.md`.
- `templates/` — resumable change records and Subagent briefs.

## UI Projects

Before implementing or materially changing an interface, complete the required
fields in root `DESIGN.md` and obtain approval for its visual direction. Reuse
its tokens and shared components, then verify the implementation in the browser
against its states, responsive, accessibility, and Design QA requirements.

`DESIGN.md` contains durable product styling only. Keep technical architecture
in project architecture records and task-specific decisions in the relevant
change design document.

## Bundled And Optional Roles

The starter includes a deliberately small set of broadly useful advisory roles.
They provide specialist judgment but do not grant permission to edit, deploy,
publish, contact others, or take external actions.

The source `alice-skills` repository contains a larger optional role catalog.
Consult its `agents/INDEX.md` when curating additional roles, then copy only the
specific role files the project needs. Normal starter operation does not depend
on that repository or its path.

## Working With Changes

Simple work follows an inspect-change-verify-report loop. Small work uses light
tracking only when resumability is useful. Complex work uses the complete
numbered change set. Follow the **Task Routing** and **Change Tracking** sections
in `AGENTS.md` for the canonical classification, instantiated-record location,
template-copy procedure, change index, resume behavior, and completion gates.
Do not edit the files under `templates/change/` as live task records.
