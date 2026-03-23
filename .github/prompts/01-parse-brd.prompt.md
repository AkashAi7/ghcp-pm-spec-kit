---
mode: agent
description: "STEP 1 — Parse and validate a BRD file from the intake/ folder. Produces a structured BRD summary saved to output/."
---

# Step 1 — Parse BRD

## What This Does
Reads the BRD file from `intake/` (`.md`, `.txt`, or pasted content) and produces a
clean, structured BRD summary that all subsequent steps will reference.

## Instructions

1. Scan the `intake/` folder and identify the BRD file. If multiple files exist, list them and ask which to use.
2. Read the full contents of the BRD file.
3. Extract and structure the following sections (infer/derive if not explicitly present):
   - **Project Name**
   - **Problem Statement**
   - **Business Objectives** (bullet list)
   - **Stakeholders & Personas** (identify roles mentioned)
   - **Functional Requirements** — number each as `BRD-FR-01`, `BRD-FR-02`, etc.
   - **Non-Functional Requirements** — number each as `BRD-NFR-01`, etc.
   - **Constraints & Assumptions**
   - **Success Metrics / Acceptance Criteria**
   - **Out of Scope items** (if mentioned)
4. Highlight any **gaps or ambiguities** you find — list them as `GAP-01`, `GAP-02`, etc.
5. Save the structured output as `output/01-brd-summary-<project-name>.md`.

## Output Format

Use the following structure exactly:

```markdown
# BRD Summary — <Project Name>
**Generated:** <date>
**Source File:** <intake filename>

## Project Overview
...

## Business Objectives
- ...

## Stakeholders
| Persona | Role | Interest |
|---------|------|----------|

## Functional Requirements
| ID | Requirement | Priority |
|----|-------------|----------|
| BRD-FR-01 | ... | High |

## Non-Functional Requirements
| ID | Category | Requirement |
|----|----------|-------------|
| BRD-NFR-01 | Performance | ... |

## Constraints & Assumptions
- ...

## Success Metrics
- ...

## Identified Gaps
| ID | Gap Description | Suggested Clarification |
|----|-----------------|------------------------|
| GAP-01 | ... | ... |
```

After saving, confirm: "BRD parsed. X functional requirements, Y NFRs, Z gaps identified. Proceed to Step 2 (FSD generation)."
