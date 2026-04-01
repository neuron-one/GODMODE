---
name: llm-council
description: Multi-model planning committee. Up to 4 models create plans independently, then an anonymous judge selects the best or combines the best parts. Use for major architectural decisions.
disable-model-invocation: true
model: opus
effort: high
---

# LLM Council - Multi-Model Planning

## Process
1. Define the planning task clearly
2. Send to 2-4 different models in parallel
3. Each creates an independent plan
4. Anonymize all plans (remove model names)
5. Judge evaluates each plan on merits
6. Judge selects best plan OR combines best elements
7. Present final plan with reasoning

## Judging Criteria
- Feasibility (can it actually be built?)
- Completeness (are all requirements covered?)
- Elegance (is it the simplest solution?)
- Scalability (will it work at 10x scale?)
- Security (are risks addressed?)

## Rules
- Plans MUST be anonymized before judging
- Judge evaluates purely on quality, not model reputation
- Dissenting opinions are valuable — document them