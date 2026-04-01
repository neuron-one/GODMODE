---
name: gemini-mcp
description: Delegates text tasks to Google Gemini through MCP (gemini/gemini-reply). Use for architecture disputes, design critique, second opinions. Don't use for media — use gemini-media for images/video.
disable-model-invocation: true
model: sonnet
effort: medium
---

# Gemini MCP Integration

## Two Gemini Servers

### `gemini` (Text — Delegator Bridge)
- Tools: `mcp__gemini__gemini`, `mcp__gemini__gemini-reply`
- Use for: architecture disputes, code review, design critique, text consultations
- Powered by: Gemini CLI → Gemini 2.5 Flash/Pro
- Supports: multi-turn (threadId), developer-instructions, sandbox modes

### `gemini-media` (Media — @fre4x/gemini)
- Tools: `mcp__gemini-media__analyze_media`, `mcp__gemini-media__generate_image`, `mcp__gemini-media__generate_video`
- Use for: image analysis, image generation (Imagen), video generation (Veo)
- Powered by: Gemini API directly

## When to Use Gemini (Text)
- As independent expert in /dispute (full text architecture/design reviews)
- Design and visual critique (describe, don't just send image)
- Second opinion on Claude's decisions
- Tasks where Google ecosystem knowledge helps

## When to Use Gemini-Media
- Analyze screenshots, diagrams, photos
- Generate images (Imagen)
- Generate videos (Veo)

## Rules
- Include full context (Gemini doesn't see our conversation)
- Specify output format expected
- Compare with Claude's own analysis
- Note: data sent to Google servers
