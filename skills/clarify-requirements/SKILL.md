---
name: clarify-requirements
description: Use when a coding request is vague, ambiguous, missing user value, missing constraints, or missing acceptance criteria.
---

# Clarify Requirements

## Purpose

Turn vague intent into a small set of requirements that can be designed and verified.

## Source Ideas

`interview-me`, `grill-with-docs`, Superpowers `brainstorming`.

## Process

1. Read relevant project rules and prior change files if present.
2. Ask one question at a time.
3. Capture purpose, user, scope, constraints, and acceptance criteria in `01-requirements.md`.
4. Stop when the next step can be designed without guessing.

## Decision Tree

```text
Does the request define success?
  no -> ask acceptance criteria
  yes -> continue

Does it touch existing behavior?
  yes -> inspect docs/code and ask about compatibility
  no -> continue

Multiple independent features?
  yes -> split into separate changes
  no -> write requirements
```

## Anti-Patterns And Alternatives

| Anti-Pattern | Use Instead |
|---|---|
| Guessing hidden requirements | Ask one focused question |
| Asking five questions at once | Ask the highest-leverage question first |
| Treating examples as full spec | Convert examples into acceptance criteria |

## Self-Check

- [ ] Acceptance criteria are explicit
- [ ] Out-of-scope items are named
- [ ] Ambiguities are resolved or recorded
- [ ] Requirements are saved in the change folder
