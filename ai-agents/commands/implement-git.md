---
description: Implement git contribution
allowed-tools: Grep, Read, LS, Find, Bash(gh issue view:*), Bash(glab issue view:*), Bash(git checkout:*), Bash(git pull:*)
argument-hint: ISSUE_ID=<issue_id> GITHUB_OR_GITLAB=<GITHUB>
---

Use these skills and do not restate their rules:
- `skills/coding-standards/SKILL.md`
- `skills/testing-standards/SKILL.md`
- `skills/git-guidelines/SKILL.md`

Do not start implementing features until explicitly asked.

# Workflow

## High-level steps

1. Start from `master` or `main` (unless told to work on a different branch). Create and work on a dedicated branch for every feature, bug-fix, or requested refactor. If a branch already exists and is linked to the PR/MR, use it; otherwise create a new one. Avoid `feature/` prefix; ideally use the issue name as reference.
2. Retrieve the issue details.
3. Plan before implementation and get approval.
4. Do not push commits; create them and let me review them before pushing.

## Retrieve issue details

Determine whether the target is a GitLab Issue or a GitHub Issue, then run the appropriate command:

- For GitLab: `glab issue view $ISSUE_ID`
- For GitHub: `gh issue view $ISSUE_ID`

Both CLI tools accept an ID and display the full metadata. You are allowed to run these commands with internet access.

## Plan before implementation

* Read the related code and `README.md` plus any relevant documentation.
* Ask questions when requirements are unclear.
* Draft a detailed, step-by-step blueprint for building the feature.
* Break that plan into small, iterative chunks.
* Refine until each step is small enough to implement safely with thorough tests, yet large enough to move the project forward.
* Present the plan for approval before implementing.

# Extra user input

Follow the following extra user input when available:

$ARGUMENTS
