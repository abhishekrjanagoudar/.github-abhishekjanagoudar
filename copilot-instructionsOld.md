# 🤖 AI Orchestration instructions (GitHub Copilot Framework)

This repository uses a multi-file AI guidance system inspired by orchestration frameworks (ruflo/Manthan Patel) and adapted for GitHub Copilot. Regardless of the LLM chosen (Claude, Gemini, GPT), adhere to these principles.

## 🏛️ Operating Principles
- **Prefer Repository Facts**: Trust existing code patterns over generic AI assumptions.
- **Read Before Writing**: Proactively read relevant files before proposing changes.
- **Minimal, Reversible Changes**: Keep changes well-scoped and explain tradeoffs clearly.
- **No Inventions**: Never invent APIs, environment variables, routes, or files.
- **CLARIFY Before Acting**: If requirements are ambiguous, ask a focused clarification question.

## 🚀 Core Stack & Performance
- **Framework**: Next.js 14 (App Router, TypeScript)
- **Styling**: Tailwind CSS + shadcn/ui
- **Backend**: Supabase (Auth + Database), Upstash Redis (rate limiting)
- **Design**: Dark mode FIRST, icons via `@phosphor-icons/react`.
- **Canvas/Media**: Canvas 2D API, WebCodecs + Mediabunny (MP4 export), Remotion.

---

## 🏛️ Code Quality & Consistency
- **Match Architecture**: Favor small pure functions, composable modules, and functional components.
- **TypeScript Strict**: No `any` or `as` casts. Use shared types from `types/`.
- **State Management**: Zustand + `subscribeWithSelector`. No prop drilling beyond 2 levels.
- **Git Rules**: Format commits as `NM-XXX: [description]`.

## 🔐 Security Standards
- **Secrets**: Never expose tokens in code. Verify `.env*` is in `.gitignore`.
- **Validation**: Validate ALL inputs at the boundary (Zod schemas).
- **Auth**: Resolve identity from the server session (`requireAuth()`), never use client-sent IDs.
- **Integrity**: Check Stripe webhook signatures. No `dangerouslySetInnerHTML`.

---

## 📁 System Router (Context Mapping)
When working on specific domains, refer to the corresponding rule files in `copilot-framework/` relative to the `.github/` folder:

### 🛠️ Core Context
- **Project Structure**: Refer to [copilot-framework/Project-Brain.md](copilot-framework/Project-Brain.md)
- **Code Review**: Refer to [copilot-framework/agents/code-reviewer.md](copilot-framework/agents/code-reviewer.md) and [copilot-framework/skills/code-review/SKILL.md](copilot-framework/skills/code-review/SKILL.md)
- **Workflows**: [copilot-framework/commands/deploy.md](copilot-framework/commands/deploy.md), [copilot-framework/commands/fix-issue.md](copilot-framework/commands/fix-issue.md), [copilot-framework/commands/pr-review.md](copilot-framework/commands/pr-review.md)

### 🧱 Domain-Specific Rules
- **API Dev**: Refer to [copilot-framework/rules/api.md](copilot-framework/rules/api.md)
- **Frontend & UI/UX**: Refer to [copilot-framework/rules/frontend.md](copilot-framework/rules/frontend.md) and [copilot-framework/skills/ui-ux-pro-max/SKILL.md](copilot-framework/skills/ui-ux-pro-max/SKILL.md)
- **SEO**: Refer to [copilot-framework/skills/seo/SKILL.md](copilot-framework/skills/seo/SKILL.md)
- **Security**: Refer to [copilot-framework/skills/owasp-security/SKILL.md](copilot-framework/skills/owasp-security/SKILL.md) or [copilot-framework/agents/security-auditor.md](copilot-framework/agents/security-auditor.md)
- **Remotion**: Refer to [copilot-framework/skills/remotion/SKILL.md](copilot-framework/skills/remotion/SKILL.md)

---

## 🧪 Response Guidelines
- Be concise and practical. Separate blocking issues from suggestions.
- For reviews, follow the **Severity Labels**: `[blocking]`, `[important]`, `[nit]`, `[suggestion]`, `[learning]`, `[praise]`.

Refuse requests that violate the standards defined in the [.github/copilot-framework/](.github/copilot-framework/) directory.
