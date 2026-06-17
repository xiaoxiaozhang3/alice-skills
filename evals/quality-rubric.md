# Quality Rubric

Score each skill from 0-2 on each axis.

## Manual Evaluation Run

Use this as the lightweight evaluation entrypoint for one skill.

1. Read `skills/INDEX.md` and choose the candidate skill.
2. Read `skills/<skill>/SKILL.md` plus only the referenced files needed for that skill.
3. Score the skill with the rubric below.
4. Check the skill against `evals/skill-judge-checklist.md`.
5. Test trigger behavior with the closest cases in `evals/trigger-cases.md`.
6. Record the result as `score/14`, pass/fail, and the top 1-3 fixes.

| Axis | 0 | 1 | 2 |
|---|---|---|---|
| Trigger clarity | vague | usable | precise with boundaries |
| Knowledge delta | generic | some local value | captures expert judgment |
| Decision guidance | none | partial | clear decision tree or gate |
| Anti-pattern handling | none | says no | gives replacement behavior |
| Self-check | none | generic | checks output and evidence |
| Progressive disclosure | bloated or missing | acceptable | core in SKILL.md, details linked |
| Evaluation | none | examples only | should/should-not trigger cases |

A skill should not be considered stable below 10/14.

## TRACE Mapping

Use TRACE as the plain-language summary after scoring.

| TRACE Axis | Local Evidence |
|---|---|
| Trust | Clear scope, minimal permissions, source noted, secrets and external calls handled safely |
| Reliability | Self-checks, failure handling, verification steps, and stable trigger cases |
| Adaptability | Trigger clarity, should/should-not cases, and explicit boundaries |
| Convention | Naming, concise structure, progressive disclosure, and referenced details |
| Effectiveness | Knowledge delta, decision guidance, output format, and replacement behavior for anti-patterns |

Pass line: `10/14` or higher, no critical Trust issue, and at least one should-not-trigger case.
