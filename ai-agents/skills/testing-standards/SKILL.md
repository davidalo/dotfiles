---
name: testing-standards
description: Testing expectations and TDD workflow. Use when adding or changing behavior.
---

# Testing Standards

## Instructions
- Tests must cover all implemented functionality.
- Never ignore system or test output; logs often contain critical info.
- Test output must be pristine.
- Capture and assert expected errors in logs.
- No exceptions: every project requires unit, integration, and end-to-end tests unless I say exactly:
  "I AUTHORIZE YOU TO SKIP WRITING TESTS THIS TIME."

## TDD Essentials
- Write tests before implementation.
- Write only enough code to pass the failing test.
- Refactor continually while tests stay green.
- See `commands/tdd.md` for details.
