# Database Optimization Report

## 1. Schema Analysis (Indexes)
- [ ] Are Foreign Keys indexed? (Prisma does not index foreign keys by default).
- [ ] Are search fields indexed? (e.g., `@@index([email])`)
**Findings:** [Agent to report missing indexes here]

## 2. Query Analysis (N+1 Problems)
- [ ] Are we fetching relations inside a loop?
- [ ] Should we use `include` or a `join` instead?
**Findings:** [Agent to report N+1 risks here]

## 3. Data Types
- [ ] Are we using `String` for UUIDs or CUIDs?
- [ ] Are Enums used properly instead of loose strings?
