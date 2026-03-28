---
paths:
  - "app/api/**"
  - "src/app/api/**"
---

# API Development Rules (Copilot Framework)

## Input validation
- Validate ALL inputs with Zod schemas
- Parse request body: schema.parse(await req.json())
- Validate URL params: z.string().uuid()
- Return 400 with { error: "..." } on validation failure

## Authentication
- All protected routes: const user = await requireAuth()
- requireAuth() throws 401 if no session
- Never trust client-sent user IDs -- use auth.uid()

## Error handling
- Consistent format: { error: string, code?: string }
- Never expose stack traces or internal errors
- Log errors with context (route, user_id, input)
- Return appropriate HTTP codes:
  400 = bad input, 401 = no auth, 403 = forbidden
  404 = not found, 429 = rate limited, 500 = server error

## Rate limiting
- All public endpoints: rateLimit(req, { max: 10 })
- Stripe checkout: rateLimit(req, { max: 3 })
- Export: rateLimit(req, { max: 5 })
- Use Upstash Redis: @upstash/ratelimit

## Response
- Always return NextResponse.json()
- Set Cache-Control headers where appropriate
- Stripe webhooks: return 200 quickly, process async
