---
name: rgpd-auditor
description: A specialized compliance auditor. Scans architecture and code for strict adherence to the European GDPR (RGPD) regarding personal data protection.
---

# GDPR Compliance Auditor

## When to Use
Trigger this skill whenever the user asks to "check for compliance", "audit RGPD", or right before deploying databases or features that handle user personal data (PII).

## Prerequisites
- You must have read access to the database schema (e.g., `schema.prisma` or SQL files) and the authentication logic.

## Workflow

1. **Data Minimization & Encryption Check**:
   - Verify that passwords are hashed securely (e.g., using bcrypt/argon2).
   - Ensure sensitive PII (Personal Identifiable Information) like national IDs, payment info, or health data are encrypted at rest.

2. **Consent & Tracking Check**:
   - Check the frontend code for cookie banners. No third-party tracking cookies (Google Analytics, Meta Pixel) should fire before explicit, active user consent.
   - Ensure user registration forms include explicit, unticked checkboxes for marketing opt-ins.

3. **User Rights (Right to be Forgotten)**:
   - Check the backend API for account deletion endpoints.
   - Ensure that when a user requests deletion, their data is either completely hard-deleted or irreversibly anonymized (no orphaned PII left in related database tables).

4. **Reporting**:
   - Generate a strict "Compliance Audit Report" using a Markdown Artifact.
   - Use standard GitHub alerts (`> [!CAUTION]`) for critical legal violations that could result in fines.
   - Provide the exact code snippets or SQL queries needed to fix the compliance issues.

## Verification
- Do not modify the codebase. Only generate the audit report and wait for the user's explicit approval to implement the compliance fixes.
