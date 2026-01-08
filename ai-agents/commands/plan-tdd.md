---
description: Implement TDD contribution
allowed-tools: Grep, Read, LS, Find, Bash(glab issue view:*), Bash(glab issue view:*), Bash(git checkout:*), Bash(git pull:*)
---

This document describes the development practices and principles you **must** follow.  
Do **not** start implementing features until explicitly asked. Use this guide to get into the right state of mind.

# Workflow

## High-level steps

1. Start from `master` or `main` (unless told to work on a different branch).
2. Follow plan mode. Do not modify anything, just plan.
3. Present me this plan and the code architecture in the screen, do not create extra files.
The code architecture must be presented as a block diagram with the different entities.
Lay out the implementation plan as numbered Step X sections, each with indented sub-bullets for the details. 
Lay out a change list with the changes per file / feature.
4. Once approved, follow development flow (Red -> Green -> Refactor)

## How to implement

### Plan mode

* Read the related code, undersand what need. Ask me questions if required. Read also `README.md` and any relevant documentation it references.
* If the contribution is big and it contains changes in many codebase features (i.e. server, n2k, etc.) draft the proposed code architecture, how new code fits in the existing codebase.
* Draft a detailed, step-by-step blueprint for building the feature.  
* Break that plan into small, iterative chunks.  
* Refine until each step is:  
  * **Small enough** to implement safely with thorough tests, yet  
  * **Large enough** to move the project forward meaningfully.
* Ask me any question you need about the architecture, how to implement or any doubt you have. Do not invent or hallucinate, ask if needed.
* You MUST review, understand, design and plan before presenting me the plan. You MUST not start implementing.
* Complete the full analysis and planning, only present me when you have completed your planning mode.


### Development flow (Red → Green → Refactor)

1. **Red** – Write a failing test that captures the new desired behaviour.  
   * Run the test: it **must fail**.  
   * Do **not** change production code during this phase.  

2. **Green** – Implement the simplest code that makes **all tests pass**.  
   * Do **not** modify tests here.  
   * Commit to git **only when the full test suite passes** (do not push yet).  

3. **Refactor** – Improve the code you just wrote—and any related code—without changing behaviour.  
   * For minor refactors, one commit is enough; for larger ones, commit in logical stages.  
   * Commit only when tests pass.  

Repeat this loop, one new test at a time, until the feature is complete.

---

# Commit message format

<50‑character summary>

Avoid body lines when the commit is reducted.

---

## Pure refactors

When asked **only** to refactor existing code (as opposed to adding functionality), you do **not** begin with a new failing test—refactoring should not change behaviour.

---

# Capturing additional guidance

If I interrupt to correct your approach, update this document so future sessions retain the guidance. Always ask for permission before adding new general-purpose prompts.


# Extra user input

Follow the following extra user input when available:

$ARGUMENTS
