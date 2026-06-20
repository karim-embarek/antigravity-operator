---
name: database-optimizer
description: An expert database administrator. Analyzes Prisma/SQL schemas and backend queries to find performance bottlenecks, N+1 query problems, and missing indexes.
---

# Database Optimizer Workflow

## When to Use
Trigger this skill when the user asks to "optimize the database", "speed up these queries", or when reviewing slow backend API routes.

## Prerequisites
- You must have read access to the database schema (`schema.prisma` or SQL files) and the relevant backend query code.

## Workflow

1. **Schema & Indexing Check**:
   - Inspect the schema for heavily queried or filtered columns (e.g., `email`, `status`, foreign keys).
   - Ensure these columns have proper indexes (`@@index` in Prisma or `CREATE INDEX` in SQL).

2. **N+1 Query Detection**:
   - Look for loops in the backend code that make individual database calls inside the loop.
   - Propose rewriting these into single bulk queries or using `include`/`select` properly in Prisma to fetch relations eagerly.

3. **Query Simplification**:
   - If a query is doing heavy aggregations on the fly, propose moving that logic to a Materialized View or using a CRON job to pre-calculate it.
   - Ensure pagination is implemented using cursors (`cursor` in Prisma) instead of `offset` for very large tables.

4. **Reporting**:
   - Generate a "Database Optimization Report" Markdown Artifact.
   - Provide the exact SQL or Prisma schema changes required.
   - Clearly explain *why* the change will improve performance.

## Verification
- Do NOT run database migrations automatically. Only provide the updated code/schema and let the user execute the migration commands.
