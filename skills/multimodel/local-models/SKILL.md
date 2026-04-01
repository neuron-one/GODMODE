---
name: local-models
description: Running AI models locally with Ollama and llama.cpp. Free inference, privacy, custom model deployment. Use for cost-free routine tasks or private data processing. Don't use when quality of Opus is needed.
disable-model-invocation: true
model: sonnet
effort: medium
allowed-tools: Read, Write, Bash
---

# Local Model Deployment

## Ollama Setup
```bash
# Install model
ollama pull qwen2.5:7b

# Run
ollama run qwen2.5:7b

# API endpoint
curl http://localhost:11434/api/generate
```

## llama.cpp (for Claude Code integration)
```bash
# Start server
llama-server --model model.gguf --port 8001

# Point Claude Code to local
ANTHROPIC_BASE_URL=http://localhost:8001
```

## Model Selection
- Routine tasks: Qwen 3B (fast, light)
- Code generation: Qwen 7B or CodeLlama 7B
- Reasoning: Qwen 27B (heavy but capable)

## When to Use Local vs Cloud
- Private data processing -> local
- Cost-free batch operations -> local
- Complex reasoning -> cloud (Opus)
- Critical decisions -> cloud (Opus)