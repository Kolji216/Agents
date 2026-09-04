# Bot-Builder Agent Workflow

Operation: compose library prompts to plan, freeze, then implement a bot.
Surfaces: Grok Chat (Phase 0–1) → Cursor Agent + Grok Code Engine (Phase 2).
Variant: A — Spec First (`P-20260903-024`).

## Sequence

| Step | Phase | Base | Overlay | Output |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Discover | `P-20260903-021` | `P-20260903-016` Grok Chat | one-page brief |
| 2 | Design freeze | `P-20260903-022` | `P-20260903-016` Grok Chat | spec + acceptance tests |
| 3 | Go / No-Go | `P-20260903-024` | — | implement only if spec complete |
| 4 | Implement | `P-20260903-023` + `P-20260903-014` | `P-20260903-020` Cursor Agent | vertical slices + verify cmds |
| 5 | Eval | `P-20260903-027` | — | red-team new system prompts |

## Composition rules (AGENTS.md)

* One base P-id. At most one overlay (except chatbot→CLI handoff).
* Cite the P-id in sentence one.
* Catalog edits = **Shinobu** (`P-20260903-028`). Disk / Downloads = **Kanae**. Do not merge trees.
* No GitHub push unless the user writes `PUSH TO GITHUB`.
* No Finder. No force-push. No invented APIs.

## Blocking inputs before Phase 1

1. Target of the *built* bot (Discord / Telegram / web / CLI).
2. Host runtime (Cursor vs Grok CLI).
3. First bot to ship.

Phase 0 brief: [phase-0-bot-builder.md](phase-0-bot-builder.md).
