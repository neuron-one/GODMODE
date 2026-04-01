---
name: cost-estimate
description: Estimates project cost at market rates. Scans codebase, counts APIs, integrations, and complexity. Shows what the project would cost without AI. Use for pitches and ROI demonstrations.
disable-model-invocation: true
context: fork
agent: Explore
model: sonnet
effort: medium
allowed-tools: Read, Grep, Glob
---

# Project Cost Estimation

Scan the codebase and estimate development cost at market rates:

## Analyze
1. Count lines of code by language
2. Identify frameworks and libraries used
3. Count API endpoints
4. Count database tables/models
5. Identify external integrations
6. Assess UI complexity (screens, components)

## Calculate
- Junior developer: $30-50/hr
- Senior developer: $80-150/hr
- Estimated hours per component
- Total cost range (min-max)
- Estimated timeline with team of 3

## Output
```
PROJECT: [name]
TOTAL LINES: N
LANGUAGES: [list]
COMPLEXITY: low/medium/high

ESTIMATED COST (without AI): $X - $Y
ESTIMATED TIME (team of 3): X-Y months
ACTUAL TIME (with GODMODE): X days/weeks

ROI: [percentage savings]
```