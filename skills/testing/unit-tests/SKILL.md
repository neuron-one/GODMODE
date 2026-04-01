---
name: unit-tests
description: Unit test writing with Jest (JS/TS) or pytest (Python). Test structure, mocking, edge cases, coverage. Don't use for E2E or integration tests.
model: sonnet
effort: medium
allowed-tools: Read, Write, Edit, Bash, Grep
paths: "**/*.test.ts,**/*.test.tsx,**/*.spec.ts,**/test_*.py,**/*_test.py"
---

# Unit Testing

## Structure (Arrange-Act-Assert)
```
describe('ServiceName', () => {
  it('should [expected behavior] when [condition]', () => {
    // Arrange: setup
    // Act: call function
    // Assert: verify result
  });
});
```

## What to Test
- Happy path (normal operation)
- Edge cases (empty, null, boundary values)
- Error cases (invalid input, network failure)
- Business logic (calculations, transformations)

## Mocking
- Mock external dependencies (DB, API, filesystem)
- Never mock the thing you're testing
- Use dependency injection for testability

## Coverage Target
- New code: 80%+ line coverage
- Critical paths: 100%