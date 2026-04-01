---
name: docker
description: Docker and docker-compose configuration. Multi-stage builds, container orchestration, volume management, networking. Don't use for Kubernetes or cloud-native deployments.
model: sonnet
effort: medium
allowed-tools: Read, Write, Edit, Bash, Grep
paths: "**/Dockerfile,**/docker-compose*.yml,**/.dockerignore"
---

# Docker Development

## Dockerfile Best Practices
- Multi-stage builds (separate build and runtime)
- Minimal base images (alpine when possible)
- Non-root user inside container
- .dockerignore for node_modules, .git, etc
- Layer caching: COPY package*.json first, then npm install, then COPY code

## Docker Compose
- Named volumes for persistent data
- Environment variables via .env file
- Health checks for dependencies
- Restart policies (unless-stopped)
- Network isolation between services

## Common Stack
```yaml
services:
  app:          # Application
  db:           # PostgreSQL/MongoDB
  redis:        # Cache/queues
  minio:        # Object storage (dev)
```