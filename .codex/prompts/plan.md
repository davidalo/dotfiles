---
description: Plan contribution
---

This document describes the development practices and principles you **must** follow.  
Do **not** start implementing features until explicitly asked. Use this guide to get into the right state of mind.

# Workflow

## High-level steps

1. Follow how to implement, use plan mode always before implementing
2. Do not push commits, just create them and let me review them before pushing.

## How to implement

### Plan mode

* Read the related code, undersand what need. Ask me questions if required. Read also `README.md` and any relevant documentation it references.
* Draft a detailed, step-by-step blueprint for building the feature.  
* Break that plan into small, iterative chunks.  
* Refine until each step is:  
  * **Small enough** to implement safely with thorough tests, yet  
  * **Large enough** to move the project forward meaningfully.
* After planning the feature, present the implementation plan to me for approval. 
* You MUST review, understand, design and plan before presenting me the plan. You MUST not start implementing until I accept your plan.

### Implementation

Avoid comments when they are not necessary; add them only when making assumptions, clarifying non-obvious code, or handling edge cases.
Follow code style and existing architecture when possible. If the requested work can be fitted in the existing architecture, follow the code style.
If the requested work is completely new, follow best practices and propose your own architecture.

When asked **only** to refactor existing code (as opposed to adding functionality), avoid changing behaviour and ensure tests continue to pass.

Remember adding or updating the existing documentation after your changes to keep a consistent documentation

# Commit message format

<50-character summary>

Avoid body lines when the commit is reducted.


# Capturing additional guidance

If I interrupt to correct your approach, update this document so future sessions retain the guidance. Always ask for permission before adding new general-purpose prompts.


# User input (details about the feature)

$ARGUMENTS

