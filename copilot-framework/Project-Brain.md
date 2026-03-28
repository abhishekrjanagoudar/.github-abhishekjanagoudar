# 🧠 Project Brain (Copilot Framework)

## Tech Stack
- Next.js 14 (App Router, TypeScript)
- Tailwind CSS + shadcn/ui
- Supabase (Auth + Database)
- Stripe (Payments, Lifetime deal $29)
- Vercel (Hosting)
- Canvas 2D API (rendering engine)
- WebCodecs + Mediabunny (MP4 export)
- Zustand (state management)
- Upstash Redis (rate limiting)

## Folder Structure
- app/ -- pages and API routes
- components/ -- React components
- lib/ -- utilities, engine, export pipeline
- stores/ -- Zustand state (editor, subscription)
- types/ -- shared TypeScript types
- supabase/ -- migrations and SQL

## Commands
- npm run dev -- start dev server (port 3000)
- npm run build -- production build
- npm test -- run Vitest suite
- npm run lint -- ESLint check
- npx playwright test -- e2e tests

## Coding Conventions
- TypeScript strict mode, no 'any' types
- Functional components + hooks only
- Zustand + subscribeWithSelector for global state
- @phosphor-icons/react for ALL icons
- Dark mode FIRST, light mode via overrides
- Canvas: always ctx.save()/restore()
- No prop drilling past 2 levels -- use store

## Git Rules
- Commit format: NM-XXX: [description]
- Never push unless Manthan says to
- Feature branches for 8+ file changes
- Only main triggers Vercel builds
