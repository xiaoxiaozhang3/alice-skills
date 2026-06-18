# Plan

## Goal

[State the implementation outcome.]

## File Boundaries

| Path | Action | Responsibility |
|---|---|---|
| `[path]` | create / modify / read-only | [purpose] |

## Verification Strategy

- Automated: `[smallest command that proves intent]`
- Manual: [check, or not applicable]
- Final integration: `[combined verification command]`

## Ordered Tasks

### Task 1: [Name]

**depends_on:** none

**can_parallelize:** no

**allowed_files:**

- `[path or pattern]`

**forbidden_files:**

- `[path or pattern]`

**expected_output:**

- [Concrete artifact or behavior]

**verification:**

- `[command or evidence]`

**stop condition:**

- Stop and report `[NEEDS_CONTEXT or BLOCKED]` if [specific condition].

**steps:**

1. [Implementation step]
2. [Verification step]

## Integration Order

1. [Task or parallel batch]
2. Main-agent specification check
3. Independent batch quality review when the approved plan uses Subagents
4. Main-agent integration and final verification
