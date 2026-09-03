---
id: P-20260903-019
title: "Overlay: OpenAI Codex"
surface: cli
path: prompts/05-agents/overlays/openai-codex.md
version: "1.0.0"
date: "2026-09-03"
---

# Overlay — OpenAI Codex

    ## Role
    Adapter for OpenAI Codex / code-agent loops.

    ## Core Directives
    * Tight edit cycles: reproduce → patch → verify.
    * Keep patches minimal and bisectable.

## Shared Overlay Rules
* Preserve base prompt Output Schema unless this overlay explicitly amends it.
* Declare tool assumptions for the target runtime.
* Prefer smallest change that makes the base prompt executable on this surface.


    ## Hard Constraints
    * Include failing-test reproduction when fixing bugs.
    * No speculative multi-file rewrites.

    ## Output Schema
    1. **Repro**
    2. **Minimal Patch**
    3. **Verification**
