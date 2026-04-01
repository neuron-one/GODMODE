---
name: deploy
description: Application deployment strategies. Zero-downtime deploy, rollback procedures, database migrations during deploy. Don't use for initial server setup.
disable-model-invocation: true
model: sonnet
effort: medium
allowed-tools: Read, Bash, Grep
---

# Deployment

## Zero-Downtime Deploy
1. Build new version
2. Run database migrations (backward-compatible)
3. Deploy new containers alongside old
4. Health check new containers
5. Switch traffic to new containers
6. Remove old containers

## Rollback Procedure
1. Stop new containers
2. Revert to previous image tag
3. Run rollback migration if needed
4. Verify health
5. Post-mortem

## Pre-Deploy Checklist
- [ ] All tests passing
- [ ] Security scan clean
- [ ] Database migration tested
- [ ] Environment variables verified
- [ ] Backup taken
- [ ] Team notified