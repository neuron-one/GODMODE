---
name: graphiti
description: Temporal knowledge graph for long-term memory. Facts have timestamps and expiry. Tracks how decisions evolve over time across projects. Use for Stage 3 deep memory. Don't use for simple key-value storage.
disable-model-invocation: true
model: opus
effort: high
allowed-tools: Read, Write, Bash
---

# Graphiti — Temporal Knowledge Graph

## What It Is
Knowledge graph where every fact has a TIME dimension:
- When was this decided?
- Is it still current?
- What replaced it?

## When to Deploy (Stage 3 Memory)
Deploy when GODMODE has 10+ projects and file-based memory is insufficient.

## Architecture
```
Episode → extracted entities + relationships → stored in graph
Each fact: subject → predicate → object + valid_from + valid_to
```

## Example
```
"MUNO uses PostgreSQL" (valid_from: Jan 2025, valid_to: current)
"MUNO considered MongoDB" (valid_from: Oct 2025, valid_to: Oct 2025, status: rejected)
"GODMODE uses Adaptive Swarm" (valid_from: Mar 2026, valid_to: current)
```

## Reference: https://github.com/getzep/graphiti
## Replaces: Cognee (no temporal awareness)