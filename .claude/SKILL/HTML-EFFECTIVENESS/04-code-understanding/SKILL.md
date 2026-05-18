---
name: 04-code-understanding
description: Learn cookie-based authentication by tracing a single request through five layers of code
---

# Codebase Understanding — Auth Flow Walkthrough

Trace a request from browser → cookie → middleware → cache → database to understand the whole auth system.

## The Five-Step Flow

1. **Browser** → `GET /api/session` with `fw_sid` cookie (credentials: 'include')
2. **Route handler** → Thin, just returns `req.ctx.session`
3. **verifyToken() middleware** ⚠️ **Trust boundary** — reads cookie, asks SessionStore, populates req.ctx or 401s
4. **SessionStore** → LRU cache + Postgres fallback; writes bypass cache (always invalidate)
5. **Postgres sessions table** → Keyed on random 32-byte ID, covered index on user_id for revoke-everywhere

## Key Insight

There is exactly **one place** where auth logic lives: the `verifyToken()` middleware. Every protected route is mounted behind it. Change that function, change auth globally. No duplication means fewer places to reason about.

## Gotchas

- **LRU cache is per-process** — Revoking a session only clears the local worker's cache. Other workers may serve the session for up to 60s until their TTL expires. This is intentional (auth shouldn't require Redis), but affects "sign out everywhere" latency.
- **expiresAt comparison uses Date objects** — The Postgres driver returns a JS Date, so `session.expiresAt < Date.now()` works. Don't refactor this to string comparison without adjusting the middleware check.
- **SessionStore is the only DB caller** — All auth reads/writes go through SessionStore. Don't query the sessions table directly from routes; route through the store so the cache stays coherent.
- **Client context mirrors server session** — AuthProvider hydrates from `/api/session`. If server revokes but client cache is stale, user may see "logged in" UI briefly before the next auth error.

## When to Reference

- **Adding new protected routes** → Mount behind `verifyToken`
- **Changing session expiry logic** → Update both middleware check and DB column
- **Adding "logout everywhere" feature** → Cache invalidation across workers is the hard part
- **Debugging auth flakiness** → Check LRU TTL and whether concurrent requests are hitting stale cache

## Full Walkthrough

See `resources/04-code-understanding.html` for the complete diagram, step-by-step code snippets, and sidebar reference to key files.
