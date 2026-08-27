# Copilot Report Context

Use this context when generating or updating report logic for CR approval reporting.

## Intent
- Keep outputs decision-focused.
- Prefer incremental, branch-based enhancements.
- Avoid adding complexity without measurable value.

## Required outcomes
1. Accurate KPI definitions consistent with `/docs/report-spec.md`.
2. Visuals that explain throughput, SLA, bottlenecks, and risk.
3. Naming and structure understandable by technical and executive stakeholders.

## Guardrails
- Do not change KPI definitions without updating `docs/report-spec.md` and `powerbi-authoring/copilot-spec.yaml`.
- Keep new feature changes isolated and PR-sized.
- Maintain straightforward filter behavior and avoid hidden logic.
