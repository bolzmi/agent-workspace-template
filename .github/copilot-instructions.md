# GitHub Copilot Repository Instructions

The canonical cross-agent instructions for this repository are in `AGENTS.md`.

Before substantial work, read:
1. `AGENTS.md`
2. `STATE.md`
3. `TASKS.md`
4. `HANDOFF.md`

Key requirements:
- Prefer the smallest reliable change.
- Diagnose before modifying.
- Do not refactor unrelated components.
- Verify current state from authoritative sources.
- Validate changes before claiming success.
- Never commit secrets.
- At the end of substantial work, follow the closeout protocol in `docs/AGENT_PROTOCOL.md`.

If these instructions conflict with `AGENTS.md`, treat `AGENTS.md` as canonical unless a platform-level policy requires otherwise.
