# SaaS Architectural Blueprint

## 1. Product Vision
- **Idea:** [User's idea]
- **Target Audience:** [Who is this for]

## 2. Recommended Tech Stack
- **Frontend:** Next.js (App Router), TailwindCSS
- **Backend:** [e.g., Next.js API Routes or NestJS]
- **Database:** PostgreSQL (via Prisma ORM or Supabase)
- **Auth:** [e.g., Supabase Auth / NextAuth]
- **Payments:** Stripe Checkout

## 3. Core Database Schema
```prisma
// Agent: Write the 3-4 most critical Prisma models here
model User {
  id    String @id @default(cuid())
  email String @unique
  // ...
}
```

## 4. MVP Features (Phase 1)
- [ ] Feature 1
- [ ] Feature 2
- [ ] Feature 3

## 5. Monetization Strategy
- **Pricing Model:** [e.g., Freemium, $15/mo Pro tier]
- **Value Metric:** [e.g., Number of pets, API calls]
