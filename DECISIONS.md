# Decision Log

Record decisions that should survive individual sessions. Keep entries concise.

---

## ADR-0001 — Adopt agent-neutral Git workspace

**Date:** YYYY-MM-DD  
**Status:** accepted

### Decision

Use repository files as the durable cross-agent source of truth. `AGENTS.md` holds canonical standing instructions; changing state and handoff information live in separate files.

### Why

This reduces dependence on any one AI vendor or conversation history and enables clean handoffs between agents and machines.

### Consequences

- Agents must read the startup files.
- Material sessions should perform closeout.
- Vendor-specific instruction files should remain compatibility layers rather than independent policy sources.

---
