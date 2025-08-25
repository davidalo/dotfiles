---
allowed-tools: [Grep, Read, LS, Bash(git checkout:*), Bash(gh issue view:*), Bash(glab issue view:*), Bash(gh pr view:*), Bash(gh pr diff:*)]
description: Review GitHub PR or GitLab MR
argument-hint: "<mr-pr-number-or-URL>"
---

# Code Review Analysis

Review the contribution identified by **`<ARGUMENTS>`**.
If no MR or PR is provided, try to use `gh pr view --json number` to detect the current PR or the glab cli tool (always try gh first).

---

Follow instructions in @~/.claude/docs/git.md for retrieving the contribution details.

---

## 2 Prepare your review
Using the information returned, produce a report with the following sections:

1. **Summary & Overview** – Concise description of the changes and their purpose  
2. **Code Quality Analysis**  
   * Style consistency and best‑practice adherence. 
   * Potential bugs, logical errors, or anti‑patterns  
   * Error handling and edge‑case coverage  
3. **Security Review** – Possible vulnerabilities or security concerns  
4. **Performance Considerations** – Impact on runtime or resource usage  
5. **Testing Coverage** – Adequacy of new or updated tests  
6. **Documentation** – Whether docs require updates  
7. **Dependencies** – New packages or version changes and their implications  
8. **Architecture & Design** – Alignment with existing project structure  

For the points 2-8,just share details about problems, potential improvement or recomendations. 
Don't add details about things that are OK, just say it's OK.

Review any issues linked in the MR/PR description for additional context and requirements.

Post a comment in the linked PR or MR. That must include that you (Claude) are the reviewer and
your final decision: approve or reject.
If posting the comment fails, just tell me that, do not retry or whatever.

Print your analysis via console for me to read it as well.

> **Important:** Do **not** commit or push code—provide analysis, add recommendations only.

# Extra user input

Follow the following extra user input when available:

$ARGUMENTS