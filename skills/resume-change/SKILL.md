---
name: resume-change
description: Use when continuing, resuming, picking up, or recovering an interrupted task or change.
---

# Resume Change

## Purpose

Resume from durable files instead of guessing from conversation memory.

## Source Ideas

OpenSpec change folders, flow-kit progress/SUMMARY pattern, handoff patterns.

## Process

1. Identify the target change folder. If not specified, choose the most recent relevant folder.
2. Read `05-progress.md`.
3. Read `04-tasks.md`.
4. Read the phase file for `current_phase`.
5. State the current step and next action.
6. Continue only from the recorded next action.

## Decision Tree

```text
Progress file missing?
  yes -> inspect change files and reconstruct minimal progress, then ask if uncertain
  no -> continue from progress

Status blocked?
  yes -> address blocker or ask user
  no -> execute next action
```

## Self-Check

- [ ] Did not restart from scratch
- [ ] Did not rely only on chat history
- [ ] Read progress and task checklist
- [ ] Updated progress after continuing
