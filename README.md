# Agent Markdown Memory Bank Protocol

A lightweight protocol for AI coding agents (GitHub Copilot, Cursor, etc.) to maintain persistent project context across sessions using a structured `.memory-bank/` directory.

## What is AGENTS.md?

`AGENTS.md` is a root-level instruction file that AI agents automatically read to understand how to behave in this repository. It enforces two core protocols:

### 1. Memory Bank Protocol

The agent maintains a `.memory-bank/` directory as its single source of truth, containing:

| File | Purpose |
|---|---|
| `product-context.md` | Project goal and purpose |
| `active-context.md` | Current focus and next steps |
| `system-architecture.md` | Architectural patterns and decisions |
| `progress.md` | Timestamped journal of completed work |

**Workflow:**
1. **Before any task** — read `product-context.md`, `active-context.md`, `system-architecture.md`
2. **During a task** — update `system-architecture.md` immediately on architectural changes
3. **After every task** — append a timestamped entry to `progress.md`, update `active-context.md` with next steps

The agent runs `date '+%Y-%m-%d %H:%M'` to get an accurate timestamp rather than guessing.

### 2. Todo Workflow

When asked to pick up the next task, the agent reads the `Next Steps (unsorted)` section in `active-context.md` and recommends the top 3 items.

## Mandatory Completion Checklist

Every session that involves code changes MUST end with:
- [ ] Append entry to `.memory-bank/progress.md`
- [ ] Update `.memory-bank/active-context.md`
- [ ] Confirm memory bank update to the user

## Usage

Drop `AGENTS.md` into the root of any repository. AI agents that support root-level instruction files (Copilot with `AGENTS.md`, Cursor with `.cursorrules`, etc.) will automatically pick it up and follow the memory bank protocol.
