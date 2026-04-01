# 🤖 GitHub Copilot Instructions

This repository follows a multi-file AI guidance system inspired by orchestration frameworks (ruflo/Manthan Patel) and adapted for GitHub Copilot. Regardless of the LLM chosen (Claude, Gemini, GPT), adhere to these principles.

---

## 🏛️ Core Philosophy
- **Repository Facts First**: Trust existing code patterns over generic assumptions.
- **Read Before Writing**: Proactively read relevant files before proposing changes.
- **Minimal, Reversible Changes**: Keep changes well-scoped; explain tradeoffs.
- **No Inventions**: Never invent APIs, env vars, routes, or files that don't exist.
- **Clarify First**: If requirements are ambiguous, ask one focused question before acting.

---

## 🏗️ Technical Stack
- **Framework**: Next.js 14, App Router, TypeScript
- **Frontend**: Tailwind CSS, shadcn/ui, @phosphor-icons/react
- **Backend**: Supabase (Auth + DB), Upstash Redis (rate limiting), Stripe (payments)
- **Engine**: Canvas 2D API, WebCodecs + Mediabunny (MP4), Remotion
- **Testing**: Vitest (unit), Playwright (e2e)
- **Hosting**: Vercel

> [!NOTE]
> Full folder structure and dev commands → [`copilot-framework/Project-Brain.md`](copilot-framework/Project-Brain.md)

---

## ⚡ Non-Negotiable Standards

### 🛠️ Architecture & State
- **TypeScript**: Strict mode. No `any`, no `as` casts. Shared types in `types/`.
- **State**: Zustand + `subscribeWithSelector`. No prop drilling beyond 2 levels.
- **Components**: Functional + hooks only. shadcn/ui for primitives — never build from scratch.

### 🎨 UI & UX
- **Styling**: Tailwind CSS only. `cn()` for conditionals. Dark mode first, light via overrides.
- **Icons**: `@phosphor-icons/react` exclusively.
- **Images**: `next/image` with `sizes` and `priority` where needed. Never use `<img>`.
- **Canvas**: Always `ctx.save()` / `ctx.restore()` around context changes.

### 🔐 Security & Auth
- **Auth**: Always `requireAuth()` server-side. Use `auth.uid()` — never trust client-sent IDs.
- **Secrets**: Never expose tokens in code. Verify `.env*` is in `.gitignore`.
- **Validation**: Validate ALL inputs with Zod schemas. Return 400 on failure.
- **Integrity**: Check Stripe webhook signatures. No `dangerouslySetInnerHTML`.

---

## 📁 Context Routing System
Load the relevant file(s) below based on the task. Do not load files that aren't needed.

### 🧱 Domain Rules (Auto-applied by path)
| Scope | Instruction File |
| :--- | :--- |
| `app/api/**` | [`rules/api.md`](copilot-framework/rules/api.md) |
| `components/**`, `app/**/*.tsx` | [`rules/frontend.md`](copilot-framework/rules/frontend.md) |
| `supabase/**`, `lib/db/**` | [`rules/database.md`](copilot-framework/rules/database.md) |

### 🤖 specialized Agents (Invoke by task)
| Task | Agent |
| :--- | :--- |
| Code review / PR audit | [`agents/code-reviewer.md`](copilot-framework/agents/code-reviewer.md) |
| Bug investigation | [`agents/debugger.md`](copilot-framework/agents/debugger.md) |
| Cleanup / simplification | [`agents/refactorer.md`](copilot-framework/agents/refactorer.md) |
| Security audit | [`agents/security-auditor.md`](copilot-framework/agents/security-auditor.md) |
| Writing tests | [`agents/test-writer.md`](copilot-framework/agents/test-writer.md) |
| Writing docs / JSDoc | [`agents/doc-writer.md`](copilot-framework/agents/doc-writer.md) |

### ⚡ Workflows & Skills
| Requirement | Skill / Command |
| :--- | :--- |
| Deploy to production | [`commands/deploy.md`](copilot-framework/commands/deploy.md) |
| Fix a GitHub issue | [`commands/fix-issue.md`](copilot-framework/commands/fix-issue.md) |
| Review a PR | [`commands/pr-review.md`](copilot-framework/commands/pr-review.md) |
| UI component design | [`skills/frontend-design/SKILL.md`](copilot-framework/skills/frontend-design/SKILL.md) |
| Full design system | [`skills/ui-ux-pro-max/SKILL.md`](copilot-framework/skills/ui-ux-pro-max/SKILL.md) |
| OWASP / security | [`skills/owasp-security/SKILL.md`](copilot-framework/skills/owasp-security/SKILL.md) |
| Code review depth | [`skills/code-review/SKILL.md`](copilot-framework/skills/code-review/SKILL.md) |
| SEO optimization | [`skills/seo/SKILL.md`](copilot-framework/skills/seo/SKILL.md) |
| Remotion video | [`skills/remotion/SKILL.md`](copilot-framework/skills/remotion/SKILL.md) |

---

## 🧪 Response Guidelines
- **Be Concise**: Lead with the fix, not the explanation.
- **Severity Labels**: Use `[blocking]`, `[important]`, `[nit]`, `[suggestion]`, `[praise]`.
- **Logic**: Separate blocking issues from suggestions clearly.
- **Git**: Format commits as `NM-XXX: [description]`.
- **Refuse**: Decline requests that violate the standards defined here or in loaded sub-files.
