# Agent Session Protocol

This protocol is intentionally vendor-neutral.

## 0. Synchronize when working from a local checkout

Before relying on repository state, determine whether the local checkout is current with its configured remote when that capability is available.

- Fetch/check remote state before substantial work.
- Pull or otherwise synchronize before reading startup context if the remote is ahead and doing so will not overwrite uncommitted local work.
- If local changes or divergence make synchronization unsafe, do not discard work automatically; identify the discrepancy and resolve it deliberately.
- If remote synchronization cannot be checked, state that limitation and treat local state as potentially stale.

This prevents a correct handoff on GitHub from being undermined by an outdated local clone.

## 1. Open

Read, in order:

1. `AGENTS.md`
2. `STATE.md`
3. `TASKS.md`
4. `HANDOFF.md`

Then inspect only the additional files necessary for the assigned task.

### Goal

Begin with the smallest sufficient context rather than replaying old conversations or scanning the entire repository.

## 2. Orient

Before making changes, determine:

- the requested outcome,
- the authoritative source of current truth,
- constraints that must be preserved,
- what changed since the last handoff,
- the smallest likely work surface.

If the handoff conflicts with current repository/system state, current verified state wins. Record the discrepancy.

## 3. Execute

- Prefer focused edits.
- Avoid unrelated refactors.
- Save durable discoveries in repository documentation rather than relying on session memory.
- Use explicit TODOs only when work is genuinely deferred.

## 4. Validate

Use real evidence appropriate to the project.

Examples:

- test suite,
- lint/type checks,
- workflow dry run,
- API response,
- generated artifact inspection,
- direct comparison against expected output,
- human-readable checklist.

Never convert "I changed it" into "it works" without validation.

## 5. Close

At the end of substantial work:

### STATE.md
Update only current truth that materially changed.

### TASKS.md
Move completed work and identify the next actionable item.

### DECISIONS.md
Add an entry only for decisions with future consequences.

### HANDOFF.md
Replace with a concise summary containing:
- objective,
- completed work,
- validation,
- remaining issues,
- exact next action,
- things not to redo.

### SESSION_LOG.md
Append a short historical record.

## 6. Handoff to a different agent

The new agent should not need the old agent's private transcript.

The handoff is successful if the next agent can resume from:
`AGENTS.md` + `STATE.md` + `TASKS.md` + `HANDOFF.md`.

If it cannot, improve those files rather than adding more dependence on proprietary session history.

## 7. Context budget discipline

Keep startup files short.

Suggested targets:
- `AGENTS.md`: under ~2,000 words
- `STATE.md`: under ~1,000 words
- `TASKS.md`: under ~100 active lines
- `HANDOFF.md`: under ~1,000 words

Move stable detail to `docs/` and historical detail to `SESSION_LOG.md`.

## 8. What not to store

Do not store:
- passwords,
- API keys,
- refresh tokens,
- cookies,
- private keys,
- unnecessary personal/sensitive data,
- giant copied chat transcripts.

Reference secure systems and source files instead.
