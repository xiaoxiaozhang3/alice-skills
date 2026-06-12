---
name: simplify-code
description: Use when code works but is unnecessarily complex, duplicated, hard to read, hard to test, or difficult to change.
---

# Simplify Code

## Purpose

Reduce complexity without changing behavior.

## Source Ideas

`code-simplification`, Matt Pocock architecture/deepening ideas.

## Process

1. Identify the behavior that must remain unchanged.
2. Find duplication, tangled responsibilities, unclear names, or unnecessary abstractions.
3. Prefer small local simplifications over broad refactors.
4. Preserve public interfaces unless the change explicitly requires altering them.
5. Run behavior-preserving verification.

## Anti-Patterns And Alternatives

| Anti-Pattern | Use Instead |
|---|---|
| Refactor unrelated files | Touch only code serving this change |
| Add abstraction for one use | Inline or keep direct code |
| Change behavior while simplifying | Separate behavior change into another task |

## Self-Check

- [ ] Behavior-preserving verification exists
- [ ] Scope stayed local
- [ ] Complexity actually decreased
- [ ] No speculative abstraction was added
