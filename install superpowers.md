# Installing Superpowers

> Source: https://github.com/obra/superpowers

Superpowers is a skills framework that enforces mandatory workflows: brainstorming → git worktree setup → plan writing → subagent-driven execution (with TDD) → code review → branch finishing. Skills trigger automatically based on what you're doing.

## Claude Code

### Option 1: Official Marketplace

```
/plugin install superpowers@claude-plugins-official
```

### Option 2: Superpowers Marketplace

```
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```

## Codex CLI

```
/plugins
```

Search for `superpowers`, then choose **Install Plugin** from the results.

## Codex App

1. Click **Plugins** in the sidebar
2. Find **Superpowers** under the **Coding** section
3. Click the **+** button and follow the prompts

## Notes

- No configuration needed — skills trigger automatically
- If you use multiple agents, install Superpowers separately for each one
- Updates are often automatic (agent-dependent)
- Latest release: **v5.1.0**
- License: MIT
