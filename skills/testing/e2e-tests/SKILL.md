---
name: e2e-tests
description: End-to-end testing with Playwright or Cypress. User flows, form submissions, navigation, visual regression. Don't use for unit or API tests.
model: sonnet
effort: medium
allowed-tools: Read, Write, Edit, Bash, Grep
---

# E2E Testing

## Key User Flows to Test
- Registration -> Login -> Dashboard
- CRUD operations (create, read, update, delete)
- Payment flow (if applicable)
- Error handling (invalid input, network failure)

## Best Practices
- Test user behavior, not implementation
- Use data-testid attributes for selectors
- Clean test data before each test
- Run in CI with headless browser
- Screenshot on failure for debugging