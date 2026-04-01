---
name: server-setup
description: Linux server configuration. Firewall, SSH hardening, user management, system updates. Use for initial VPS setup or server hardening. Don't use for application deployment.
model: sonnet
effort: medium
allowed-tools: Read, Write, Bash, Grep
---

# Server Setup & Hardening

## Initial Setup
1. Update system packages
2. Create non-root user with sudo
3. Disable root SSH login
4. Configure SSH key authentication (disable password)
5. Change SSH port from default 22
6. Configure UFW firewall (allow only needed ports)

## Firewall Rules
- 443/tcp: HTTPS (always)
- 22/tcp or custom: SSH (your IP only)
- 80/tcp: HTTP (redirect to HTTPS)
- Block everything else by default

## Security
- Fail2ban for brute-force protection
- Automatic security updates (unattended-upgrades)
- Log rotation configured
- Swap file for memory overflow

## Monitoring
- System metrics: htop, df, free
- Log monitoring: journalctl
- Uptime monitoring: external service