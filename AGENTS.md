# Agent Instructions

This file is the canonical standing instruction source for all AI agents working in this repository.

## Mission

Help advance this project safely, efficiently, and with minimal unnecessary change. Preserve working systems and documented decisions unless the task explicitly requires changing them.

## Required startup protocol

Before substantial work:

1. Read `STATE.md`.
2. Read `TASKS.md`.
3. Read `HANDOFF.md`.
4. Read relevant entries in `DECISIONS.md` and `docs/` only as needed.
5. Inspect the authoritative source/system before making claims about current state.

Do not rely on prior chat/session memory when repository state can answer the question.

## Operating principles

- Prefer the smallest reliable change that satisfies the task.
- Diagnose before modifying.
- Do not refactor, redesign, or clean up unrelated components unless explicitly asked.
- Preserve existing working behavior unless change is necessary.
- Distinguish verified facts from assumptions.
- If evidence is incomplete or contradictory, say so instead of guessing.
- Prefer reversible changes.
- Never expose or commit secrets.
- Follow existing project conventions before inventing new ones.
- Treat source data and operational systems identified in `STATE.md` or `docs/` as authoritative.
- Keep context files concise. Link to detailed documentation instead of duplicating it.

## Agent portability

Do not assume a particular vendor, model, IDE, operating system, or agent runtime unless this repository explicitly requires one.

Avoid instructions such as "use ChatGPT Work" or "use Claude Code" in canonical project rules. Vendor-specific behavior belongs in a vendor compatibility file.

## Before editing

State, internally or to the user when useful:

- what evidence you inspected,
- what you believe the problem/task is,
- what files/systems you intend to change,
- how you will validate the result.

For small obvious changes, keep this lightweight.

## Validation

A task is not complete merely because files were edited.

Use the project's available validation method: tests, dry runs, linting, generated output checks, API checks, or direct inspection. Do not claim validation occurred if it did not.

## Closeout protocol

Before ending substantial work:

1. Update `STATE.md` with material current-state changes.
2. Update `TASKS.md`.
3. Record durable decisions in `DECISIONS.md`.
4. Replace `HANDOFF.md` with a compact handoff.
5. Append one concise entry to `SESSION_LOG.md`.
6. Note validation performed and remaining uncertainty.

See `docs/AGENT_PROTOCOL.md`.

## File ownership

- `AGENTS.md`: stable operating rules. Change rarely.
- `STATE.md`: current state. Keep short and current.
- `TASKS.md`: task queue. Keep actionable.
- `HANDOFF.md`: most recent handoff. Replace, do not endlessly append.
- `DECISIONS.md`: append durable decisions; do not rewrite history casually.
- `SESSION_LOG.md`: append brief historical entries.
- `docs/`: stable reference material.

## Safety / secrets

Never write passwords, API keys, OAuth refresh tokens, session cookies, private keys, or other credentials into repository files or logs.

If a task requires a secret, use the project's approved secret-management mechanism and document only the secret's name/purpose, never its value.
