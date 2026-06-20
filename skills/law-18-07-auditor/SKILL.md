---
name: law-18-07-auditor
description: A strict legal auditor for the Algerian Law 18-07 on personal data protection. Ensures data localization and sovereign compliance.
---

# Algerian Law 18-07 Compliance Auditor

## When to Use
Trigger this skill when the user asks to "check Algerian compliance", "audit Law 18-07", or when deploying an application targeting the Algerian market.

## Prerequisites
- You must have read access to the infrastructure configuration (e.g., Vercel, AWS, local VPS scripts) and database schemas.

## Workflow

1. **Data Localization (Sovereignty) Check**:
   - **CRITICAL**: Article 43 of Law 18-07 mandates that personal data must be hosted in Algeria unless explicit authorization is granted by the ANPDP (Autorité Nationale de Protection des Données à Caractère Personnel).
   - Check the deployment targets. If deploying to AWS, Vercel, or DigitalOcean (outside Algeria), generate a `> [!CAUTION]` warning that data localization is violated. Recommend Algerian cloud providers (Icosnet, Djezzy, local VPS).

2. **ANPDP Declaration Check**:
   - Ensure the architecture includes a privacy policy page that explicitly mentions the declaration made to the ANPDP.
   - Check for explicit consent banners tailored to Algerian users.

3. **Data Encryption & Security**:
   - Verify that passwords and national identification numbers (NIN) are strongly hashed and encrypted.
   - Ensure the system prevents unauthorized cross-border data transfers via third-party APIs (e.g., sending user emails directly to unauthorized foreign SaaS tools without consent).

4. **Reporting**:
   - Generate an "Audit Loi 18-07" Markdown Artifact.
   - Highlight any sovereign hosting violations.
   - Provide recommendations for local VPS deployment (e.g., Docker Compose on an Algerian host).

## Verification
- Do not deploy the code if a major sovereignty violation is detected without explicitly warning the user first.
