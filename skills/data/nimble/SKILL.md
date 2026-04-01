---
name: nimble
description: Structured data extraction from multiple websites into normalized tables. Returns JSON with consistent schema across sources. Use when you need STRUCTURED data, not raw content.
disable-model-invocation: true
model: sonnet
effort: medium
allowed-tools: Read, Write, Bash, WebFetch
---

# Nimble - Structured Data Extraction

## Capabilities
- Extracts data from multiple sources simultaneously
- Normalizes data between different sites
- Returns structured JSON/CSV tables
- Handles JavaScript-rendered content

## Output Format
Always return structured table:
```json
[
  {"source": "site.com", "field1": "value", "field2": "value"},
  {"source": "other.com", "field1": "value", "field2": "value"}
]
```