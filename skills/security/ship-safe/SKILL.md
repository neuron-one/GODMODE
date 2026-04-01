---
name: ship-safe
description: 16 parallel security agents scanning 80+ attack classes. Prompt injection, RAG poisoning, API key leaks, supply chain, MCP misconfigurations. Use before production deployment. Don't use for minor code changes.
disable-model-invocation: true
context: fork
model: opus
effort: max
allowed-tools: Bash, Read, Grep, Glob
---

# Ship Safe - Full Security Scan

Run comprehensive security scan:

## Attack Classes Covered:
- Prompt injection vectors
- RAG data poisoning
- Active API key/secret leaks
- Supply chain risks (dependencies)
- MCP misconfiguration
- Authentication bypasses
- Authorization flaws
- Data exposure
- Injection attacks (SQL, NoSQL, Command)
- Cross-site attacks (XSS, CSRF)

## Process:
1. Scan all source code files
2. Check all configuration files
3. Audit dependencies (npm audit / pip audit)
4. Check .env and secrets handling
5. Verify MCP configurations
6. Check authentication flows
7. Report with severity levels

## Output:
```
SCAN COMPLETE
CRITICAL: N issues
HIGH: N issues
MEDIUM: N issues
LOW: N issues

[Detailed report per issue with fix suggestions]
```