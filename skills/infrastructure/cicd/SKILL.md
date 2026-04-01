---
name: cicd
description: CI/CD pipeline with GitHub Actions. Automated testing, building, deployment. PR checks, auto-merge, release workflow. Don't use for Jenkins or GitLab CI.
model: sonnet
effort: medium
allowed-tools: Read, Write, Edit, Bash, Grep
paths: ".github/**/*.yml"
---

# CI/CD with GitHub Actions

## PR Pipeline
1. Lint check
2. Type check (TypeScript)
3. Unit tests
4. Build verification
5. Security scan (optional)

## Deploy Pipeline
1. Build Docker image
2. Push to registry
3. Deploy to server (SSH or webhook)
4. Health check verification
5. Rollback on failure

## Branch Strategy
- main: production, protected
- develop: staging
- feature/*: development branches
- hotfix/*: urgent fixes