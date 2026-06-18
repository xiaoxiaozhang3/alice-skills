# Default Skill Routing

Use the single default Skill listed for the lifecycle concern that matches the task. Open its `SKILL.md` before acting, and load only the Skills needed for the current task.

| Lifecycle concern | Default Skill | Trigger |
|---|---|---|
| Specification | [`spec-driven-development`](spec-driven-development/SKILL.md) | A significant feature or change needs explicit requirements and acceptance criteria before implementation. |
| Planning | [`planning-and-task-breakdown`](planning-and-task-breakdown/SKILL.md) | Approved requirements need ordered tasks, dependencies, file boundaries, and verification steps. |
| Incremental delivery | [`incremental-implementation`](incremental-implementation/SKILL.md) | A multi-file change should be delivered and verified in small, coherent slices. |
| Test-first implementation | [`test-driven-development`](test-driven-development/SKILL.md) | New or changed behavior should be implemented through a red-green-refactor loop. |
| Debugging and recovery | [`debugging-and-error-recovery`](debugging-and-error-recovery/SKILL.md) | A failure, regression, or unexpected result requires root-cause diagnosis before a fix. |
| Code review and quality | [`code-review-and-quality`](code-review-and-quality/SKILL.md) | Completed changes need a structured correctness, maintainability, and regression review. |
| Security and hardening | [`security-and-hardening`](security-and-hardening/SKILL.md) | Work touches authentication, authorization, input, storage, secrets, permissions, or external integrations. |
| Documentation and decisions | [`documentation-and-adrs`](documentation-and-adrs/SKILL.md) | A durable technical decision, operating constraint, or handoff context must be recorded. |

## Deterministic Defaults

- Use `test-driven-development` as the only bundled TDD route; do not introduce a second TDD default.
- Use `debugging-and-error-recovery` as the only bundled debugging route; do not introduce a second diagnosis default.
- If several concerns apply, use the lifecycle order represented above rather than substituting an overlapping Skill.

## Standalone Adaptations

The bundled Skills originate from the source Skill collection. Four copies contain intentional, narrowly scoped changes so this starter has no missing operational dependencies:

- `spec-driven-development`: replaces the unavailable `context-engineering` dependency with an inline rule for loading only task-relevant specification sections, files, callers, utilities, and tests.
- `security-and-hardening`: replaces two unavailable `references/security-checklist.md` references with the OWASP 2021 ordering and instructions that use the Skill's own security and verification checklists.
- `code-review-and-quality`: replaces unavailable security and performance reference files with a link to the bundled `security-and-hardening` Skill and a complete inline performance-review instruction.
- `test-driven-development`: replaces the unavailable testing-patterns reference with explicit routing to the Skill's bundled testing guidance and repository-local test conventions.

The other four bundled Skill directories remain byte-for-byte identical to their source copies.
