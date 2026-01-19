---
description: Implement contribution
allowed-tools: Grep, Read, LS, Find, mcp__github__*, mcp__gitlab__*, Bash(git checkout:*), Bash(git pull:*)
---

Use these skills and do not restate their rules:
- `skills/coding-standards/SKILL.md`
- `skills/testing-standards/SKILL.md`
- `skills/git-guidelines/SKILL.md`
Follow `skills/git-guidelines/SKILL.md` for commit message format.

Do not start implementing features until explicitly asked.

1. Start from `master` or `main` (unless told to work on a different branch).
2. Understand the existing code before making changes.
3. Work on a dedicated branch for every feature, bug-fix, or requested refactor. If a branch already exists and is linked to the PR/MR, use it; otherwise create a new one.
4. Do not push commits; create them and let me review them before pushing.

## Retrieve issue details

An issue URL will be provided in the arguments. If it is missing, ask for it before proceeding.

Use the URL to determine whether the issue is on GitHub or GitLab, then use the corresponding MCP server to retrieve the issue details.

---

# Capturing additional guidance

If I interrupt to correct your approach, update this document so future sessions retain the guidance. Always ask for permission before adding new general-purpose prompts.
