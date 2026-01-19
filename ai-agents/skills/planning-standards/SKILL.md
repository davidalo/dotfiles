---
name: planning-standards
description: Standard planning workflow for plan-only commands.
---

# Planning Standards

Use this skill for plan-only responses when a command requires planning before implementation.

## Core workflow

1. Gather context from the codebase, `README.md`, and referenced documentation.
2. Identify ambiguities and ask clarifying questions before finalizing a plan.
3. Draft a step-by-step plan in small, safe increments that move the work forward.
4. Call out assumptions, risks, and dependencies.
5. If the command asks for architecture or change lists, include them explicitly.
6. Do not implement or modify files until the plan is approved.

## Output expectations

- Follow the plan structure required by the command prompt (e.g., numbered steps with sub-bullets).
- Keep the plan actionable, testable, and easy to review.
- Present the plan in the terminal; do not create extra files unless instructed.
- When a command requires a structured presentation, include:
  - A block diagram of the code architecture with the different entities.
  - A numbered plan using "Step X" sections with indented sub-bullets.
  - A change list that calls out changes per file or feature.
- Avoid restating these rules in the output.
