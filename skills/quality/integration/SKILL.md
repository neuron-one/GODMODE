---
name: integration
description: Verifies that separate code parts work together. Checks imports, API contracts, shared types, data flow between components. Use after multiple agents completed parallel tasks.
context: fork
model: opus
effort: high
allowed-tools: Read, Grep, Glob, Bash
---

# Integration Check

Verify that all parts work together:

## 1. Import Verification
- All imports resolve to existing files
- No circular dependencies
- Shared types match between producer and consumer

## 2. API Contract Check
- Frontend calls match backend endpoint signatures
- Request/response types are consistent
- Error codes handled on both sides
- Auth tokens passed correctly

## 3. Data Flow
- Database schema matches model definitions
- Required fields are always populated
- Foreign keys reference existing records
- Enum values consistent across layers

## 4. Configuration
- Environment variables referenced but not defined
- Port numbers match between services
- URLs and paths are consistent

## 5. Run Verification
- Attempt to build/compile the project
- Run existing tests
- Check for TypeScript/linting errors

## Output
```
INTEGRATION STATUS: pass/fail
ISSUES FOUND: N

[For each issue]
TYPE: import/api/data/config
FILES: file1.ts <-> file2.ts
ISSUE: Description
FIX: How to resolve
```