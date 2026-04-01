---
name: auth-patterns
description: Implements secure authentication patterns. JWT with refresh tokens, OAuth 2.0, RBAC, session management. Use when building auth for any project. Don't use for social login setup.
model: opus
effort: high
allowed-tools: Read, Write, Edit, Bash, Grep
---

# Secure Authentication Patterns

## JWT Implementation
- Access token: short-lived (15 min)
- Refresh token: long-lived (7 days), stored in httpOnly cookie
- Always validate: expiry, issuer, audience
- Never store JWT in localStorage (XSS vulnerable)
- Rotate refresh tokens on each use

## Password Security
- Hash with bcrypt (cost factor 12+)
- Minimum 8 characters, require complexity
- Rate limit login attempts (5 per minute)
- Account lockout after 10 failed attempts
- Never log passwords, even hashed

## RBAC (Role-Based Access Control)
- Define roles: admin, manager, user
- Middleware checks role on EVERY protected route
- Principle of least privilege
- Separate admin endpoints from user endpoints

## Session Management
- Regenerate session ID after login
- Expire inactive sessions (30 min)
- Allow user to see/revoke active sessions
- Invalidate all sessions on password change

## API Security
- CORS: whitelist specific origins, not *
- Rate limiting per user and per IP
- Input validation with schema (Zod, Joi)
- Sanitize all outputs