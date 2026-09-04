# Phase 0 — Bot-Builder Discovery Brief

Ids used: `P-20260903-021` + `P-20260903-016` + `P-20260903-024`.
Date: 2026-09-03. No implementation.

## 1. Goal Statement

Stand up an agent that loads one base P-id plus one overlay, then either plans a bot (chatbot surface) or implements a bot (CLI surface) without inventing APIs, URLs, or signatures.

## 2. Constraints & Non-Goals

* Follow AGENTS.md composition and Missing Data Protocol.
* Not Shinobu. Not Kanae. No disk hygiene. No catalog P-id invention.
* No mid-flight redesign; amendments require a Phase-1 update.
* Non-goals: hosting, billing, voice, multi-platform fan-out on first ship.

## 3. Unknowns

**Blocking**
* Target surface of the built bot (Discord / Telegram / web / CLI).
* Host runtime (Cursor vs Grok CLI).
* First bot to ship.

**Non-blocking**
* Hosting provider, cost, voice, extra channels.

## 4. Recommended Next Phase Gate

Phase 1 Design Freeze (`P-20260903-022` + `P-20260903-016`) after the three blocking items are filled. Then Variant A Go/No-Go (`P-20260903-024`). No code until Go.
