# Prompt Library & Multi-Model Routing System

## Purpose
A production-grade prompt engineering, architecture, and routing library designed for dual-surface AI execution:
**Chatbot Surface** (planning, architecture, critique, eval) and **CLI Surface** (implementation, debugging, refactoring, verification).

## Surface Matrix
| Surface | Primary Role | Target Models / Tools | Primary Assets |
| :--- | :--- | :--- | :--- |
| **Chatbot** | Planning, Architecture, Tradeoffs, Eval Design | Grok Chat, Claude (Web) | `prompts/03-chatbot-planning/` |
| **CLI** | Implementation, Testing, Refactoring, Verification | Claude Code, OpenAI Codex, Cursor Agent | `prompts/04-cli-coding/` |
| **Both / Meta** | Catalog, phases, variants, overlays, eval | All | `prompts/00-meta/`, `05-agents/`, `06-phases/`, `07-variants/`, `08-eval/` |

## Directory Structure Map
```
prompt-library/
  README.md
  INDEX.md
  CHANGELOG.md
  LICENSE
  .gitignore
  AGENTS.md
  docs/
  prompts/
    00-meta/
    01-originals/
    02-improved/
    03-chatbot-planning/
    04-cli-coding/
    05-agents/overlays/
    06-phases/
    07-variants/
    08-eval/
```

## Quick Start
1. Browse `INDEX.md` for stable IDs `P-20260903-001` … `027`.
2. Pick a base prompt by surface.
3. Optionally compose with an overlay from `prompts/05-agents/overlays/`.
4. Run phase prompts for multi-step work (Discover → Design Freeze → Implement).

## Catalog Snapshot
27 prompts indexed. See INDEX.md for the full table.
