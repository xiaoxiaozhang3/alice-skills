# Verification

## Current Final State

`alice-skills/skills` now contains mature upstream skill folders copied directly from existing local skill collections. The earlier custom aggregate skill folders were moved out of `alice-skills`.

## Commands

| Command | Result | Evidence |
|---|---|---|
| `find /Users/mac/Documents/obsidian/alice-skills/skills -type f -name 'SKILL.md' | wc -l` | pass | Output: `28` |
| `find /Users/mac/Documents/obsidian/alice-skills/skills -maxdepth 2 -type f -name 'SKILL.md' ...` | pass | Listed 28 copied mature skills including `to-prd`, `to-issues`, `tdd`, `diagnose` |
| `test ! -e /Users/mac/Documents/obsidian/alice-skills/vendor && echo 'vendor absent'` | pass | Output: `vendor absent` |
| custom aggregate directory check | pass | No custom aggregate skill names remain in `alice-skills/skills` |

## Included Skills

- `browser-testing-with-devtools`
- `code-review-and-quality`
- `code-simplification`
- `create-prd`
- `debugging-and-error-recovery`
- `diagnose`
- `documentation-and-adrs`
- `grill-with-docs`
- `improve-codebase-architecture`
- `incremental-implementation`
- `intended-vs-implemented`
- `planning-and-task-breakdown`
- `pre-mortem`
- `prototype`
- `security-and-hardening`
- `setup-matt-pocock-skills`
- `shipping-and-launch`
- `shipping-artifacts`
- `source-driven-development`
- `spec-driven-development`
- `strategy-red-team`
- `tdd`
- `test-driven-development`
- `test-scenarios`
- `to-issues`
- `to-prd`
- `triage`
- `zoom-out`

## Risks

- Copied skills may reference assumptions from their original ecosystem. Review and adapt only when you actually use them.
