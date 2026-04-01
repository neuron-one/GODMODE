---
name: adversarial-review
description: Cross-model code review. Sends code to a DIFFERENT model (GPT/Gemini) for independent review. Reviewer must be on a different model than the code author. Use for critical PRs and security-sensitive code.
disable-model-invocation: true
model: sonnet
effort: medium
---

# Adversarial Cross-Model Review

## Principle
Same model has same blind spots when writing AND reviewing.
Different model catches what the author's model missed.

## Process
1. Identify code changes for review
2. Select DIFFERENT model than what wrote the code
3. Send code + context to external model
4. Collect review findings
5. Compare with internal review
6. Address all unique findings from external model

## Rules
- Reviewer MUST be different model
- Claude wrote code -> GPT reviews (or vice versa)
- Include sufficient context for reviewer
- Don't dismiss external findings without investigation