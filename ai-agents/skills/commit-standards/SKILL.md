---
name: commit-standards
description: Use when preparing git commits, user says "write a commit", "commit message", "/commit", etc.  
  Conventional commits format. Subject ≤50 chars, body only when "why" isn't obvious. 
  Auto-triggers when staging changes.
---

## Rules

**Subject line:**
- `<scope>: (<type>) <imperative summary>` — `<scope>` optional
- Types: `feat`, `fix`, `refactor`, `perf`, `docs`, `test`, `chore`, `build`, `style`, `revert`
- Imperative mood: "add", "fix", "remove" — not "added", "adds", "adding"
- ≤50 chars when possible, hard cap 72
- No trailing period
- Match project convention for capitalization after the type
- Scope is derived from the project, such as `API`, `Cart`, `CI/CD`, `Drivers` 

**Body (only if needed):**
- Skip entirely when subject is self-explanatory.
- Add body only for: non-obvious *why*, breaking changes, migration notes, linked issues.
- Wrap at 72 chars
- Bullets `-` not `*`

**What NEVER goes in:**
- "This commit does X", "I", "we", "now", "currently" — the diff says what
- "Generated with Claude Code" or any AI attribution
- Emoji (unless project convention requires)
- Restating the file name when scope already says it

## Examples

Diff: new endpoint for user profile with body explaining the why
- ❌ "API: (feat) add a new endpoint to get user profile information from the database"
- ✅
  ```
  API: (feat) add GET /users/:id/profile

  - Mobile client needs profile data without the full user payload
  to reduce LTE bandwidth on cold-launch screens.
  ```

Diff: breaking API change
- ✅
  ```
  - API: (feat) rename /v1/orders to /v1/checkout

  - BREAKING CHANGE: clients on /v1/orders must migrate to /v1/checkout
  before 2026-06-01. Old route returns 410 after that date.
  ```

## Auto-Clarity

Always include body for: breaking changes, security fixes, data migrations, anything reverting a prior commit. Never compress these into subject-only — future debuggers need the context.
Always add body if there is a regression. Link the commit / PR that introduced the regresion.