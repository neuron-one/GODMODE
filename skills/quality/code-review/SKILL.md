---
name: code-review
description: Deep code review like a senior engineer. Checks SOLID violations, security vulnerabilities (XSS, injections, race conditions), performance issues (N+1, missing cache), error handling and edge cases. Don't use for formatting or style-only reviews.
context: fork
model: opus
effort: high
allowed-tools: Read, Grep, Glob, Bash
---

# Code Review Expert

Review the code with focus on these 4 areas:

## 1. SOLID Violations
- Single Responsibility: does each module/class do ONE thing?
- Open/Closed: can it be extended without modification?
- Liskov Substitution: are subtypes interchangeable?
- Interface Segregation: are interfaces minimal?
- Dependency Inversion: do high-level modules depend on abstractions?

## 2. Security Vulnerabilities
- XSS: unescaped user input in HTML/templates
- SQL/NoSQL Injection: unsanitized queries
- Command Injection: user input in shell commands
- Race Conditions: concurrent access without locks
- Authentication bypass: missing auth checks on endpoints
- Insecure direct object references
- Sensitive data exposure in logs/errors

## 3. Performance Issues
- N+1 queries: loops making individual DB calls
- Missing indexes on frequently queried fields
- Missing caching for expensive computations
- Unnecessary re-renders in React components
- Large payloads without pagination
- Synchronous operations that should be async

## 4. Error Handling & Edge Cases
- Missing error handling at system boundaries
- Empty arrays/null values not handled
- Network failure scenarios
- Concurrent modification scenarios
- Input validation at API boundaries

## Output Format
For each issue found:
```
SEVERITY: critical/high/medium/low
FILE: path/to/file.ts:line
ISSUE: Description of the problem
FIX: Specific suggestion to resolve
```