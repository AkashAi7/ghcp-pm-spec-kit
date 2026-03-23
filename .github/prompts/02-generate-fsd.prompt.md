---
mode: agent
description: "STEP 2 — Generate a Functional Specification Document (FSD / SRS) from the parsed BRD summary."
---

# Step 2 — Generate Functional Specification Document (FSD)

## Prerequisites
- Step 1 (Parse BRD) must be complete. The file `output/01-brd-summary-<project-name>.md` must exist.
- Template: `templates/fsd_template.md`

## Instructions

1. Read `output/01-brd-summary-<project-name>.md` (find the correct file in `output/`).
2. Read `templates/fsd_template.md` to understand the required structure.
3. Generate a complete FSD by expanding each `BRD-FR-xx` requirement into:
   - **Detailed functional description** (screen-level behaviour, field validations, error states)
   - **User stories** (`As a <persona>, I want to <action> so that <benefit>`)
   - **Acceptance criteria** (Given/When/Then format)
   - **UI hints** (what the screen/component looks like — described in text)
   - **Business rules** (e.g., "Lock account after 3 failed attempts")
4. Group requirements by **module or feature area**.
5. Each FSD requirement ID format: `FSD-FR-01` with a back-reference to `BRD-FR-xx`.
6. Include a **Data Dictionary** section (key entities and their fields).
7. Include an **Integration Points** section (external systems, APIs, third-party services).
8. Save as `output/02-fsd-<project-name>.md`.

## Depth Expectations

| Good FSD Entry | Too Shallow |
|----------------|-------------|
| "The login screen shows email + password fields. Email validates RFC 5322 format on blur. After 3 failed attempts, account locks for 15 minutes and shows error `ERR-LOGIN-003`." | "Users can log in." |

## Output Format

Follow `templates/fsd_template.md` exactly. Key sections:
- Document Header (project, version, date, author)
- Table of Contents
- System Overview
- User Roles & Permissions
- Feature Modules (one H2 per module)
  - Functional Requirements with FSD-FR-xx IDs
  - User Stories
  - Acceptance Criteria
  - UI Description
  - Business Rules
- Data Dictionary
- Integration Points
- Glossary

After saving, confirm: "FSD generated. X feature modules, Y requirements. Proceed to Step 3 (TDD)."
