---
name: ml-training
description: Machine learning model training with HuggingFace. Fine-tuning LLMs, dataset creation, GPU selection, training monitoring. Use for training custom models. Don't use for using pre-trained models via API.
disable-model-invocation: true
model: opus
effort: high
allowed-tools: Read, Write, Edit, Bash, Grep, WebFetch
---

# ML Model Training

## Pipeline
1. Define task and success metrics
2. Collect/prepare training data
3. Choose base model (by size and task fit)
4. Select GPU and estimate cost
5. Configure training (SFT, DPO, or GRPO)
6. Monitor training run
7. Evaluate on test set
8. Deploy model

## Model Selection
- Small tasks (classification): Qwen 0.6B-3B
- Medium tasks (generation): Mistral 7B, Llama 8B
- Complex tasks (reasoning): Qwen 27B, Llama 70B

## Training Methods
- SFT: supervised fine-tuning on examples
- DPO: preference optimization (good vs bad)
- GRPO: group relative policy optimization

## Deployment
- Ollama for local inference
- LitServe for MCP server
- llama.cpp for production