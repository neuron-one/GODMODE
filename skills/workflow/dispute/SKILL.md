---
name: dispute
description: Cross-model dispute with Claude + GPT + Gemini. All three models give independent positions, then see each other's arguments and negotiate through rounds until consensus. Use for stack choices, architecture decisions, or any important technical decision.
disable-model-invocation: true
allowed-tools: AskUserQuestion, Read, Glob, Grep, Write, Agent, mcp__codex__codex, mcp__codex__codex-reply, mcp__gemini__gemini, mcp__gemini__gemini-reply
argument-hint: [topic]
model: opus
effort: high
---

# GODMODE Cross-Model Dispute

Three independent AI models debate until consensus.

Topic: $ARGUMENTS

## Participants
- **Claude** (you, the orchestrator) — Architect #1
- **GPT** (via mcp__codex__codex) — Architect #2
- **Gemini** (via mcp__gemini__gemini) — Architect #3

## Step 0: Preparation

1. Analyze the topic. Determine what context is needed (files, code, prior decisions).
2. Read relevant files if needed.
3. Formulate a clear dispute question with full context.
4. Prepare the expert prompt for GPT and Gemini — they need FULL context since they don't see our conversation.

## Step 1: Independent Positions (Round 1)

All three models give positions **independently** (no one sees others' answers yet).

**Claude**: Write your position directly in the conversation.

**GPT**: Send via mcp__codex__codex with:
- Full context of the dispute topic
- Role: "You are Architect #2 in a 3-way dispute. Give your INDEPENDENT position."
- developer-instructions: architect prompt
- sandbox: read-only

**Gemini**: Send via mcp__gemini__gemini with:
- Same full context
- Role: "You are Architect #3 in a 3-way dispute. Give your INDEPENDENT position."
- sandbox: read-only

Launch GPT and Gemini in **parallel** (same message, two tool calls).

Save all three positions. Present to user.

## Step 2: Cross-Critique (Round 2)

Each model sees ALL other positions and critiques them.

**Claude**: Read GPT's and Gemini's positions. Critique both — find at least 2 weaknesses in each.

**GPT** (via mcp__codex__codex-reply or new session): Send:
- Claude's position (full text)
- Gemini's position (full text)
- Task: "Critique both positions. Find at least 2 weaknesses in each. Defend your own where you disagree."

**Gemini** (via mcp__gemini__gemini-reply or new session): Send:
- Claude's position (full text)
- GPT's position (full text)
- Task: "Critique both positions. Find at least 2 weaknesses in each. Defend your own where you disagree."

Launch GPT and Gemini in **parallel**.

Save all critiques. Present to user.

## Step 3: Defense & Concessions (Round 3)

Each model responds to criticism and acknowledges valid points.

**Claude**: Read critiques from GPT and Gemini. Respond: what you accept, what you defend.

**GPT**: Send both critiques (from Claude and Gemini) of GPT's position.
Task: "These are critiques of YOUR position. Respond: what do you concede? What do you defend and why?"

**Gemini**: Send both critiques (from Claude and GPT) of Gemini's position.
Task: "These are critiques of YOUR position. Respond: what do you concede? What do you defend and why?"

Launch GPT and Gemini in **parallel**.

## Step 4: Consensus Check

Analyze all three Round 3 responses. Categorize:

| Category | Description |
|----------|-------------|
| **CONSENSUS** | All three agree |
| **MAJORITY** | Two agree, one disagrees |
| **OPEN** | All three still disagree |

**If no OPEN items remain** → go to Step 6 (Final Document).

**If OPEN items exist** → go to Step 5 (Negotiation).

## Step 5: Negotiation Rounds (repeat until consensus or max 2 extra rounds)

For each OPEN item:

Send to GPT and Gemini:
- Current state: who agrees on what, what's still open
- The specific point of disagreement
- Task: "Propose a compromise or explain why you cannot concede this point."

Claude also proposes compromise.

After each negotiation round, re-check consensus:
- **Resolved** → move to CONSENSUS
- **Still open after 2 extra rounds** → mark as UNRESOLVED, record all positions

Maximum total rounds: 5 (3 standard + 2 negotiation).

## Step 6: Final Document

Write a summary document with:

```markdown
# Dispute: [Topic]
Date: [date]
Participants: Claude (Opus), GPT (Codex), Gemini

## Consensus (all agree)
- [point 1]
- [point 2]

## Majority decisions (2 of 3)
- [point]: [majority position] — [dissenter] disagrees because [reason]

## Unresolved (if any)
- [point]: Claude says X, GPT says Y, Gemini says Z

## Final Recommendation
[synthesized recommendation based on consensus + majority]

## Key Arguments
[most valuable insights from each participant]
```

Present to user for final decision.
Record in project MEMORY.md.

## Rules

- All three models MUST participate. If GPT or Gemini MCP is unavailable, inform user and fall back to 2-model dispute.
- Never fake consensus — real disagreements are valuable.
- Each model gets FULL context of others' positions — no "telephone game".
- Orchestrator (Claude) must be intellectually honest — concede when GPT or Gemini make better arguments.
- GPT and Gemini prompts must include ALL relevant context (they don't see our conversation).
- Use multi-turn (threadId via *-reply) when possible to preserve context across rounds.
- Maximum 5 rounds total to avoid infinite loops.
- Present each round's results to user before proceeding to next.
