# AGENTS.md — How Agents Should Use This Library

## Routing
* **Plan / critique / research** → `prompts/03-chatbot-planning/` (+ optional chatbot overlay).
* **Implement / debug / refactor** → `prompts/04-cli-coding/` (+ CLI overlay).
* **Multi-step work** → `prompts/06-phases/` in order.
* **Shape of attack** → pick a `prompts/07-variants/` profile.
* **Harden prompts** → `prompts/08-eval/red-team-auditor.md`.

## Composition
1. Load base prompt by INDEX ID.
2. Append one overlay max unless composing chatbot plan → CLI implement handoff.
3. Keep YAML `id` in citations when reporting which prompt was used.

## Non-Negotiables
* Do not invent APIs, facts, or URLs.
* Prefer Missing Data Protocol over guessing.
* Do not open Finder or kill unrelated processes from agent sessions.
