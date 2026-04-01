---
name: react-doctor
description: Scans React code for anti-patterns. Finds unnecessary useEffect, prop drilling, accessibility issues. Run repeatedly until all issues pass. Don't use for non-React code.
disable-model-invocation: true
context: fork
model: sonnet
effort: medium
allowed-tools: Bash, Read, Grep
paths: "**/*.tsx,**/*.jsx"
argument-hint: [path-to-scan]
---

# React Doctor

Scan React code for anti-patterns:

```bash
npx -y react-doctor@latest $ARGUMENTS
```

## What it checks:
- Unnecessary useEffect hooks
- Prop drilling (should use Context or composition)
- Accessibility (a11y) violations
- Component complexity

## Process:
1. Run scan on specified path
2. Report all findings
3. Fix issues found
4. Run again to verify fixes
5. Repeat until clean