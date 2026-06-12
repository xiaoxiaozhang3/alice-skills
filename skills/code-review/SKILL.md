---
name: code-review
description: Use when reviewing completed changes, self-reviewing before merge, or checking another agent's code for bugs and risk.
---

# Code Review

## Purpose

Find correctness, requirement, testing, and maintainability issues before work is called done.

## Source Ideas

`code-review-and-quality`, Superpowers `requesting-code-review`.

## Review Order

1. Requirement/spec compliance
2. Behavior and edge cases
3. Test quality and coverage
4. Security and data risks
5. Maintainability and simplicity
6. Integration and migration risks

## Output Format

Findings first, ordered by severity. Include file paths and exact evidence when available.

## Self-Check

- [ ] Reviewed against requirements, not only code style
- [ ] Checked tests and missing verification
- [ ] Separated must-fix from optional cleanup
- [ ] Did not hide uncertainty
