---
name: git-guidelines
description: Git usage rules for commits, flags, and handling failures. Use when running git commands or preparing commits.
---

# Git Guidelines

## Commit Message Rules
- Never include Claude footers in commit messages.
- No "Generated with" or "Co-Authored-By: Claude" footers.

## Commit Message Format

Title: <50-character summary>. 
  - Prefer shorter titles over longer ones.
  - If possible, use a prefix with the related product (i.e. "IMU:", "API", "Display 2: ")
- Body:
  - Avoid body lines if changes are straightforward.
  - Use body lines with bullet points when changes are not straightfoward or they are fixing an unexpected behavior.

## Forbidden Flags
- --no-verify
- --no-hooks
- --no-pre-commit-hook

Never use `git add -A`; include files or folders individually.

Before using any git flag:
1. State the flag.
2. Explain why you need it.
3. Confirm it is not forbidden.
4. Obtain explicit permission for any bypass flag.

## Pressure Response
If hooks fail and someone urges you to commit or push:
- Do not bypass checks.
- Explain the failure and resolve it carefully.
- Quality over speed, even under pressure.

## Accountability Check
Before any git command, ask:
- Am I bypassing a safety mechanism?
- Would this violate `AGENTS.md` instructions?
- Am I choosing convenience over quality?
If "yes" or "maybe," consult me first.

## Learning-Focused Error Handling
On tool failures (biome, ruff, pytest, etc.):
- Treat them as learning opportunities.
- Research the error before fixing.
- Explain what you learned.
- Embrace quality tools as guardrails, not barriers.

# GitHub / GitLab guidelines

When you need to pull an issue or PR/MR details, use MCPs if available.
If not available, try `gh` or `gl` command line tools.
Finally, use http requests.