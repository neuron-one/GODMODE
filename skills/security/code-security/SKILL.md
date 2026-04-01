---
name: code-security
description: Security audit for application code. Scans for OWASP Top 10, authentication flaws, data exposure, injection attacks. Don't use for infrastructure or network security.
context: fork
model: opus
effort: high
allowed-tools: Read, Grep, Glob, Bash
---

# Code Security Audit

Scan codebase for security vulnerabilities:

## 1. Injection Attacks
- SQL injection in raw queries
- NoSQL injection in MongoDB queries
- Command injection in exec/spawn calls
- LDAP injection
- XPath injection

## 2. Authentication & Authorization
- Missing auth middleware on protected routes
- JWT without expiry validation
- Hardcoded secrets in code
- Weak password requirements
- Missing rate limiting on auth endpoints
- Session fixation vulnerabilities

## 3. Data Exposure
- Sensitive data in logs (passwords, tokens, PII)
- Verbose error messages exposing internals
- API responses including unnecessary fields
- Secrets in git history
- .env files not in .gitignore

## 4. Cross-Site Attacks
- XSS via unescaped user input
- Missing Content-Security-Policy headers
- CSRF without token validation
- Clickjacking without X-Frame-Options

## 5. Insecure Configuration
- Debug mode enabled
- CORS allowing all origins
- HTTP instead of HTTPS
- Default credentials
- Missing security headers

## Output
For each vulnerability:
```
SEVERITY: critical/high/medium/low
OWASP: category (e.g., A01:2021 Broken Access Control)
FILE: path:line
VULNERABILITY: Description
EXPLOIT: How it could be exploited
FIX: Specific remediation
```

Mark every vulnerability with WARNING comment in code.