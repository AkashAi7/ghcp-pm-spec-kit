# Persona-Wise TODO Work Items
# Project: [PROJECT NAME]

| Field | Value |
|-------|-------|
| **Version** | 1.0 |
| **Date** | [DATE] |
| **WBS Reference** | `output/04-wbs-[project-name].md` |
| **TDD Reference** | `output/03-tdd-[project-name].md` |

---

## Summary Dashboard

| Persona | Total Tasks | Total SP | Sprints |
|---------|------------|---------|---------|
| Frontend Engineer | [X] | [X] | Sprint 1–4 |
| Backend Engineer | [X] | [X] | Sprint 1–4 |
| Data Engineer | [X] | [X] | Sprint 1–4 |
| Data Analyst | [X] | [X] | Sprint 2–4 |
| SRE / Cloud Engineer | [X] | [X] | Sprint 1–4 |

---

## 👩‍💻 Frontend Engineer

### TODO-FE-001 · [Task Title]
- **Persona**: Frontend Engineer
- **Phase**: [Phase number and name]
- **Sprint**: Sprint [X]
- **Story Points**: [X]
- **Labels**: `frontend`, `[feature-area]`, `sprint-[X]`
- **WBS Ref**: WBS-[XXX]
- **FSD Ref**: FSD-FR-[XX]
- **TDD Ref**: TDD-COMP-[XX]

**Description**
[Clear description of what needs to be built. Reference relevant screen from the UI prototype wireframes.]

**Acceptance Criteria**
- [ ] [Criterion 1 — testable, specific]
- [ ] [Criterion 2]
- [ ] [Criterion 3 — error/edge case]
- [ ] Component has unit tests with ≥ 80% coverage

---

### TODO-FE-002 · [Task Title]
[Repeat pattern]

---

## ⚙️ Backend Engineer

### TODO-BE-001 · [Task Title]
- **Persona**: Backend Engineer
- **Phase**: [Phase number and name]
- **Sprint**: Sprint [X]
- **Story Points**: [X]
- **Labels**: `backend`, `[feature-area]`, `sprint-[X]`
- **WBS Ref**: WBS-[XXX]
- **FSD Ref**: FSD-FR-[XX]
- **TDD Ref**: TDD-API-[XX]

**Description**
[What API endpoint(s) / service(s) / module(s) to build. Reference TDD API Catalogue.]

**Acceptance Criteria**
- [ ] `[HTTP Method] [path]` returns `[status code]` with `[response shape]`
- [ ] Input validation rejects `[bad input]` with `[error code]`
- [ ] Business rule: [specific rule]
- [ ] Integration test covers happy path and [X] error scenarios
- [ ] OpenAPI spec updated to reflect new endpoint

---

### TODO-BE-002 · [Task Title]
[Repeat pattern]

---

## 🗄️ Data Engineer

### TODO-DE-001 · [Task Title]
- **Persona**: Data Engineer
- **Phase**: [Phase number and name]
- **Sprint**: Sprint [X]
- **Story Points**: [X]
- **Labels**: `data-engineering`, `[azure-service]`, `sprint-[X]`
- **WBS Ref**: WBS-[XXX]
- **TDD Ref**: TDD-DB-[XX]

**Description**
[Description — e.g., database migration, ADF pipeline, Fabric workspace setup, schema definition]

**Acceptance Criteria**
- [ ] [Schema / migration] deployed to Dev + QA environments without errors
- [ ] [Pipeline] runs successfully end-to-end with sample data
- [ ] Data quality check: [specific validation rule]
- [ ] [Table / entity] matches the data dictionary in FSD section 5
- [ ] Pipeline alerts configured for failure notification

**Azure Services Involved**
- [ ] Azure SQL Database / Cosmos DB
- [ ] Azure Data Factory
- [ ] Microsoft Fabric / Synapse
- [ ] Azure Storage Account

---

### TODO-DE-002 · [Task Title]
[Repeat pattern]

---

## 📊 Data Analyst

### TODO-DA-001 · [Task Title]
- **Persona**: Data Analyst
- **Phase**: [Phase number and name]
- **Sprint**: Sprint [X]
- **Story Points**: [X]
- **Labels**: `data-analytics`, `power-bi`, `sprint-[X]`
- **WBS Ref**: WBS-[XXX]
- **FSD Ref**: FSD-FR-[XX]

**Description**
[Description — e.g., Power BI report design, DAX measure creation, KPI definition, notebook analysis, data validation]

**Acceptance Criteria**
- [ ] Report connects to [data source] and loads within [X] seconds
- [ ] KPI: "[Metric name]" matches business definition: [formula]
- [ ] DAX measure `[MeasureName]` is peer-reviewed and validated
- [ ] Row-level security (RLS) restricts data to correct user groups
- [ ] Report is published to Power BI workspace and shared with Finance team
- [ ] Mobile layout configured for key visuals

**Visuals to Include**
- [ ] [Chart type 1] showing [metric] by [dimension]
- [ ] [Chart type 2] for [trend/comparison]
- [ ] KPI card(s) for [metric 1], [metric 2]
- [ ] Slicer(s): [date range], [department], [status]

---

### TODO-DA-002 · [Task Title]
[Repeat pattern]

---

## ☁️ SRE / Cloud Engineer

### TODO-SRE-001 · [Task Title]
- **Persona**: SRE / Cloud Engineer
- **Phase**: [Phase number and name]
- **Sprint**: Sprint [X]
- **Story Points**: [X]
- **Labels**: `infrastructure`, `azure`, `devops`, `sprint-[X]`
- **WBS Ref**: WBS-[XXX]
- **TDD Ref**: TDD-7 (Azure Resource Map)

**Description**
[Description — e.g., Bicep templates, GitHub Actions pipeline, Azure Monitor alerts, networking setup, Key Vault configuration]

**Acceptance Criteria**
- [ ] All Azure resources provisioned via Bicep (no manual portal clicks)
- [ ] Bicep template deploys idempotently (`what-if` shows no changes after apply)
- [ ] All secrets stored in Azure Key Vault — no hardcoded credentials
- [ ] Resource tags applied: `environment`, `project`, `cost-centre`, `owner`
- [ ] CI/CD pipeline: [specific pipeline stage] passes on PR to `develop`
- [ ] [Alert rule] fires when [condition] (tested in Dev environment)

**Bicep Resources to Define**
```bicep
// Resources to create:
// - [resourceType] named [resourceName]
// - [resourceType] named [resourceName]
```

**GitHub Actions Steps**
- [ ] `build` job: build + unit test
- [ ] `deploy-qa` job: deploy to QA slot on merge to develop
- [ ] `deploy-prod` job: deploy to prod after manual approval gate

---

### TODO-SRE-002 · [Task Title]
[Repeat pattern]

---

## Master Checklist (Quick Reference)

### Frontend Engineer
- [ ] TODO-FE-001 · [Task] ([X]SP, Sprint [X])
- [ ] TODO-FE-002 · [Task] ([X]SP, Sprint [X])

### Backend Engineer
- [ ] TODO-BE-001 · [Task] ([X]SP, Sprint [X])
- [ ] TODO-BE-002 · [Task] ([X]SP, Sprint [X])

### Data Engineer
- [ ] TODO-DE-001 · [Task] ([X]SP, Sprint [X])
- [ ] TODO-DE-002 · [Task] ([X]SP, Sprint [X])

### Data Analyst
- [ ] TODO-DA-001 · [Task] ([X]SP, Sprint [X])
- [ ] TODO-DA-002 · [Task] ([X]SP, Sprint [X])

### SRE / Cloud Engineer
- [ ] TODO-SRE-001 · [Task] ([X]SP, Sprint [X])
- [ ] TODO-SRE-002 · [Task] ([X]SP, Sprint [X])

---

## GitHub Issues Export

Use the blocks below to create GitHub Issues directly.
Copy each block, go to your GitHub repository → Issues → New Issue → paste content.

```
---
Title: TODO-FE-001 · [Task Title]
Labels: frontend, [feature], sprint-1
Milestone: Sprint 1
Assignee: @[github-username]

## Description
[Description text]

## Acceptance Criteria
- [ ] [Criterion 1]
- [ ] [Criterion 2]

## References
- WBS: WBS-[XXX]
- FSD: FSD-FR-[XX]
- TDD: TDD-COMP-[XX]
---
```

---

*Generated by GitHub Copilot PM Spec-Kit*
