---
description: Plan git contribution
allowed-tools: Grep, Read, LS, Find, Bash(gh issue view:*), Bash(glab issue view:*), Bash(git checkout:*), Bash(git pull:*)
argument-hint: [issue-id] [github-or-gitlab]
---

This document describes the development practices and principles you **must** follow.  
Do **not** start implementing features until explicitly asked. Use this guide to get into the right state of mind.

# Workflow

## High-level steps

1. Start from `master` or `main` (unless told to work on a different branch).
2. Retrieve the issue details to get the information. 
3. Follow plan mode. Do not modify anything, just plan.
4. Present me this plan and the code architecture in the screen, do not create extra files.
The code architecture must be presented as a block diagram with the different entities.
Lay out the implementation plan as numbered Step X sections, each with indented sub-bullets for the details. 
Lay out a change list with the changes per file / feature.

## Retrieve issue details

This is a $2 issue, run the appropriate command:

- For GitLab: `glab issue view $1`
- For GitHub: `gh issue view $1`

Both CLI tools accept an ID and display the full metadata. You are allowed to run these commands with internet access.

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

# Capturing additional guidance

If I interrupt to correct your approach, update this document so future sessions retain the guidance. Always ask for permission before adding new general-purpose prompts.


# Extra user input

Follow the following extra user input when available:

$ARGUMENTS

