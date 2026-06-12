---
name: tdd-implementation
description: Use when implementing behavior, fixing bugs, changing logic, or adding tests where correctness must be proven.
---

# TDD Implementation

## Purpose

Use red-green-refactor for behavior changes and bug fixes.

## Source Ideas

Superpowers `test-driven-development`, Matt Pocock `tdd`.

## Process

1. Identify the smallest behavior to prove.
2. Write or update a failing test first.
3. Run it and record the failure.
4. Implement the smallest passing change.
5. Run the test and record pass evidence.
6. Refactor only after green.
7. Update `04-tasks.md`, `05-progress.md`, and `06-verification.md`.

## Anti-Patterns And Alternatives

| Anti-Pattern | Use Instead |
|---|---|
| Writing implementation before test | Delete or ignore it, write the test first |
| Testing private internals | Test observable behavior |
| Huge end-to-end test for tiny logic | Use the smallest meaningful test |

## Self-Check

- [ ] Red failure was observed
- [ ] Green pass was observed
- [ ] Test proves the requirement, not implementation trivia
- [ ] Verification evidence was recorded
