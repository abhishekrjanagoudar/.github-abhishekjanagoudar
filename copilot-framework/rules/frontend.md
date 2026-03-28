---
paths:
  - "components/**/*.tsx"
  - "app/**/*.tsx"
---

# Frontend Design & Development Rules (Copilot Framework)

## Global Standards
- Functional components + hooks only. No class components.
- shadcn/ui for primitives, never build from scratch.
- Tailwind CSS exclusively for all styling.
- Dark mode FIRST, light mode via overrides.
- Zustand for global state, no prop drilling past 2 levels.
- cn() utility for all conditional classes.
- @phosphor-icons/react for ALL icons.

## Next.js Best Practices
- next/image for ALL images with proper `sizes` and `priority` where needed.
- Server Components by default; `use client` only for interactivity.
- Canvas: always wrap context changes in `ctx.save()`/`restore()`.

## Animation intent
- Purposeful micro-interactions on hover/focus only.
- Transition speed: 200-300ms.
- Loading states: skeleton loaders only, no generic spinners.
- Accessibility: Contrast ratio >= 4.5:1 (WCAG AA).
