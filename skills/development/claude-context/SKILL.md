---
name: claude-context
description: Semantic code search via MCP. Indexes entire codebase, finds relevant code by natural language query. 40% token savings. Use for large codebases (10K+ lines). Don't use for small projects.
user-invocable: false
model: sonnet
effort: low
---

# Claude Context — Semantic Code Search

## What It Is
MCP plugin that indexes your codebase and enables natural language search.
Instead of loading entire files → search and load only relevant parts.

## When to Use
- Codebase > 10K lines
- Need to find code by description, not filename
- Want to reduce token usage by loading only relevant code

## Setup
```bash
# Install as MCP
claude mcp add claude-context -- npx @anthropic-ai/claude-context
```

## Reference: https://github.com/zilliztech/claude-context