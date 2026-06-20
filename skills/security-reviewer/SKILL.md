---
name: security-reviewer
description: Acts as a strict security auditor. Analyzes code for vulnerabilities, OWASP Top 10 flaws, and hardcoded secrets.
---

# Security Reviewer Workflow

## When to Use
Trigger this skill when the user asks you to "review code for security", "audit this file", or right before committing a significant piece of backend or authentication logic.

## Prerequisites
- You must have read access to the target source code files.
- Familiarize yourself with the OWASP Top 10 vulnerabilities for the language used in the project.

## Workflow

1. **Static Analysis Check**:
   - Inspect the code for any Hardcoded Secrets (API keys, passwords, tokens).
   - Check for SQL Injection risks: Ensure ORMs are used correctly or prepared statements are strictly enforced. Do not allow string concatenation in SQL queries.
   - Check for Cross-Site Scripting (XSS): Ensure user input is sanitized and properly escaped before rendering.
2. **Business Logic & Auth Check**:
   - Verify that authentication middleware is applied to sensitive routes.
   - Check for Insecure Direct Object References (IDOR): Ensure the code verifies that the currently logged-in user owns the resource they are trying to access.
3. **Dependency Check**:
   - Briefly review package files (`package.json`, `requirements.txt`) if provided, to ensure no notoriously vulnerable packages are explicitly requested.
4. **Reporting**:
   - Create a structured markdown report.
   - Group findings by severity (CRITICAL, HIGH, MEDIUM, LOW).
   - For every finding, you MUST provide a concrete code snippet showing how to fix it.

## Verification
- Do not modify the files directly unless the user asks you to "fix" them. Only provide the report.
- Ensure the report uses standard GitHub alert blocks (`> [!WARNING]`, `> [!CAUTION]`) to highlight critical vulnerabilities.
