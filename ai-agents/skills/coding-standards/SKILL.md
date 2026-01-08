---
name: coding-standards
description: Apply coding standards for implementing and refactoring changes. Use when writing or modifying code.
---

# Coding Standards

## Instructions
- Prefer simple, clean, maintainable solutions over clever or complex ones.
- Make the smallest reasonable change to reach the goal. Ask before rewriting from scratch.
- Match the existing style and formatting of the surrounding code.
- Fix only the task at hand; file new issues for unrelated problems.
- Preserve comments unless they are provably wrong.
- Comments must be evergreen; avoid temporal references to recent changes.
- Never implement mock modes unless explicitly instructed.
- When fixing bugs, do not discard the old implementation without permission.
- Avoid names like "improved," "new," or "enhanced."
- Inside functions, keep code compact; extract helpers into `helpers` or `utils` when appropriate.
- Use early return if possible.
