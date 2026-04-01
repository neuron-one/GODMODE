---
name: browser-testing
description: Automated browser testing and visual verification. Opens app in browser, clicks elements, verifies UI renders correctly. Use after frontend changes to verify visually.
context: fork
model: sonnet
effort: medium
allowed-tools: Read, Bash, Grep
---

# Browser Testing

## Process
1. Start dev server if not running
2. Open application in browser
3. Navigate through key pages
4. Verify elements render correctly
5. Check console for errors
6. Test interactive elements (clicks, forms)
7. Report findings

## What to Verify
- Page loads without JS errors
- All images/assets load
- Forms submit correctly
- Navigation works
- Responsive layout at different widths
- No visual regressions