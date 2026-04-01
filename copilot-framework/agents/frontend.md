---
paths:
  - "components/**/*.tsx"
  - "app/**/*.tsx"
---

# Frontend Rules (Copilot Framework)

> Non-negotiables (Tailwind, shadcn/ui, dark mode, Zustand, icons, next/image, canvas) are defined in `copilot-instructions.md`. Do not restate them here.

## Next.js Specifics
- Server Components by default; `use client` only when interactivity is required.
- Never use `<img>` — always `next/image` with `sizes` and `priority` set appropriately.

## Animation
- Micro-interactions on hover/focus only — no gratuitous motion.
- Transition speed: 200–300ms.
- Loading states: skeleton loaders only, never generic spinners.
- Accessibility: contrast ratio ≥ 4.5:1 (WCAG AA). Touch targets ≥ 44px.
