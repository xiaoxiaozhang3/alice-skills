---
name: release-check
description: Use when preparing a change for release, deployment, handoff, rollout, or production exposure.
---

# Release Check

## Purpose

Make shipping safer by checking verification, rollback, observability, and known risks.

## Source Ideas

`shipping-and-launch`, PM `pre-mortem`, Superpowers completion gate.

## Checklist

- [ ] Requirements are complete or gaps are explicit
- [ ] Verification evidence is recorded
- [ ] Migration or rollback notes exist when needed
- [ ] Monitoring/logging impact is considered
- [ ] User-facing change notes are prepared when needed
- [ ] Known risks and mitigations are listed
- [ ] Owner/next action is clear

## Pre-Mortem Questions

- What could break first?
- How would we detect it?
- How would we roll back or mitigate it?
- What user or data boundary is most sensitive?

## Self-Check

- [ ] Release decision is evidence-based
- [ ] Rollback path is clear or explicitly not needed
- [ ] Residual risk is not hidden
