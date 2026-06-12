---
name: source-grounded-implementation
description: Use when framework, library, API, standard, or tool behavior may have changed or correctness depends on authoritative documentation.
---

# Source-Grounded Implementation

## Purpose

Ground implementation choices in primary sources when memory may be stale.

## Source Ideas

`source-driven-development`, Context7/OpenAI-doc style source rules.

## Process

1. Identify the exact library, API, version, or standard.
2. Prefer official docs, local docs, or source code.
3. Record the relevant source and decision in `02-design.md` or `03-plan.md`.
4. Implement only the needed pattern.
5. Verify against the documented behavior.

## When Not To Use

- Pure local code with stable behavior already visible in the repo
- Tiny edits unrelated to external APIs

## Self-Check

- [ ] Primary source was consulted when needed
- [ ] Version or environment assumptions are recorded
- [ ] No deprecated or guessed API was introduced
- [ ] Verification matches the documented behavior
