---
name: git-guardrails
description: Soft rules for Claude to avoid dangerous git commands (force-push, hard reset, branch -D). Always-active behavioral guardrail. Don't use for hook setup — use git-guardrails-external instead.
user-invocable: false
model: sonnet
effort: low
---

# Git Guardrails

BLOCK these git commands and suggest safe alternatives:

## Blocked Commands
- `git push --force` -> Use `git push --force-with-lease` instead
- `git reset --hard` -> Use `git stash` or `git reset --soft` instead
- `git clean -f` / `git clean -fd` -> List files first with `git clean -n`
- `git branch -D` -> Use `git branch -d` (safe delete) instead
- `git checkout .` / `git restore .` -> Restore specific files instead
- `git rebase` on shared branches -> Merge instead

## Always Before Destructive Operations
1. Check if there are uncommitted changes: `git status`
2. Create a backup branch: `git branch backup-[date]`
3. Confirm with user before proceeding

## Never
- Skip hooks with --no-verify
- Force push to main/master
- Delete branches that have unmerged changes
- Amend published commits