# Research Notes

## Design Goals
* Maximize truthfulness and density; minimize sycophancy and hallucinated APIs.
* Make chatbot planning artifacts handoff-clean for CLI implementers.
* Keep originals for regression scoring against improved prompts.

## Observations
* Soft "please be helpful" seeds score poorly on fabrication and premise-audit tests.
* Overlays beat forking entire prompts per model when 80%+ of directives are shared.
* Phase gates reduce mid-flight redesign thrash on brownfield work.

## Open Questions
* Automated rubric for P-IDs (lint frontmatter vs INDEX).
* Whether Fusion360 specialist should also expose a pure chatbot teaching mode.
