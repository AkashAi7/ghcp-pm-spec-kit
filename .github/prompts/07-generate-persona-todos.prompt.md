---
mode: agent
description: "STEP 7 — Generate persona-wise TODO work items from the WBS. Produces GitHub-Issues-ready task lists for each engineering persona."
---

# Step 7 — Generate Persona-Wise TODO Work Items

## Prerequisites
- `output/04-wbs-<project-name>.md` must exist.
- `output/03-tdd-<project-name>.md` must exist (for tech-specific task detail).
- Template: `templates/persona_todos_template.md`

## Instructions

Read the WBS and TDD from `output/`, then read `templates/persona_todos_template.md`.

Generate a **structured TODO list for each of the five personas**. These should be
GitHub-Issues-ready: clear title, description, acceptance criteria, labels, and story points.

---

## Five Personas (use these EXACT labels)

### 1. `Frontend Engineer`
Responsibilities: React/Angular/Vue components, routing, state management, CSS/Design System, API integration, accessibility (WCAG), unit tests (Jest/Vitest).

### 2. `Backend Engineer`
Responsibilities: REST/GraphQL APIs, business logic, authentication & authorisation, background jobs, unit & integration tests, API documentation (OpenAPI/Swagger).

### 3. `Data Engineer`
Responsibilities: Azure Data Factory pipelines, Microsoft Fabric workspaces, SQL/NoSQL schemas and migrations, data warehouse design, ETL/ELT processes, data quality checks.

### 4. `Data Analyst`
Responsibilities: Power BI reports and dashboards, DAX measures, KPI definitions, notebook-based analysis (Fabric/Databricks), data validation sign-off.

### 5. `SRE / Cloud Engineer`
Responsibilities: Azure resource provisioning (Bicep/ARM/Terraform), GitHub Actions CI/CD pipelines, Azure Monitor alerts, Key Vault secrets, networking (VNet, NSG), cost optimisation tags, disaster recovery runbooks.

---

## Output Format Per Persona

Use this format for each TODO item:

```markdown
### TODO-FE-001 · Implement Login Screen
- **Persona**: Frontend Engineer
- **Phase**: 3 — Development
- **Sprint**: Sprint 1
- **Story Points**: 3
- **Labels**: `frontend`, `auth`, `sprint-1`
- **WBS Ref**: WBS-032
- **FSD Ref**: FSD-FR-03
- **TDD Ref**: TDD-COMP-02

**Description**
Build the Login screen component using the wireframe in `output/06-ui-wireframes-*.md`.
Implement email + password fields, show/hide password toggle, and "Forgot Password" link.

**Acceptance Criteria**
- [ ] Email field validates RFC 5322 format on blur
- [ ] Password field has show/hide toggle
- [ ] "Sign In" button is disabled until both fields are non-empty
- [ ] On successful API response (200), redirect to `/dashboard`
- [ ] On 401 response, show inline error "Invalid email or password"
- [ ] After 3 consecutive 401 responses, show "Account locked" message
- [ ] Component has unit tests ≥ 80% coverage
```

---

## Summary Checklist at End

After all personas, produce a **master checklist** in this format for quick reference:

```markdown
## Master TODO Checklist

### Frontend Engineer
- [ ] TODO-FE-001 · Implement Login Screen (3SP, Sprint 1)
- [ ] TODO-FE-002 · Build Dashboard layout (5SP, Sprint 1)
...

### Backend Engineer
- [ ] TODO-BE-001 · Auth API endpoints (3SP, Sprint 1)
...

### Data Engineer
- [ ] TODO-DE-001 · Design database schema (5SP, Sprint 1)
...

### Data Analyst
- [ ] TODO-DA-001 · Define KPI metrics (2SP, Sprint 2)
...

### SRE / Cloud Engineer
- [ ] TODO-SRE-001 · Provision Azure resource group + vNet (3SP, Sprint 1)
...
```

---

## Also Generate: GitHub Issues Export

Append a section `## GitHub Issues Export` with each TODO formatted as a GitHub-pasteable markdown block:

```markdown
**Title**: TODO-FE-001 · Implement Login Screen
**Labels**: frontend, auth, sprint-1
**Milestone**: Sprint 1
**Assignee**: @frontend-engineer
**Body**:
[Description + Acceptance Criteria from above]
```

---

Save as `output/07-persona-todos-<project-name>.md`.

After saving, confirm: "Persona TODOs generated. Summary: Frontend (X tasks), Backend (X), Data Eng (X), Data Analyst (X), SRE/Cloud (X). Pipeline complete! 🎉"
