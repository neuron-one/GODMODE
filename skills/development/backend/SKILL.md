---
name: backend
description: NestJS and Node.js backend development. REST APIs, middleware, guards, DTOs, database integration. Don't use for Python backends or frontend code.
model: sonnet
effort: medium
allowed-tools: Read, Write, Edit, Bash, Grep, Glob
paths: "src/**/*.ts,**/*.controller.ts,**/*.service.ts,**/*.module.ts"
---

# Backend Development

## NestJS Patterns
- Module-based architecture
- Dependency injection for all services
- DTOs with class-validator for input validation
- Guards for authentication/authorization
- Interceptors for logging/transformation
- Exception filters for consistent error responses

## API Design
- RESTful naming: plural nouns, HTTP verbs
- Consistent response format: { data, meta, errors }
- Pagination for list endpoints
- Proper HTTP status codes (201 created, 204 no content)
- API versioning: /api/v1/

## Database
- Repository pattern for data access
- Migrations for schema changes (never manual)
- Indexes on frequently queried columns
- Transactions for multi-table operations

## Security
- Input validation on EVERY endpoint
- Rate limiting on sensitive endpoints
- CORS configuration (specific origins)
- Helmet for security headers
- Never trust client-side data

## Error Handling
- Custom exception classes
- Consistent error format across API
- Log errors with context (request ID, user)
- Don't expose internal errors to client