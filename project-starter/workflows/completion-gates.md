# Completion Gates

Current evidence must support every completion claim. Inspection and Subagent
reports can inform review, but neither substitutes for main-agent verification.

## Completion Claim Gate

Before saying complete, fixed, passing, ready, or shipped:

- [ ] Re-read the user request and applicable requirements, design, and plan.
- [ ] Confirm the requested scope and acceptance criteria are satisfied.
- [ ] Check every applicable item in `04-tasks.md` for tracked work.
- [ ] Review the final diff for scope, unrelated changes, secrets, and regressions.
- [ ] Resolve required review findings or document an explicitly accepted limitation.
- [ ] Run the smallest current command or manual check that proves the claim.
- [ ] Run main-agent final verification after integrating any Subagent batch.
- [ ] Record commands, result summaries, and evidence in `06-verification.md` for tracked work.
- [ ] Record skipped checks, limitations, and residual risk.
- [ ] Set `05-progress.md` to `complete` only when the evidence supports it.

The final report states what changed, what was verified, and any remaining
concerns. Deployment, publication, external messages, commits, and other
external actions still require the authorization defined in `AGENTS.md`.

## Not Enough

- Prior or stale test runs
- A Subagent report without main-agent review and verification
- Code inspection when the claim concerns runtime behavior
- A passing formatter or linter when build or test behavior is the claim
- A test that was not observed failing before a regression fix when red/green evidence matters
- Successful scoped checks when combined integration is the claim

If verification cannot be run, report the reason and do not overstate status.
