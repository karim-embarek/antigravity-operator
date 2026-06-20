---
name: zero-to-saas-architect
description: An expert SaaS architect. Takes a basic 1-sentence idea and generates a comprehensive, production-ready SaaS architecture plan including database schema, auth, monetization, and infrastructure.
---

# Zero-to-SaaS Architect Workflow

## When to Use
Trigger this skill whenever the user asks to "build a SaaS", "design an app", "create an architecture for my idea", or when starting a completely new project from scratch.

## Prerequisites
- Ask the user for their business idea, target audience, and any specific technology constraints.

## Workflow

1. **Requirement Analysis**:
   - Extract the core value proposition.
   - Identify the primary target audience (B2B vs B2C).
   - Identify multi-tenancy requirements (Does the app need workspaces/organizations?).

2. **Technology Stack Selection**:
   - Default to a modern, highly scalable stack (e.g., Next.js App Router, Supabase/PostgreSQL, Stripe, TailwindCSS).
   - If a backend framework is needed, default to NestJS or Go.
   - Only deviate if the user explicitly requests specific technologies.

3. **Architecture Blueprint Generation**:
   You MUST generate a highly detailed Markdown document (Artifact) covering:
   - **System Architecture**: Create a `mermaid` diagram showing the flow between the frontend, backend, database, and third-party APIs.
   - **Data Model (Prisma/SQL)**: Define the core tables, relationships, and user roles (Tenant, Admin, User). Include Row Level Security (RLS) considerations if using Supabase.
   - **Authentication & Security**: How users sign up, JWT/Session handling, OAuth providers, and basic compliance checks.
   - **Monetization Strategy**: Define subscription tiers, usage-based billing logic, and Stripe webhook handling workflows.
   - **Infrastructure & Deployment**: Vercel/Docker setup, CI/CD pipelines, and VPS staging environments.

4. **SEO & UX Foundation**:
   - Outline the SEO strategy (Dynamic sitemaps, per-page generateMetadata, canonicals).
   - Define the UX/UI design system (e.g., "Neo-SaaS design language, glassmorphism, modern typography").

## Verification
- You MUST ensure the final output is formatted as a beautiful, professional Markdown report using clear headings and GitHub alerts (`> [!TIP]`, `> [!IMPORTANT]`).
- Do NOT start writing the source code until the user explicitly approves this architecture blueprint. The goal of this skill is PLANNING, not coding.
