# Completion Gates

Evidence before claims.

## Completion Claim Gate

Before saying complete, fixed, passing, ready, or shipped:

- [ ] Re-read `01-requirements.md` and `03-plan.md`
- [ ] Check every relevant item in `04-tasks.md`
- [ ] Run the smallest command that proves the claim
- [ ] Record command, output summary, and result in `06-verification.md`
- [ ] Record any skipped verification or residual risk
- [ ] Update `05-progress.md` to `status: complete` only if evidence supports it

## Not Enough

- Prior test runs
- Agent reports
- Code inspection without running the relevant check
- A passing linter when build/test behavior is the claim
- Saying a test was added without red/green evidence when regression matters
