---
description: Implement GitHub PR or GitLab MR review comments
argument-hint: PR_ID=<pr_id> GITHUB_OR_GITLAB=<GITHUB>
---

This document describes the development practices and principles you **must** follow.  
Do **not** start implementing features until explicitly asked. Use this guide to get into the right state of mind.

# Workflow

## High-level steps

1. Start from the related branch, we MUST implement changes on that branch. Checkout that branch ALWAYS.
2. Retrieve the contribution details and the comments. 
3. Follow how to. Do not push commits, just create them and let me review them before pushing.

## Retrieve contribution details

This is a $GITHUB_OR_GITLAB issue, run the appropriate command:

## GitLab

Use `glab mr view $PR_ID -c -F json --page <page_number> --per-page <items_per_page>`.
The comments inside this json are in section "Notes" and have type "DiffNote".
Iterate over all the pages to get all the comments.

Filter for unresolved comments:
```bash
glab mr view $PR_ID -c -F json --page <page_id> --per-page 200 | jq '[.Notes[] | select(.resolvable == true and .resolved == false) | {body: .body, position: .position, resolved: .resolved, resolvable: .resolvable, created_at: .created_at}]'
```

## GitHub

Identify the owner and the repo name.

### Option 1: Get ALL review comments (REST API)
Use this when you want to see all comments regardless of resolution status:

```bash
gh api repos/<owner-name>/<repo-name>/pulls/$PR_ID/comments --jq '[.[] | {id, author: .user.login, body, path: .path, line: .line, created_at, updated_at}]'
```

### Option 2: Get ONLY UNRESOLVED comments (GraphQL API)
Use this when you specifically need unresolved review threads:

```bash
gh api graphql -f query='
{
  repository(owner: "<owner-name>", name: "<repo-name>") {
    pullRequest(number: $PR_ID) {
      reviewThreads(first: 50) {
        nodes {
          id
          isResolved
          comments(first: 10) {
            nodes {
              id
              author {
                login
              }
              body
              path
              line
            }
          }
        }
      }
    }
  }
}' --jq '.data.repository.pullRequest.reviewThreads.nodes[] | select(.isResolved == false) | {isResolved, comment: .comments.nodes[0] | {id, author: .author.login, body, path, line}}'
```

**Note**: The REST API (`/pulls/PR/comments`) does NOT expose resolution status. You MUST use GraphQL to filter by resolved/unresolved status.
Both CLI tools accept an ID and display the full metadata. You are allowed to run these commands with internet access.

## How to 

* Draft a detailed, step-by-step plan for all the comments.
* Break that plan into small, iterative chunks. If several comments are related, merge them into one step.   
* Always look into the review comments with **fresh eyes**, you can disagree with the reviewer. 
* Before implementing, prepare a detailed plan and present that to me for approval. Include your opinion about the changes.
* Implement each contribution (one or multiple review comments) into a different commit after my approval

# Commit message format

<50-character summary>

Avoid body lines when the commit is reducted.

# Capturing additional guidance

If I interrupt to correct your approach, update this document so future sessions retain the guidance. Always ask for permission before adding new general-purpose prompts.


# Extra user input

Follow the following extra user input when available:

$ARGUMENTS
