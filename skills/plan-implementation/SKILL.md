---
name: plan-implementation
description: Use when an approved spec or clear requirement needs ordered, executable implementation tasks before code changes.
---

# Plan Implementation

## Purpose

Turn an approved design into small tasks with file boundaries, verification, and checkpoints.

## Source Ideas

Superpowers `writing-plans`, `planning-and-task-breakdown`, `to-issues`, spec-kit tasks.

## Process

1. Read `02-design.md` and project context.
2. Map files to responsibilities.
3. Split work into ordered tasks.
4. For each task, list read files, write files, and verification.
5. Write `03-plan.md` and `04-tasks.md`.
6. Update `05-progress.md`.

## Schema-First API Gate

If frontend-backend data exchange is touched, plan tasks in this order:

1. Define schema/domain model
2. Define request/response/error contract
3. Define shared types or mapping
4. Add contract fixture/test
5. Implement backend logic
6. Implement frontend integration
7. Verify end-to-end contract

## Self-Check

- [ ] Every requirement has a task
- [ ] Every task has verification
- [ ] File boundaries are explicit
- [ ] API/data contracts precede logic when applicable
