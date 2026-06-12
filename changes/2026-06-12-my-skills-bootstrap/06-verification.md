# Verification

## Commands

| Command | Result | Evidence |
|---|---|---|
| `find /Users/mac/Documents/obsidian/my-skills -maxdepth 3 -type f | sort` | pass | Listed AGENTS, README, workflows, bootstrap change files, evals, templates, and all skill files |
| `find /Users/mac/Documents/obsidian/my-skills/skills -type f -name 'SKILL.md' | wc -l` | pass | Output: `15` |
| `find /Users/mac/Documents/obsidian/my-skills -maxdepth 2 -type d | sort` | pass | Listed root, changes, evals, skills, templates, workflows, and 15 skill directories |
| `rg -n '^name:|^description:' /Users/mac/Documents/obsidian/my-skills/skills --glob 'SKILL.md'` | pass | All 15 skill files expose `name` and `description` frontmatter |

## Manual Checks

- [x] AGENTS.md exists
- [x] README.md exists
- [x] workflows exist
- [x] changes bootstrap folder exists
- [x] templates exist
- [x] evals exist
- [x] 15 skill files exist

## Risks

- v1 skills are concise drafts and should be iterated with real trigger cases before installation into Codex.
