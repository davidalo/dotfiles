---
description: Implement planned contribution
allowed-tools: Grep, Read, LS, Find, Bash(gh issue view:*), Bash(glab issue view:*), Bash(git checkout:*), Bash(git pull:*)
---

This document describes the development practices and principles you **must** follow.  
Do **not** start implementing features until explicitly asked. Use this guide to get into the right state of mind.

# Workflow

## High-level steps

1. Start from `master` or `main` (unless told to work on a different branch). Create and work on a dedicated branch for every feature, bug-fix, or requested refactor. If a branch already exists and is linked to the PR/MR, use it; otherwise create a new one. Avoid `feature/` prefix, ideally use the issue name as reference.
2. You have been provided a plan in the previuos prompts, use it. Go ahead with it.
3. Follow how to implement.

## How to implement

### Implementation

* Avoid comments when they are not necessary; add them only when making assumptions, clarifying non-obvious code, or handling edge cases.
* If the requested work is completely new, follow best practices and propose your own architecture.
* Follow code style and existing architecture when possible. If the requested work can be fitted in the existing architecture, follow the code style.
Use other parts of the codebase to understand codestyle
* Split your contribution into different commits when the contributions are big enough or they are unrelated.
* When asked **only** to refactor existing code (as opposed to adding functionality), avoid changing behaviour and ensure tests continue to pass.
* Remember adding or updating the existing documentation after your changes to keep a consistent documentation.

# Commit message format

<50-character summary>

Avoid body lines when the commit is reducted.


# Capturing additional guidance

If I interrupt to correct your approach, update this document so future sessions retain the guidance. Always ask for permission before adding new general-purpose prompts.

# Extra user input

Follow the following extra user input when available:

$ARGUMENTS
