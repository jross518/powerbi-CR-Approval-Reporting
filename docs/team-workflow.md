# Team Workflow (Incremental, Low-Complexity)

## Branch strategy
- Create a branch per scoped enhancement: `feature/<topic>`.
- Keep PRs small and single-purpose.
- Merge to `main` after review and validation evidence.

## Suggested PR checklist
- [ ] Scope statement is clear and limited.
- [ ] Any KPI or metric changes reflected in `docs/report-spec.md`.
- [ ] `powerbi-authoring/copilot-spec.yaml` updated when schema or logic changes.
- [ ] Short test/validation note added to PR description.
- [ ] Leadership summary updated if report meaning changed.

## Increment model
1. Define one enhancement (e.g., new SLA cut, new filter, new KPI card).
2. Update specs first.
3. Implement model/visual changes.
4. Validate with controlled sample slices.
5. Merge and repeat.
