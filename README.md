## Description

My personal dotfiles for working with Claude Code and Codex.

Claude Code commands and Codex prompts are equivalent but using their own syntax.

## Getting started

How to install:

```bash
# Claude Code
ln -sf $(pwd)/.claude/CLAUDE.md ~/.claude/CLAUDE.md
ln -sf $(pwd)/.claude/commands ~/.claude/commands

# Codex
ln -sf $(pwd)/.codex/prompts ~/.codex/prompts
```

## Notes about plan mode

Claude Code typically do not require using plan commands, just by switching on plan mode is enough.
However, Codex CLI do not have plan mode and we should force planning by a prompt. 

My workflow so far when a feature is complex and requires planning: 
* Claude Code: 1 prompt: plan mode on + implementation command
* Codex CLI: 2 prompts: plan + implementation command