# Design

## Approach

Create a personal Agent Skill source repository that combines three ideas:

1. Standard `skills/<name>/SKILL.md` folders for reusable agent capabilities.
2. OpenSpec-style `changes/<date>-<slug>/` folders for auditable task execution.
3. Superpowers-style governance for planning, task execution, review, and verification gates.

## Directory Design

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

## Source Mapping

| Local Skill | Borrowed From |
|---|---|
| `use-engineering-skills` | Superpowers `using-superpowers`, flow-kit GO, skill index idea |
| `clarify-requirements` | `interview-me`, `grill-with-docs`, Superpowers `brainstorming` |
| `write-spec` | `spec-driven-development`, `create-prd`, OpenSpec propose |
| `plan-implementation` | Superpowers `writing-plans`, `planning-and-task-breakdown`, `to-issues` |
| `tdd-implementation` | Superpowers `test-driven-development`, Matt Pocock `tdd` |
| `execute-tasks` | Superpowers `executing-plans`, `subagent-driven-development`, GSD task execution |
| `resume-change` | OpenSpec change folder, flow-kit SUMMARY/progress pattern |
| `diagnose-bug` | Superpowers `systematic-debugging`, Matt Pocock `diagnose` |
| `source-grounded-implementation` | `source-driven-development` |
| `code-review` | `code-review-and-quality`, Superpowers `requesting-code-review` |
| `simplify-code` | `code-simplification`, architecture simplification patterns |
| `security-review` | `security-and-hardening`, `intended-vs-implemented` |
| `browser-verify` | `browser-testing-with-devtools`, UI verification practices |
| `release-check` | `shipping-and-launch`, `pre-mortem`, verification gate |
| `document-decisions` | `documentation-and-adrs`, `shipping-artifacts`, OpenSpec archive |

## Key Decisions

- Do not create a separate schema-first API skill. Make schema-first a planning and rules gate.
- Do not copy `agency-agents` as skills; it is a persona collection.
- Do not make this a PM marketplace in v1.
- Keep v1 concise and editable, with room for later references/scripts.

## Risks

- Skills are first-pass drafts and need pressure testing before installing into Codex.
- Some source projects have stricter or heavier workflows; this repository intentionally keeps a lighter personal version.
