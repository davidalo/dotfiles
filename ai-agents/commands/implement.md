---
description: Implement contribution
allowed-tools: Grep, Read, LS, Find, Bash(gh issue view:*), Bash(glab issue view:*), Bash(git checkout:*), Bash(git pull:*)
---

This document describes the development practices and principles you **must** follow.  
Do **not** start implementing features until explicitly asked—use this guide to get into the right state of mind.

1. **Start from `master` or `main`** (unless told to work on a different branch).  
2. **Understand the existing code** before making changes.  
3. **Work on a dedicated branch** for every feature, bug-fix, or requested refactor. If a branch already exists and is linked to the PR/MR, use it; otherwise create a new one.  
4. **Omit the Claude footer** from all commit messages.  
5. **Do not push commits**, just create them and let me review them before pushing.

## Retrieve issue details

Determine whether the target is a **GitLab Issue** or a **GitHub Issue**, then run the appropriate command:

- For GitLab: `glab issue view`
- For GitHub: `gh issue view`

Both CLI tools accept an ID and display the full metadata.

---

# High-level flow

* Create a markdown file in `doc/dev/` named after the feature (use the same name as the branch). Do not commit those files.  
* Use this file to record clarifying questions, answers, and other insights while you work. Treat it as long-term memory in case the session is interrupted.  
* Feel free to edit, rearrange, or delete content in this notes file.  
* Add only information that is genuinely helpful — **be brief and useful**.

---

## Understand the feature

1. Read `README.md` and any relevant documentation it references. Read any code you need to understand what you have to do.  
2. Identify ambiguities and ask clarifying questions *before* you code.  
   * Example: for a tic-tac-toe app you might ask, “Should this be a TUI, web-based, or something else?”  
3. Update `README.md` or any other docs with any new insights that future developers would need.

---

## Develop the feature

After you understand both the codebase and the requested feature, follow the **development flow** below.

Avoid comments when they are not necessary; add them only when making assumptions, clarifying non-obvious code, or handling edge cases.

### Preparation

* Draft a detailed, step-by-step blueprint for building the feature.  
* Break that plan into small, iterative chunks.  
* Refine until each step is:  
  * **Small enough** to implement safely with thorough tests, yet  
  * **Large enough** to move the project forward meaningfully.

---

# Commit message format

<50-character summary>

Avoid body lines; additional detail can be added later in the MR if needed.

---

## Pure refactors

When asked **only** to refactor existing code (as opposed to adding functionality), avoid changing behaviour and ensure tests continue to pass.

---

## Capturing additional guidance

If I interrupt to correct your approach, update this document so future sessions retain the guidance. Always ask for permission before adding new general-purpose prompts.
