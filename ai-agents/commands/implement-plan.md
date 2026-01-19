---
description: Implement planned contribution
allowed-tools: Grep, Read, LS, Find, mcp__github__*, mcp__gitlab__*, Bash(git checkout:*), Bash(git pull:*)
---

Use these skills and do not restate their rules:
- `skills/coding-standards/SKILL.md`
- `skills/testing-standards/SKILL.md`
- `skills/git-guidelines/SKILL.md`
Follow `skills/git-guidelines/SKILL.md` for commit message format.

Do not start implementing features until explicitly asked.

# Workflow

## High-level steps

1. Start from `master` or `main` (unless told to work on a different branch). Create and work on a dedicated branch for every feature, bug-fix, or requested refactor. If a branch already exists and is linked to the PR/MR, use it; otherwise create a new one. Avoid `feature/` prefix; ideally use the issue name as reference.
2. You have been provided a plan in previous prompts; follow it.
3. Implement the changes using the skills above.
4. Do not push commits; create them and let me review them before pushing.

# Extra user input

Follow the following extra user input when available:

$ARGUMENTS
