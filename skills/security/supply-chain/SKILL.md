---
name: supply-chain
description: Checks npm/pip dependencies for known vulnerabilities, typosquatting, and malicious packages. Use before adding new dependencies or during security audits. Don't use for runtime monitoring.
context: fork
model: sonnet
effort: medium
allowed-tools: Read, Bash, Grep, Glob
---

# Supply Chain Security Check

## 1. Audit Existing Dependencies
```bash
npm audit          # Node.js
pip audit          # Python (pip-audit)
```

## 2. Check New Package Before Installing
- Verify package name (typosquatting: lodash vs 1odash)
- Check npm/PyPI page: downloads, maintainers, last update
- Check GitHub: stars, issues, last commit
- Verify no postinstall scripts doing suspicious things

## 3. Lockfile Integrity
- package-lock.json / yarn.lock exists and committed
- No unexpected changes in lockfile
- Integrity hashes present

## 4. Dependency Health
- No deprecated packages
- No packages with known CVEs
- No unmaintained packages (>1 year no updates)
- Minimal dependency tree (avoid mega-dependencies)

## Output
```
DEPENDENCIES SCANNED: N
VULNERABILITIES: N (critical/high/medium/low)

[For each issue]
PACKAGE: name@version
SEVERITY: critical/high/medium/low
CVE: if applicable
ISSUE: Description
FIX: upgrade to version X / replace with Y
```