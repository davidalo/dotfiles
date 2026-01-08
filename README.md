## Description

My personal dotfiles for working with Claude Code and Codex.
All AI agent assets live in the agents directory alongside `AGENTS.md`, `commands/`, and `skills/`.

Claude Code commands and Codex prompts are equivalent but use their own syntax.

## Getting started

How to install:

Run these commands from the agents directory (the one that contains `AGENTS.md`, `commands/`, and `skills/`).

```bash
# Claude Code
ln -sf $(pwd)/AGENTS.md ~/.claude/CLAUDE.md
ln -sf $(pwd)/commands ~/.claude/commands
ln -sf $(pwd)/skills ~/.claude/skills

# Codex
ln -sf $(pwd)/commands ~/.codex/prompts
ln -sf $(pwd)/AGENTS.md ~/.codex/AGENTS.md
ln -sf $(pwd)/skills ~/.codex/skills
```

## Notes about plan mode

Claude Code typically do not require using plan commands, just by switching on plan mode is enough.
However, Codex CLI do not have plan mode and we should force planning by a prompt. 

My workflow so far when a feature is complex and requires planning: 
* Claude Code: 1 prompt: plan mode on + implementation command
* Codex CLI: 2 prompts: plan + implementation command
