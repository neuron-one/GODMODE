---
name: monitoring
description: Application and server monitoring. Error tracking, log aggregation, alerting, uptime monitoring. Use for production setup. Don't use for development debugging.
model: sonnet
effort: medium
allowed-tools: Read, Write, Edit, Bash, Grep
---

# Production Monitoring

## Error Tracking
- Sentry for application errors
- Structured logging (JSON format)
- Error grouping by root cause
- Alert on new error types

## Metrics
- Response time (p50, p95, p99)
- Error rate (4xx, 5xx)
- Throughput (requests/sec)
- CPU/Memory/Disk usage

## Alerting Rules
- S1 (Critical): service down, data loss -> immediate
- S2 (High): error rate >5%, response >2s -> 15 min
- S3 (Medium): error rate >1%, disk >80% -> 1 hour
- S4 (Low): deprecation warnings -> daily

## Health Checks
- /health endpoint on every service
- Database connectivity check
- External dependency checks
- Synthetic monitoring (periodic requests)