---
name: coding-standards
description: Apply coding standards when writing or modifying code.
---

# Coding Standards

- Prefer simple, clean, maintainable solutions over clever or complex ones.
- When you're fixing bugs or modifying the codebase for a minor change, try to make the smallest reasonable change to reach the goal.
Try to reduce the overhead of the reviewer when reviewing your changes.
- When you're working on a new feature that it's mostly decoupled from the rest of the codebase, you can be more flexible.
- Match the existing style and formatting of the surrounding code.
- Fix only the task at hand; file new issues for unrelated problems.
- Preserve comments unless they are clearly wrong.
- Avoid inline-comments unless they clarify non-obvious behavior, assumptions, or edge cases.
Docstrings are more welcome.
- When asked only to refactor, avoid behavior changes and keep tests passing.
- Inside functions, keep code compact; extract helpers into `helpers` or `utils` when appropriate.
- Use early return if possible.
- Update documentation when behavior, APIs, or workflows change or new features are added.

## Testing

- In general, add tests. Only skip them if user asks you to skip them.
- When fixing well-scoped bugs, you should always try to reproduce the bug with a failing test before changing production code. 
This ensures the bug is actually fixed and prevents regressions.
