# Multi-Model Routing

| Job | Preferred Surface | Suggested Base | Overlay |
| :--- | :--- | :--- | :--- |
| Venture / strategy critique | chatbot | P-20260903-007 | grok-chat |
| Epistemic research | chatbot | P-20260903-008 | grok-chat |
| Creative prose / Imagine | chatbot | P-20260903-009 | grok-chat |
| Truth / anti-sycophancy | chatbot | P-20260903-010..013 | — |
| Software implementation | cli | P-20260903-014 | cursor-agent / claude-code / openai-codex / grok-cli |
| CAD + additive | cli | P-20260903-015 | grok-cli |
| Prompt hardening | both | P-20260903-027 | — |

## Handoff Pattern
Chatbot (Phase 0–1) → freeze acceptance tests → CLI (Phase 2 + coding engine) → Red-team auditor on any new system prompts.
