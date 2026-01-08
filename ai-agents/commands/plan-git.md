---
description: Plan git contribution
allowed-tools: Grep, Read, LS, Find, Bash(gh issue view:*), Bash(glab issue view:*), Bash(git checkout:*), Bash(git pull:*)
argument-hint: ISSUE_ID=<issue_id> GITHUB_OR_GITLAB=<GITHUB> EXTRA_ARGS=<extra_args>
---

This command is plan-only. Do not implement.
When implementation starts, follow `skills/coding-standards/SKILL.md` and `skills/testing-standards/SKILL.md`.

# Workflow

## High-level steps

1. Start from `master` or `main` (unless told to work on a different branch).
2. Retrieve the issue details to get the information.
3. Plan only. Do not modify anything.
4. Present the plan and code architecture in the terminal; do not create extra files.
   - The code architecture must be presented as a block diagram with the different entities.
   - Lay out the implementation plan as numbered Step X sections, each with indented sub-bullets for the details.
   - Lay out a change list with the changes per file or feature.

## Retrieve issue details

This is a $GITHUB_OR_GITLAB issue. Run the appropriate command:

- For GitLab: `glab issue view $ISSUE_ID`
- For GitHub: `gh issue view $ISSUE_ID`

Both CLI tools accept an ID and display the full metadata. You are allowed to run these commands with internet access.

## Plan mode

* Read the related code, `README.md`, and any relevant documentation it references.
* If the contribution is big and it contains changes in many codebase features, draft the proposed code architecture and how new code fits the existing codebase.
* Draft a detailed, step-by-step blueprint for building the feature.
* Break that plan into small, iterative chunks.
* Refine until each step is small enough to implement safely with thorough tests, yet large enough to move the project forward.
* Ask any questions you need about architecture or implementation details.
* Do not start implementing until the plan is approved.

# Extra user input

Follow the following extra user input when available:

$EXTRA_ARGS
