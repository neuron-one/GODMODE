---
name: batch
description: Orchestrates large-scale code changes in parallel. Decomposes work into 5-30 independent units, each agent in isolated git worktree with tests and PR. Use for migrations, refactoring across many files. Don't use for single-file changes.
disable-model-invocation: true
model: opus
effort: high
allowed-tools: Read, Write, Edit, Bash, Grep, Glob, Agent
argument-hint: <instruction>
---

# Batch Parallel Changes

Orchestrate large-scale codebase changes: $ARGUMENTS

## Process:
1. Research the codebase to understand scope
2. Decompose work into 5-30 independent units
3. Present plan for approval
4. Spawn one agent per unit in isolated git worktree
5. Each agent: implements changes, runs tests, opens PR
6. Aggregate results and report

## Requirements:
- Must be in a git repository
- Each unit must be independent (no cross-dependencies)
- Tests must exist or be created for verification

## Example usage:
- /batch migrate src/ from Solid to React
- /batch update all API endpoints to v2
- /batch add TypeScript types to all .js files