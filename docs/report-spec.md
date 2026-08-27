# Report Specification: Change Request Approval Reporting

## 1. Purpose
Provide a single reporting surface for CR approval throughput, SLA adherence, risk exposure, and bottleneck detection.

## 2. Audience
- Executive leadership (portfolio health and risk)
- Change managers (process performance)
- Approval owners (queue management)

## 3. Core Questions
1. Are CR approvals on time against SLA?
2. Where are delays concentrated?
3. Are outcomes improving over time?
4. Which requests require immediate escalation?

## 4. Minimum Data Contract
### Required entities
- `change_request`
  - `cr_id` (string, unique)
  - `created_at` (datetime)
  - `submitted_at` (datetime, nullable)
  - `approved_at` (datetime, nullable)
  - `status` (string)
  - `priority` (string)
  - `risk_level` (string)
  - `request_type` (string)
  - `requesting_team` (string)
- `approval_event`
  - `event_id` (string, unique)
  - `cr_id` (string, FK)
  - `approver` (string)
  - `event_type` (string: submitted/approved/rejected/reassigned)
  - `event_at` (datetime)

## 5. KPI Definitions
- **CR Submitted**: count distinct `cr_id` where submitted exists.
- **CR Approved**: count distinct `cr_id` where status in approved states.
- **Approval Rate**: `CR Approved / CR Submitted`.
- **Median Approval Time**: median of `approved_at - submitted_at` for approved CRs.
- **SLA Attainment %**: percent of approved CRs with approval time <= SLA threshold.
- **Aged Pending Count**: pending CRs older than threshold days.

## 6. Suggested Report Pages
1. **Overview**: KPI cards + trend line + SLA attainment by period.
2. **Bottleneck Analysis**: by approver/team/type with aging buckets.
3. **Risk & Exceptions**: high-risk pending, rejected, and rework indicators.

## 7. Filters
- Date range
- Team
- Priority
- Request type
- Risk level
- Approval status

## 8. Governance
- Refresh cadence: daily (minimum).
- Data quality checks: null IDs, duplicate CR IDs, invalid status values.
- RLS: enforce by approved business owner mapping.
