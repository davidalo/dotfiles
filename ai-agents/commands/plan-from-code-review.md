---
allowed-tools: [Grep, Read, LS, mcp__github__*, mcp__gitlab__*, Bash(git checkout:*)]
description: Implement GitHub PR or GitLab MR review comments
---

Use these skills and do not restate their rules:
- `skills/coding-standards/SKILL.md`
- `skills/testing-standards/SKILL.md`
- `skills/git-guidelines/SKILL.md`
Follow `skills/git-guidelines/SKILL.md` for commit message format.

Do not start implementing features until explicitly asked.

# Workflow

## High-level steps

1. Start from the related branch; changes must be implemented on that branch. 
Always check out to the related branch if you are not already on it. 
Use `git fetch` and `git checkout <branch-name>`, use the branch name from the PR.
2. Retrieve the contribution details and comments.
3. Assess the code review comments and the comments on the GitHub issue.
4. Present me the assesment, ask for approval before making any change.
4. Implement changes
5. Do not push commits; create them and let me review them before pushing.

### Retrieve contribution details

An MR/PR URL or its ID will be provided in the arguments. If it is missing, ask for it before proceeding.

Use the URL to determine whether the target is GitHub or GitLab, then use the corresponding MCP server to retrieve the contribution details and review comments.

- GitHub: use the GitHub MCP to fetch PR details, review comments, and review threads. Prefer unresolved comments when the tool exposes resolution status; otherwise collect all comments and note the limitation.
- GitLab: use the GitLab MCP to fetch MR details and discussion notes, filtering for unresolved threads when possible.

Capture comment metadata (author, body, file path, line, timestamps) whenever the MCP tool provides it.

### Assess the code review

* Group the related comments if related. If several comments are related, they must 
be assesed and implemented them together as a single contribution.
* Review group of comments, one by one. You must assess if the review is fair, you can disagree with the reviewer.
* Prepare a report: include the comment, who made it and pointing to which code, your decision (APPROVE REJECT or similar wording), and a brief description about your decision and the comment itself.


### Implement changes

* If several comments are related, implement them together as a single contribution.
* Implement each contribution (one or multiple review comments) as a separate commit.

## Capturing additional guidance

If I interrupt to correct your approach, update this document so future sessions retain the guidance. Always ask for permission before adding new general-purpose prompts.

# Extra user input

Follow the following extra user input when available:

$ARGUMENTS
