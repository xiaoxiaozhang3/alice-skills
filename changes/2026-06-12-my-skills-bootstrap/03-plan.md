# Plan

## Goal

Generate the first version of `/Users/mac/Documents/obsidian/my-skills`.

## Files And Responsibilities

| File/Dir | Responsibility |
|---|---|
| `AGENTS.md` | Agent rules for this repository |
| `README.md` | Human-facing overview |
| `workflows/*.md` | Process governance |
| `skills/*/SKILL.md` | Reusable skills |
| `changes/2026-06-12-my-skills-bootstrap/*` | Bootstrap run record |
| `templates/*` | Reusable file templates |
| `evals/*` | Trigger and quality checks |

## Tasks

- [x] Create root directories
- [x] Write AGENTS and README
- [x] Write workflow files
- [x] Write templates and evals
- [x] Write bootstrap change files
- [ ] Write all skill `SKILL.md` files
- [ ] Verify tree and required file count

## API/Data Contract Gate

This bootstrap does not implement frontend-backend data exchange. The schema-first rule is added to workflow and plan templates for future changes.
