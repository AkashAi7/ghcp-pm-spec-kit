# Lab 8 — From User Stories to Code: Persona-Wise Development

**Time:** ~20–30 minutes  
**Prerequisites:** Lab 7 complete (Persona TODOs generated)  
**Goal:** Take the generated TODO items and use GitHub Copilot to implement actual code, feature by feature, persona by persona.

---

## The Journey: BRD → User Story → Working Code

```
BRD Requirement
    ↓
FSD User Story  (Lab 2)
    ↓
WBS Task        (Lab 4)
    ↓
Persona TODO    (Lab 7)
    ↓
Code + Tests    (This Lab — Lab 8)
```

Each TODO item generated in Lab 7 maps directly to a user story in the FSD.
In this lab, you pick your persona, open your TODO list, and use Copilot to
implement each item — with the right tech stack, conventions, and tests for your role.

---

## Step 1 — Pick Your Persona

Each team member works as ONE persona. Choose yours:

| Persona | You build... | Instruction file |
|---------|-------------|-----------------|
| Frontend Engineer | UI screens, components, routing | `persona-instructions/frontend-engineer.instructions.md` |
| Backend Engineer | APIs, services, auth, jobs | `persona-instructions/backend-engineer.instructions.md` |
| Data Engineer | Pipelines, schemas, ETL, Fabric | `persona-instructions/data-engineer.instructions.md` |
| Data Analyst | Power BI reports, DAX, KPIs | `persona-instructions/data-analyst.instructions.md` |
| SRE / Cloud Engineer | Azure infra, CI/CD, monitoring | `persona-instructions/sre-cloud-engineer.instructions.md` |

---

## Step 2 — Load Your Persona Instruction File

Open the instruction file for your persona from the `persona-instructions/` folder.

This file tells Copilot:
- Your tech stack and conventions
- How to break down a TODO into implementation steps
- Code style and testing requirements for your role

> **How to activate it in Copilot Chat:**  
> The `.instructions.md` files in `persona-instructions/` are auto-loaded by VS Code  
> when Copilot sees related files. You can also reference one explicitly:  
> Type `#file:persona-instructions/frontend-engineer.instructions.md` in chat before your request.

---

## Step 3 — Open Your TODO List

Open `output/07-persona-todos-<your-project>.md` and find your persona's section.

Example (Frontend Engineer section):
```
## Frontend Engineer

- [ ] FE-001: Build Login screen with email/password form (FSD-FR-01)
- [ ] FE-002: Build Dashboard layout with navigation sidebar (FSD-FR-05)
- [ ] FE-003: Implement patient search component with debounced input (FSD-FR-08)
- [ ] FE-004: Build appointment booking form with date picker (FSD-FR-12)
```

Pick ONE task to start with. Always start with the first unchecked item.

---

## Step 4 — Implement a Task with Copilot

For each TODO item, use this prompt pattern in Copilot Chat:

```
#file:persona-instructions/<your-persona>.instructions.md

I am working on: [paste the TODO item]
User story reference: [paste the FSD user story — e.g. FSD-FR-01]

Please:
1. Scaffold the code for this task
2. Follow the conventions in my persona instructions
3. Include unit tests
4. Show me what files to create or modify
```

**Example for a Frontend Engineer:**
```
#file:persona-instructions/frontend-engineer.instructions.md

I am working on: FE-001 — Build Login screen with email/password form (FSD-FR-01)
User story: As a patient, I want to log in with my email and password so I can access my portal.

Please:
1. Scaffold the Login component in React
2. Follow the conventions in my persona instructions
3. Include a unit test with React Testing Library
4. Show me what files to create or modify
```

---

## Step 5 — Review, Refine, and Check Off

After Copilot generates the code:

1. **Read it** — does it match the user story intent?
2. **Ask for changes** — "Make the form accessible (WCAG 2.1 AA)" or "Add loading state"
3. **Ask for the test** — if not included, type: "Add a unit test for the happy path and one error case"
4. **Mark it done** — update your TODO list: change `- [ ]` to `- [x]`

---

## Step 6 — Move to the Next Task

Repeat Steps 3–5 for each remaining TODO item in your persona's section.

### Sequencing tip

Work in this order within your TODO list:
1. **Foundation tasks first** — auth, layout, schema setup, infra scaffold
2. **Feature tasks** — screens, endpoints, pipelines, dashboards
3. **Integration tasks** — wiring features together, E2E tests
4. **Polish tasks** — error handling, accessibility, monitoring

---

## Persona-Wise Development Cheat Sheet

### Frontend Engineer
```
Build the [ComponentName] component.
- It should [describe behaviour from user story]
- Use React functional components + TypeScript
- Style with [Tailwind / CSS Modules / your stack]
- Add a unit test with React Testing Library
- Reference: [FSD-FR-xx]
```

### Backend Engineer
```
Create the [endpoint/service] for [feature].
- Method: [GET/POST/PUT/DELETE] /api/[path]
- Input: [describe request body/params]
- Business rule: [describe logic from FSD]
- Return: [describe response shape]
- Add a unit test with 1 happy path + 1 error case
- Reference: [FSD-FR-xx]
```

### Data Engineer
```
Create the [pipeline/schema/table] for [feature].
- Source: [describe the data source]
- Transformation: [describe what needs to happen]
- Destination: [describe target table/store]
- Include idempotency and error handling
- Reference: [FSD-FR-xx / TDD-DB-xx]
```

### Data Analyst
```
Create the [report/measure/dashboard] for [feature].
- Metric: [describe what to measure]
- Grain: [daily / weekly / per-user etc]
- Filter/slicers: [what the user can filter by]
- Reference: [FSD-FR-xx]
```

### SRE / Cloud Engineer
```
Create the Bicep/YAML for [resource/workflow].
- Resource: [Azure resource type]
- SKU/tier: [dev = Basic, prod = Standard etc]
- Dependencies: [what it connects to]
- Include outputs for downstream resources
- Reference: [TDD-INFRA-xx]
```

---

## Traceability Check

After completing all tasks for your persona, verify coverage:

```
#file:output/02-fsd-<project>.md
#file:output/07-persona-todos-<project>.md

For each FSD user story relevant to my persona (Frontend Engineer),
confirm it has a corresponding checked-off TODO item.
List any FSD requirements with no matching implementation task.
```

This closes the loop: **BRD requirement → FSD user story → TODO → implemented code**.
