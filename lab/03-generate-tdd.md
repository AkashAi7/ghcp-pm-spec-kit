# Lab 3 — Generate the Technical Design Document (TDD)

**Time:** ~10 minutes  
**Prerequisites:** Lab 2 complete — `output/02-fsd-*.md` exists  
**Goal:** Produce the system architecture, database schema, API catalogue, and Azure resource map.

---

## What is a TDD?

The TDD answers **"How will we build it?"** — it's the blueprint for the engineering team.

It includes:
- System architecture diagram (how components connect)
- Tech stack decisions (why React, why .NET, why Azure SQL)
- Database entity-relationship diagram
- API endpoint catalogue (every HTTP endpoint)
- Authentication and authorisation design
- Azure resource map (which services, which SKUs)
- Security design (OWASP mitigations)
- CI/CD pipeline design

---

## Step 1: Run the TDD Prompt

```
@workspace Follow the instructions in .github/prompts/03-generate-tdd.prompt.md
Read output/02-fsd-*.md as the source.
Use templates/tdd_template.md for structure.
Generate a complete TDD and save it as output/03-tdd-<project-name>.md
```

---

## Step 2: Architecture Diagram

The TDD should include a Mermaid architecture diagram. Verify it renders in VS Code:

1. Open `output/03-tdd-<project-name>.md`
2. Click the **Preview** button (top-right, or `Ctrl+Shift+V`)
3. Scroll to the architecture diagram — it should render as a visual graph

If the diagram doesn't render:
- Ensure the VS Code **Markdown Preview Mermaid Support** extension is installed
  → Install: Extensions → search "Markdown Preview Mermaid Support"

---

## Step 3: Customise the Tech Stack

If the inferred tech stack doesn't match your project, tell Copilot:

```
Update the TDD tech stack: use Python FastAPI for the backend instead of .NET,
PostgreSQL instead of Azure SQL, and Vue.js for the frontend.
Regenerate the API catalogue and Database sections accordingly.
```

---

## Step 4: Generate the ER Diagram

If the entity-relationship diagram is missing or incomplete:

```
Based on the data dictionary in the FSD, generate a complete Mermaid erDiagram
showing all entities, their key fields, and relationships.
Add it to the Database Design section of the TDD.
```

---

## Step 5: Security Checklist

Ask Copilot to verify the security design:

```
Review the TDD and check it addresses OWASP Top 10 items.
For each item, describe the specific mitigation being used in this architecture.
Add a Security Design section if one doesn't exist.
```

---

## What You Should Have

After this lab:
- [ ] `output/03-tdd-<project-name>.md` saved
- [ ] Architecture diagram renders in Markdown Preview
- [ ] Database ER diagram included
- [ ] API catalogue with at least one endpoint per FSD module
- [ ] Azure resource map with service names and SKUs
- [ ] Security design section referencing OWASP Top 10

---

**← Previous:** [Lab 2](02-generate-fsd.md)  
**Next:** [Lab 4 — Generate the WBS →](04-generate-wbs.md)
