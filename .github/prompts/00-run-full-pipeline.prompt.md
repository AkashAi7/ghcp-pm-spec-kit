---
mode: agent
description: "FULL PIPELINE — Automatically runs all 7 steps from BRD intake to persona TODOs. Drop your BRD in intake/ and run this prompt. Zero manual prompting required."
---

# Full PM Artefact Pipeline — Auto Run

You are an expert Project Management AI. Execute the following 7 steps **in sequence**.
Complete each step fully (including saving the output file) before starting the next.
**Do NOT ask for confirmation between steps** — run the full pipeline autonomously.

## Before Starting

1. Scan the `intake/` folder and identify the BRD file (`.md` or `.txt`).
2. Extract the project name from the BRD — use it as `<project-name>` in all filenames (lowercase, hyphens for spaces).
3. If no BRD file is found in `intake/`, stop and tell the user to drop one there first.

---

## Step 1 — Parse BRD

Follow all instructions in `.github/prompts/01-parse-brd.prompt.md`.
Save output to `output/01-brd-summary-<project-name>.md`.
Print: `✅ Step 1 done — BRD parsed.`

## Step 2 — Functional Specification Document

Follow all instructions in `.github/prompts/02-generate-fsd.prompt.md`.
Read `output/01-brd-summary-<project-name>.md` as source.
Use `templates/fsd_template.md` for structure.
Save output to `output/02-fsd-<project-name>.md`.
Print: `✅ Step 2 done — FSD saved.`

## Step 3 — Technical Design Document

Follow all instructions in `.github/prompts/03-generate-tdd.prompt.md`.
Read `output/02-fsd-<project-name>.md` as source.
Use `templates/tdd_template.md` for structure.
Save output to `output/03-tdd-<project-name>.md`.
Print: `✅ Step 3 done — TDD saved.`

## Step 4 — Work Breakdown Structure

Follow all instructions in `.github/prompts/04-generate-wbs.prompt.md`.
Read `output/02-fsd-<project-name>.md` and `output/03-tdd-<project-name>.md` as sources.
Use `templates/wbs_template.md` for structure.
Save output to `output/04-wbs-<project-name>.md`.
Print: `✅ Step 4 done — WBS saved.`

## Step 5 — Project Management Plan

Follow all instructions in `.github/prompts/05-generate-pm-plan.prompt.md`.
Read `output/04-wbs-<project-name>.md` as source.
Use `templates/pm_plan_template.md` for structure.
Save output to `output/05-pm-plan-<project-name>.md`.
Print: `✅ Step 5 done — PM Plan saved.`

## Step 6 — UI Prototype

Follow all instructions in `.github/prompts/06-generate-ui-prototype.prompt.md`.
Read `output/02-fsd-<project-name>.md` as source.
Use `templates/ui_prototype_template.md` for structure.
Save Mermaid wireframes to `output/06-ui-wireframes-<project-name>.md`.
Save HTML prototype to `output/06-ui-prototype-<project-name>.html`.
Print: `✅ Step 6 done — UI prototype saved.`

## Step 7 — Persona TODOs

Follow all instructions in `.github/prompts/07-generate-persona-todos.prompt.md`.
Read `output/04-wbs-<project-name>.md` and `output/03-tdd-<project-name>.md` as sources.
Use `templates/persona_todos_template.md` for structure.
Save output to `output/07-persona-todos-<project-name>.md`.
Print: `✅ Step 7 done — Persona TODOs saved.`

---

## Final Summary

After all 7 steps complete, print:

```
🎉 Pipeline complete for: <project-name>

Files created in output/:
  01-brd-summary-<project-name>.md
  02-fsd-<project-name>.md
  03-tdd-<project-name>.md
  04-wbs-<project-name>.md
  05-pm-plan-<project-name>.md
  06-ui-wireframes-<project-name>.md
  06-ui-prototype-<project-name>.html
  07-persona-todos-<project-name>.md

Next steps — pick your role and start building:
  → /dev frontend      — scaffold components, routes, and tests (Frontend Engineer)
  → /dev backend       — scaffold APIs, services, and repositories (Backend Engineer)
  → /dev data-engineer — scaffold pipelines, schemas, and notebooks (Data Engineer)
  → /dev data-analyst  — scaffold DAX measures, report pages, KPIs (Data Analyst)
  → /dev sre           — scaffold Bicep, GitHub Actions, and alerts (SRE / Cloud Engineer)

  → Run /sprint to generate sprint plans from the WBS
  → Run /status to create a project status report
  → Run /risks for a deep risk analysis
```
