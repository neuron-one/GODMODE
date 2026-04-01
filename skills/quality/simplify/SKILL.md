---
name: simplify
description: Reviews recently changed code for reuse, quality, and efficiency. Spawns 3 parallel review agents, aggregates findings, applies fixes. Official Anthropic skill. Use after completing any coding task.
context: fork
model: sonnet
effort: medium
allowed-tools: Read, Edit, Write, Grep, Glob, Bash, Agent
argument-hint: [focus-area]
---

# Simplify Code

Review recently changed files for:

## 1. Code Reuse
- Duplicated logic that should be extracted
- Existing utilities that could be used instead
- Patterns that should be consistent

## 2. Quality
- Unclear variable/function names
- Complex logic that could be simplified
- Missing error handling at boundaries
- Inconsistent patterns

## 3. Efficiency
- Unnecessary computations
- Redundant database queries
- Unused imports and variables
- Over-engineered solutions

## Process:
1. Identify recently changed files (git diff)
2. Review each file for the 3 categories above
3. Apply fixes directly
4. Verify fixes don't break tests

Optional focus: $ARGUMENTS (e.g., "focus on memory efficiency")