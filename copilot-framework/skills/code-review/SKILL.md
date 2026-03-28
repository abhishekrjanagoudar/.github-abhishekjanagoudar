---
name: code-review-excellence
description: Multi-language code reviewer. React 19, Vue 3, Rust, TypeScript, Python, Go.
allowed-tools:
  - Read, Glob, Grep, Bash, WebFetch
---

# Code Review Excellence (Copilot Framework)

## Review phases
1. Context gathering (read PR, check CI)
2. High-level: architecture + design fit
3. Line-by-line: logic, security, perf
4. Summary + decision (approve/request)

## Severity labels
[blocking]  -- must fix before merge
[important] -- should fix, discuss
[nit]       -- nice to have
[suggestion] -- alternative approach
[learning]  -- educational, no action
[praise]    -- good work, keep it up

## Language guides (loaded on demand)
- React 19: hooks, RSC, Server Actions
- TypeScript: strict, generics, utility
- Rust: ownership, lifetime, unsafe
- Python: type hints, async patterns
- Vue 3.5: Composition API, Pinia
- Go: goroutines, error handling
- C/C++: memory safety, RAII, UB
- Java 21: virtual threads, Spring Boot

## Golden rule
Ask questions, don't command.
Always explain WHY, not just WHAT.
