---
name: adversarial-spec
description: Multiple AI models critique a spec/PRD until consensus. GPT, Gemini, Grok each find different weaknesses. Iterates until all models agree the spec is solid. Use for critical project specifications.
disable-model-invocation: true
model: opus
effort: high
---

# Adversarial Specification Review

## Process
1. Send spec to 2-3 different models simultaneously
2. Each model critiques independently
3. Claude collects all criticism
4. Claude rewrites spec addressing all points
5. Send revised spec back to models
6. Repeat until consensus

## What Models Check
- Missing requirements
- Ambiguous language
- Scope creep indicators
- Security gaps
- Performance blind spots
- Edge cases not covered

## Consensus Rules
- If a model agrees too quickly -> force it to prove it read the document
- Minimum 2 rounds of critique
- Final spec must address ALL raised issues