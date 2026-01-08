---
name: test-driven-development
description: Enforce test-driven development for new features, bug fixes, and behavior changes. Use when asked to implement or modify code with tests, or when the user mentions TDD, red-green-refactor, or "write tests first".
---

# Test-Driven Development

## Core rules
- Do not write production code before a failing test.
- If production code exists before a test, delete it and start from tests.
- Write one behavior per test and use clear, specific test names.
- Prefer real code paths; avoid mocks unless unavoidable.
- Keep test output pristine; investigate any warnings or errors.

## Workflow (Red -> Green -> Refactor)

### Red
- Write the smallest test that expresses the desired behavior.
- Run the relevant test(s) and confirm the test fails for the expected reason.
- If the test passes immediately, fix the test so it fails for the right reason.

### Green
- Write the simplest production code that makes the test pass.
- Do not change the test in this step.
- Run the relevant tests and confirm all pass.

### Refactor
- Clean up code and tests without changing behavior.
- Keep tests green throughout.

## Bug fixes
- Reproduce the bug with a failing test before changing production code.
- Keep the test as a regression guard after the fix.

## Exceptions
- Pure refactors that do not change behavior may skip writing a new failing test.
- Skipping tests requires explicit permission from the user.

## When stuck
- Write the test that describes the desired API and behavior.
- Ask for clarification instead of guessing.

## References
- Before adding mocks, test utilities, or helpers, read `references/testing-anti-patterns.md`.
