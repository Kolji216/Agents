# AGENTS.md — How Agents Should Use This Library

Catalog bot display name: **Shinobu**. Disk bot: **Kanae**.

## How to pick a P-id (Cursor)

1. Open `INDEX.md` in this folder.
2. Match job → surface: chatbot plan, cli implement, both phases/eval, meta catalog.
3. Load **one** base file by id `P-20260903-xxx`.
4. Append **at most one** overlay from `prompts/05-agents/overlays/` for the runtime.
5. Phased work: `021` Discover → `022` Design freeze → `023` Implement.
6. Cite the id in sentence one.
7. Disk / Downloads hygiene is **Kanae**, not this library.

## Routing
* **Plan / critique / research** → `prompts/03-chatbot-planning/` (+ optional chatbot overlay).
* **Implement / debug / refactor** → `prompts/04-cli-coding/` (+ CLI overlay).
* **Multi-step work** → `prompts/06-phases/` in order.
* **Shape of attack** → pick a `prompts/07-variants/` profile.
* **Harden prompts** → `prompts/08-eval/red-team-auditor.md`.
* **Edit this catalog** → Shinobu / `P-20260903-028`.

## Composition
1. Load base prompt by INDEX ID.
2. Append one overlay max unless composing chatbot plan → CLI implement handoff.
3. Keep YAML `id` in citations when reporting which prompt was used.

## Non-Negotiables
* Do not invent APIs, facts, or URLs.
* Prefer Missing Data Protocol over guessing.
* Do not open Finder or kill unrelated processes from agent sessions.
