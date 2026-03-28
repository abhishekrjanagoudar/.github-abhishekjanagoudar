---
paths:
  - "supabase/**"
  - "lib/db/**"
---

# Database & Storage Rules (Copilot Framework)

## Supabase Dev
- Use `supabase/migrations` for ALL schema changes.
- Never write raw SQL in components; always use the `supabase-js` client.
- Auth: Always use `auth.uid()` from the session. No client-sent IDs.

## Data Validation
- Validate ALL database inputs with Zod schemas in the server layer.
- `schema.parse()` before calling Supabase client.
- Check return values for `.error` on ALL client calls.

## SQL & RLS
- Enforce Row Level Security (RLS) on ALL tables.
- Use `auth.uid() = user_id` for table policies.
- Audit raw SQL for potential injection in direct queries.

## Performance
- Check for unnecessary large selects; only query required columns.
- Ensure appropriate indexes for frequently queried columns.
