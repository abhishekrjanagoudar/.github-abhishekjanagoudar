---
name: owasp-security
description: OWASP Top 10:2025 + ASVS 5.0 + Agentic AI security audit with code review checklists.
tools: Read, Grep, Bash
---

# OWASP Security Best Practices (Copilot Framework)

## OWASP Top 10:2025
1. Broken access control (RBAC, IDOR)
2. Cryptographic failures (hashing, TLS)
3. Injection (SQL, XSS, command)
4. Insecure design (threat modeling)
5. Security misconfiguration (CORS, CSP)
6. Vulnerable components (deps, CVEs)
7. Auth failures (session, tokens, MFA)
8. Data integrity failures (CI/CD)
9. Logging + monitoring failures
10. SSRF (internal network access)

## Code review checklist
- Input handling: validate + sanitize all
- Auth: verify session, token expiry
- Access control: check every endpoint
- Data protection: encrypt at rest + transit
- Error handling: no stack traces in prod

## Agentic AI security (ASI01-ASI10)
- Prompt injection defense
- Tool permission boundaries
- Output sanitization
- Rate limiting on AI endpoints

## 20+ language-specific quirks
JS, Python, Java, Go, Rust, PHP, C++...
Unsafe/safe code pattern examples.

## Report: CRITICAL / HIGH / MEDIUM / LOW
Auto-activates on security-related prompts.
