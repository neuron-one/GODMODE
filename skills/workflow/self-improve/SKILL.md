---
name: self-improve
description: Audits skills, CLAUDE.md files, and conversation patterns. Finds redundancies, suggests improvements, identifies learning opportunities. Use periodically to improve GODMODE quality.
disable-model-invocation: true
context: fork
agent: Explore
model: opus
effort: high
allowed-tools: Read, Grep, Glob
---

# GODMODE Self-Improvement

## 1. Audit Skills Library
- List all installed skills with line counts
- Find overlapping scopes between skills
- Identify skills that are too verbose (>500 lines)
- Check descriptions for clarity and negative triggers
- Report unused skills (never invoked)

## 2. Audit CLAUDE.md Files
- Check for instructions duplicating Claude Code system prompts
- Find verbose phrasing that can be shortened
- Identify content that should move to skills or memory
- Check for contradictions between global and project CLAUDE.md

## 3. Session Reflection
- Review current conversation
- Analyze: what tasks took longest? Why?
- What errors occurred? What caused them?
- What could be a new skill or rule?

## 4. Present Findings
Show user:
- What to fix (with specific suggestions)
- What to add (new skills or rules)
- What to remove (redundant or outdated)
- Ask what to implement

## 5. Record
Write accepted improvements to appropriate files.