# Session Manager Concepts We Adopt

Inspired by agent-neutral session-management patterns, without requiring a local process-control dashboard.

## Adopt now

### Agent-neutral core
Canonical project knowledge is not tied to one agent.

### Durable ledger
`SESSION_LOG.md` records material sessions at a high level.

### Explicit closeout
A session is not considered cleanly handed off until the closeout files are updated.

### Shared work state
`STATE.md`, `TASKS.md`, and `HANDOFF.md` make the next agent independent of proprietary transcript history.

### Rules as files
Standing behavior lives in version-controlled files rather than only in prompts.

### One authority per fact
Each type of information has an intended home to reduce conflicting copies.

## Defer

### Live process/liveness tracking
Useful mainly for multiple local terminal agents running concurrently.

### Transcript import/indexing
Potential Phase 2 if local agents become common.

### Usage meters and context-window dashboards
Useful later, but not needed for portable handoffs.

### Automated cross-agent launching/resuming
Potential future local session manager, but Git + handoff files solve the immediate portability problem.

## Future trigger for Phase 2

Consider a true session manager when:
- multiple CLI agents run concurrently,
- losing track of live sessions becomes common,
- proprietary transcript search becomes valuable,
- automatic cross-agent launching would save meaningful time.
