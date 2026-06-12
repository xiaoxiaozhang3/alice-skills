---
name: security-review
description: Use when changes touch authentication, authorization, user input, secrets, storage, permissions, external integrations, or trust boundaries.
---

# Security Review

## Purpose

Check whether the implementation matches intended permissions and handles untrusted data safely.

## Source Ideas

`security-and-hardening`, `intended-vs-implemented`.

## Review Checklist

- [ ] Authenticated vs unauthenticated paths are explicit
- [ ] Authorization checks match documented intent
- [ ] User input is validated at trust boundaries
- [ ] Secrets are not logged, committed, or exposed to clients
- [ ] Data access is scoped to the correct user/tenant
- [ ] External calls handle failure and timeouts
- [ ] Error messages do not leak sensitive details

## Decision Tree

```text
Does this change cross a trust boundary?
  yes -> require explicit validation and auth notes
  no -> continue

Does documented intent differ from implementation?
  yes -> flag as finding
  no -> record evidence
```

## Self-Check

- [ ] Reviewed intended behavior, not only code syntax
- [ ] Checked default deny vs default allow
- [ ] Recorded residual risks
