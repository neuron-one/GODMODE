---
name: python
description: Python development with FastAPI, data processing, audio analysis with librosa. Type hints, async patterns, Pydantic models. Don't use for JavaScript/TypeScript code.
model: sonnet
effort: medium
allowed-tools: Read, Write, Edit, Bash, Grep, Glob
paths: "**/*.py,**/requirements.txt,**/pyproject.toml"
---

# Python Development

## FastAPI Patterns
- Pydantic models for all request/response
- Dependency injection for services
- Async/await for all I/O operations
- Background tasks for heavy processing
- Proper error handling with HTTPException

## Type Hints
- Required for all function signatures
- Use Optional[] for nullable params
- Use Union[] for multiple types
- Generic types for collections

## Data Processing
- pandas for structured data
- numpy for numerical operations
- asyncio for concurrent I/O
- ThreadPoolExecutor for CPU-bound tasks

## Audio (librosa)
- BPM detection: librosa.beat.beat_track
- Key detection: librosa.feature.chroma_cqt
- Energy: librosa.feature.rms
- Spectral features: centroid, bandwidth, rolloff

## Project Structure
```
project/
  ├── app/
  │   ├── main.py
  │   ├── models/
  │   ├── services/
  │   └── routes/
  ├── tests/
  ├── requirements.txt
  └── pyproject.toml
```