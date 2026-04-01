---
name: planning
description: Creates 3 tracking files (task_plan.md, findings.md, progress.md) and continuously references them throughout execution. Eliminates drift. Use when implementing any feature requiring 3+ steps.
allowed-tools: Read, Write, Edit, Glob, Grep, Bash, Agent
argument-hint: [task-description]
model: sonnet
effort: medium
---

# GODMODE Planning with Files

Task: $ARGUMENTS

## Step 1: Create tracking files

Create these 3 files in project's .claude/ directory:

### task_plan.md
```
# Task Plan
## Goal: [one sentence]
## Steps:
1. [ ] Step description
2. [ ] Step description
...
## Dependencies: [what must exist before starting]
## Success criteria: [how to verify done]
```

### findings.md
```
# Findings
## Discovered during execution:
- [timestamp] Finding description
```

### progress.md
```
# Progress
## Completed:
- [timestamp] What was done
## Current: What's being worked on
## Blocked: Any blockers
## Next: What's coming
```

## Step 2: Execute with continuous reference

During execution:
1. Before EACH step -> re-read task_plan.md to stay on track
2. After EACH step -> update progress.md
3. When discovering anything new -> add to findings.md
4. When completing a step -> check off in task_plan.md

## Step 3: Completion

When all steps done:
1. Final update to all 3 files
2. Verify ALL success criteria met
3. Report summary to user

## Rules:
- NEVER skip re-reading task_plan.md between steps
- findings.md captures ANYTHING unexpected
- progress.md always reflects CURRENT state
- If plan needs changing -> update task_plan.md FIRST, then continue