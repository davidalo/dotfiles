---
name: git-guidelines
description: Git usage rules for commits, flags, and handling failures. Use when running git commands or preparing commits.
---

# Git Guidelines

- Never include Claude / Codex footers in commit messages. No "Generated with" or "Co-Authored-By: " footers.
- Never use: `--no-verify`, `--no-hooks`, or `--no-pre-commit-hook` flags. Never use `git add -A`.
- If any precommit tools is failing, check the error message and fix the issue. Never bypass it.

Read `commit-standards` skill when creating commits. 

# GitHub / GitLab guidelines

When you need to pull an issue or PR/MR details, use MCPs if available.
If not available, try `gh` or `gl` command line tools.
Finally, use http requests.
