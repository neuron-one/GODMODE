---
name: secrets-guard
description: Finds exposed secrets, API keys, tokens, and credentials in codebase. Checks .env files, git history, hardcoded values. Don't use for runtime security monitoring.
context: fork
model: sonnet
effort: medium
allowed-tools: Read, Grep, Glob, Bash
---

# Secrets Guard

Scan for exposed secrets:

## 1. Hardcoded Secrets in Code
Search for patterns:
- API keys: `[A-Za-z0-9_-]{20,}`
- JWT secrets: `secret`, `jwt_secret`, `TOKEN`
- Database URLs with passwords
- AWS keys: `AKIA[0-9A-Z]{16}`
- Private keys: `-----BEGIN.*PRIVATE KEY-----`

## 2. Environment Files
- .env committed to git (should be in .gitignore)
- .env.example containing real values
- docker-compose.yml with hardcoded passwords

## 3. Git History
- `git log --all -p | grep -i "password\|secret\|api_key\|token"`
- Previously committed then removed secrets (still in history)

## 4. Configuration Files
- config.json/yaml with credentials
- CI/CD configs with exposed secrets
- Dockerfile with ARG containing secrets

## Output
```
SECRETS FOUND: N

[For each]
TYPE: api-key/password/token/private-key
FILE: path:line
VALUE: [first 4 chars]****[last 2 chars]
RISK: What could be compromised
FIX: How to rotate and secure
```