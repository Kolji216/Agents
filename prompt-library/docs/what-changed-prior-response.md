# What Changed vs Prior Response (8 Seed Modifications)

Gemini's prior seed pack was reshaped into this library. The eight modifications:

1. **Stable ID schema** — Assigned `P-20260903-001` … `027` with YAML frontmatter on every prompt.
2. **Dual-surface split** — Explicit Chatbot vs CLI matrix; coding prompts moved under `04-cli-coding/`.
3. **Originals retained for eval** — Low-scoring archivist drafts archived under `01-originals/` instead of overwritten.
4. **Improved design-only refactor** — Added `02-improved/design-only-refactored-prompt.md` as the hardened successor.
5. **Agent overlays** — Added Grok Chat/CLI, Claude Code, OpenAI Codex, and Cursor Agent adapters.
6. **Phase machine** — Discover → Design Freeze → Implement prompts for gated delivery.
7. **Execution variants** — Spec-first, Spike, and Brownfield profiles for different risk postures.
8. **Catalog & routing docs** — INDEX, AGENTS.md, multi-model routing, inventory, research notes, MIT license, changelog.

## Net Effect
From a flat `AI_Prompts/` agent dump to a versioned, zip-distributable prompt-library with routing and eval hooks.
