# Power BI Change Request Approval Reporting

Streamlined managed repository for **Change Request (CR) Approval Reporting** in Power BI.

## Executive Summary
This reporting solution shows where change requests are in the approval lifecycle, where delays occur, and what actions leaders can take to improve throughput and control risk.

**Primary decisions this report supports:**
- Are approvals meeting SLA targets?
- Which teams, approvers, or CR types are creating bottlenecks?
- Which high-risk or high-impact requests need escalation now?
- Are approval outcomes trending healthier or degrading over time?

## Open Clarifications (Needed)
To finalize implementation details, confirm these items:
1. Source systems and table names (e.g., ServiceNow/Jira/ADO exports, SQL views).
2. Final SLA rules (business vs. calendar time, pause conditions, priority-specific SLA).
3. Standard approval statuses and transition logic.
4. Required row-level security model (by team, app, region, business unit).
5. Executive KPI definitions and thresholds (Green/Amber/Red).

## Repository Structure
```text
/
├─ README.md
├─ docs/
│  ├─ executive-summary.md
│  ├─ team-workflow.md
│  └─ report-spec.md
└─ powerbi-authoring/
   ├─ copilot-spec.yaml
   └─ prompts/
      └─ report-context.md
```

## Quick Start (VS Code + Copilot)
1. Open this repository in VS Code.
2. Install the required `/powerbi-authoring` plugin/extension in your environment.
3. Review:
   - `/docs/report-spec.md`
   - `/powerbi-authoring/copilot-spec.yaml`
   - `/powerbi-authoring/prompts/report-context.md`
4. Use these files as source context for AI-assisted implementation and incremental feature work.

## What Is Included
- **Executive-friendly summary** of what the report shows and why it matters.
- **AI-ingestible specification** for Copilot-guided development.
- **Small-team branch and delivery model** for incremental enhancements.

## Branching and Delivery (Small Team)
- `main`: production-ready baseline.
- `feature/<short-scope>`: small, reviewable increments.
- PR checklist: updated spec impact, validation evidence, leadership-facing summary if KPI logic changes.

Detailed workflow is in `/docs/team-workflow.md`.
