---
name: diagnose-bug
description: Use when behavior is broken, tests fail, builds fail, errors appear, or performance regresses.
---

# Diagnose Bug

## Purpose

Find root cause from evidence before changing code.

## Source Ideas

Superpowers `systematic-debugging`, Matt Pocock `diagnose`.

## Process

1. Reproduce or capture the symptom.
2. Minimize the failing case.
3. Inspect relevant code paths and recent changes.
4. Form one hypothesis at a time.
5. Add instrumentation or targeted checks when needed.
6. Fix the root cause, not the symptom.
7. Add regression verification.

## Anti-Patterns And Alternatives

| Anti-Pattern | Use Instead |
|---|---|
| Guessing a fix immediately | Reproduce first |
| Fixing multiple things at once | Test one hypothesis at a time |
| Trusting logs without context | Trace the code path and data state |

## Self-Check

- [ ] Symptom was reproduced or evidence captured
- [ ] Root cause is stated
- [ ] Fix maps to root cause
- [ ] Regression verification was recorded
