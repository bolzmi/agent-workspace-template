# Agent Workspace Starter

A vendor-neutral, Git-backed workspace for handing projects between ChatGPT, GitHub Copilot, Codex, Claude, local models, and future agents.

## Design goals

1. **Git is the durable source of truth.**
2. **AGENTS.md is the canonical standing instruction file.**
3. Stable rules are separated from changing project state.
4. Every agent begins by reading a small, predictable set of files.
5. Every substantial work session ends with a written handoff.
6. Vendor-specific instruction files are thin compatibility layers, not separate sources of truth.
7. Conversation history is useful context, but is never the only record of an important decision.

## Start-of-session reading order

1. `AGENTS.md`
2. `STATE.md`
3. `TASKS.md`
4. `HANDOFF.md`
5. Only then read `DECISIONS.md`, `docs/`, source files, or prior session notes as needed.

## Closeout order

Before ending substantial work:

1. Update `STATE.md` if system/project state changed.
2. Update `TASKS.md`.
3. Add durable decisions to `DECISIONS.md`.
4. Replace `HANDOFF.md` with a concise handoff for the next agent.
5. Add a short entry to `SESSION_LOG.md` for material work.
6. Commit changes when appropriate.

See `docs/AGENT_PROTOCOL.md` for the full protocol.

## Files

- `AGENTS.md` — canonical cross-agent operating instructions.
- `STATE.md` — current truth: what works, what is broken, what changed.
- `TASKS.md` — compact queue: Now / Next / Later / Blocked.
- `HANDOFF.md` — latest session handoff; intentionally overwritten.
- `DECISIONS.md` — durable architectural/business decisions and why they were made.
- `SESSION_LOG.md` — lightweight historical ledger of material sessions.
- `docs/` — stable project documentation.
- `.github/copilot-instructions.md` — Copilot compatibility layer.
- `.github/prompts/handoff.prompt.md` — reusable Copilot handoff prompt.
- `agent-workspace.json` — simple machine-readable project manifest.

## Recommended GitHub use

Use a **private repository** for company/internal projects. Clone only the repos/folders you want on each machine. The authoritative context remains in GitHub, so another machine or agent can resume after pulling the repository.

Do not put credentials, tokens, passwords, private keys, or regulated/confidential data in these context files unless the repository and company policy explicitly permit it.
