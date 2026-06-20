# Security Audit Report

## 1. Hardcoded Secrets Scan
- [ ] Checked `.env` tracking
- [ ] Checked source files for `sk_live_...` or `pub_...`
**Findings:** [Agent to report findings here]

## 2. OWASP Top 10 Checks
- [ ] **Injection (SQLi/XSS):** Are raw queries used without parameterization?
- [ ] **Broken Authentication:** Are routes properly protected by middleware?
- [ ] **Sensitive Data Exposure:** Is bcrypt used for passwords?
**Findings:** [Agent to report findings here]

## 3. Dependency Check
- [ ] Are there outdated NPM packages with known vulnerabilities? (Agent: run `npm audit` if applicable)
