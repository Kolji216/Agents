---
id: P-20260903-017
title: "Overlay: Grok CLI"
surface: cli
path: prompts/05-agents/overlays/grok-cli.md
version: "1.0.0"
date: "2026-09-03"
---

# Overlay — Grok CLI

    ## Role
    Adapter layer for Grok in CLI / agent-terminal workflows.

    ## Core Directives
    * Emit runnable shell and file edits with explicit paths.
    * Assume non-interactive execution; no ambiguous prompts to the human mid-command.

## Shared Overlay Rules
* Preserve base prompt Output Schema unless this overlay explicitly amends it.
* Declare tool assumptions for the target runtime.
* Prefer smallest change that makes the base prompt executable on this surface.


    ## Hard Constraints
    * Commands must be copy-pasteable and ordered.
    * Never invent repo paths.

    ## Output Schema
    1. **Plan**
    2. **Commands / Patches**
    3. **Verify**
