---
name: database
description: PostgreSQL and MongoDB database design. Schema design, migrations, indexing, query optimization, RLS security policies. Don't use for application logic or API development.
model: sonnet
effort: medium
allowed-tools: Read, Write, Edit, Bash, Grep
---

# Database Development

## PostgreSQL
- Normalized schema (3NF minimum)
- UUID primary keys for distributed systems
- Created_at/updated_at timestamps on all tables
- Foreign key constraints with ON DELETE behavior
- Check constraints for data integrity

## Indexing
- B-tree for equality and range queries
- GIN for full-text search and JSONB
- Partial indexes for filtered queries
- Composite indexes: most selective column first
- EXPLAIN ANALYZE before and after

## Migrations
- Sequential numbered migrations
- Always include rollback (down migration)
- Never modify existing migration
- Test migration on copy of production data

## MongoDB
- Schema design by access patterns (not normalization)
- Embedding for 1:few relationships
- References for 1:many or many:many
- Compound indexes matching query patterns

## Query Optimization
- Avoid N+1: use JOINs or eager loading
- Pagination with cursor, not OFFSET
- Connection pooling (PgBouncer)
- Read replicas for heavy read workloads