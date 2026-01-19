---
description: Plan git contribution
allowed-tools: Grep, Read, LS, Find, mcp__github__*, mcp__gitlab__*, Bash(git checkout:*), Bash(git pull:*)
---

This command is plan-only. Do not implement.
If you are Claude, enter plan mode and use your internal plan mode. If you are Codex, GPT, or another model, follow `skills/planning-standards/SKILL.md` for the planning workflow.
When implementation starts, follow `skills/coding-standards/SKILL.md` and `skills/testing-standards/SKILL.md`.

# Workflow

## High-level steps

1. Start from `master` or `main` (unless told to work on a different branch).
2. Retrieve the issue details to get the information.
3. Plan only. Do not modify anything.

## Retrieve issue details

An issue URL will be provided in the arguments. If it is missing, ask for it before proceeding.

Use the URL to determine whether the issue is on GitHub or GitLab, then use the corresponding MCP server to retrieve the issue details.

# Extra user input

Follow the following extra user input when available:

$ARGUMENTS
