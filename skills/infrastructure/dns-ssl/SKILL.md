---
name: dns-ssl
description: DNS configuration and SSL certificates. Domain setup, Cloudflare CDN, Let's Encrypt, HTTPS enforcement. Don't use for application-level security.
model: sonnet
effort: low
allowed-tools: Read, Write, Bash
---

# DNS & SSL Setup

## Domain Configuration
- A record -> server IP
- CNAME for www -> root domain
- MX records for email
- TXT for SPF/DKIM/DMARC

## Cloudflare Setup
- Proxy enabled (orange cloud)
- SSL mode: Full (Strict)
- Always Use HTTPS: On
- Minimum TLS: 1.2
- HSTS enabled

## SSL with Let's Encrypt
- Certbot for automated renewal
- Auto-renew cron (monthly)
- Test renewal: certbot renew --dry-run