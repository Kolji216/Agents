# Prompt Library & Multi-Model Routing System

Repo: [Kolji216/Agents-such](https://github.com/Kolji216/Agents-such)

## Purpose
Dual-surface prompt library: **Chatbot** (plan, critique, eval) and **CLI** (implement, debug, verify).

## Surface Matrix
| Surface | Primary Role | Target Models / Tools | Primary Assets |
| :--- | :--- | :--- | :--- |
| **Chatbot** | Planning, Architecture, Tradeoffs, Eval Design | Grok Chat, Claude (Web) | `prompts/03-chatbot-planning/` |
| **CLI** | Implementation, Testing, Refactoring, Verification | Claude Code, OpenAI Codex, Cursor Agent | `prompts/04-cli-coding/` |
| **Both / Meta** | Catalog, phases, variants, overlays, eval | All | `prompts/00-meta/`, `05-agents/`, `06-phases/`, `07-variants/`, `08-eval/` |

## Quick Start
1. Open [INDEX.md](INDEX.md) for IDs `P-20260903-001` … `028`.
2. Pick one base prompt by surface.
3. Optionally add one overlay from `prompts/05-agents/overlays/`.
4. Multi-step: Phase 0 Discover → Phase 1 Design freeze → Phase 2 Implement.
5. Catalog bot: `P-20260903-028` (`prompts/00-meta/library-steward-bot.md`).

## Sibling tree
**Kanae** (disk agent) lives in [`../disk-steward/`](../disk-steward/README.md). Pathway: [`../disk-steward/docs/PATHWAY.md`](../disk-steward/docs/PATHWAY.md). Do not merge.

## Catalog Snapshot
28 prompts indexed. See INDEX.md.
