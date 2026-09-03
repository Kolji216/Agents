# Disk Steward

Local-agent pathway for file organization and defensive hygiene on a machine you own.

This is instruction, not a product app. The agent follows `docs/PATHWAY.md` and only touches paths listed as **in-scope** in `docs/ROOTS_INDEX.md`.

## Start here

1. Set **OS** and **USER_ROOTS** in `docs/ROOTS_INDEX.md` (replace `YOU`).
2. Paste `prompts/system-local-agent.md` into the agent’s standing instructions.
3. Run the pathway in order: Access check → Inventory → Dry-run → your OK → Apply → Verify.
4. Use chips in `chips/` when you want quiet mode or apply-only.

## Files

| Path | Role |
|---|---|
| [docs/PATHWAY.md](docs/PATHWAY.md) | Ordered steps, stop conditions, handoffs |
| [docs/ROOTS_INDEX.md](docs/ROOTS_INDEX.md) | Allowlist / denylist, IDs, what each root is for |
| [docs/what-not-to-touch.md](docs/what-not-to-touch.md) | Hard excludes |
| [prompts/system-local-agent.md](prompts/system-local-agent.md) | Standing instructions |
| [prompts/user-task-template.md](prompts/user-task-template.md) | One-job user message |
| [chips/quiet-mode.md](chips/quiet-mode.md) | Compact output |
| [chips/apply-manifest.md](chips/apply-manifest.md) | Apply approved rows only |
| [chips/explain-on.md](chips/explain-on.md) | Restore explanations |

## Rules in one line

Local agent. Roots allowlist only. Dry-run before move/trash. Quarantine or Trash, not silent unlink. Path+kind for secrets, never contents. Do not invent tool results.
