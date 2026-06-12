---
name: browser-verify
description: Use when a change affects browser-rendered UI, DOM behavior, client routing, network requests, forms, responsiveness, or visual output.
---

# Browser Verify

## Purpose

Verify browser behavior in the real runtime, not only from code inspection.

## Source Ideas

`browser-testing-with-devtools`, frontend verification practices.

## Process

1. Identify the page, route, or component affected.
2. Start or locate the dev server when needed.
3. Open the target in a browser-capable tool.
4. Check console errors, network behavior, visible state, and responsive layout.
5. Record screenshots or observations in `06-verification.md` when useful.

## Anti-Patterns And Alternatives

| Anti-Pattern | Use Instead |
|---|---|
| Assuming UI works because build passes | Open it and inspect behavior |
| Checking only desktop | Check the relevant responsive sizes |
| Ignoring console/network errors | Record and fix or explain them |

## Self-Check

- [ ] Real browser/runtime was used when needed
- [ ] Console and network were checked
- [ ] Visual or interaction result was recorded
