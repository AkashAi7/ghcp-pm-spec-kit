---
mode: agent
description: "/sprint — Generate a detailed sprint plan from the WBS. Breaks WBS tasks into 2-week sprints with capacity, velocity, and definition of done."
---

# Sprint Plan Generator

## Trigger
This prompt runs when the user types `/sprint`, `/sprint-plan`, or asks to "plan sprints".

## Instructions

1. Read the latest WBS from `output/` — find the file matching `04-wbs-*.md`.
   If not found, read `templates/wbs_template.md` and ask the user to confirm or paste WBS content.

2. Extract all WBS tasks and their story points.

3. Build a sprint plan with the following structure:

### Sprint Configuration
- Sprint length: **2 weeks**
- Team velocity: **40 story points per sprint** (adjust if WBS provides team size)
- Include a **10% buffer** per sprint for bugs / unplanned work

### For Each Sprint, produce:
| Field | Detail |
|-------|--------|
| Sprint Name | Sprint 1, Sprint 2, … |
| Sprint Goal | One-sentence goal |
| Start / End Dates | Calculated from project start |
| Committed Stories | WBS task IDs + names + SP |
| Total SP | Sum for the sprint |
| Persona Assignments | Which persona owns which task |
| Definition of Done | 3-5 bullet criteria |
| Dependencies | Any tasks blocked by prior sprint |
| Risks | Sprint-level risks |

4. Produce a **Mermaid Gantt chart** spanning all sprints.

5. Add a **Sprint Velocity Table** showing planned vs. actual (actual left blank for live use).

6. Add a **Backlog Refinement section**: list any WBS tasks not yet assigned to a sprint (backlog items).

7. Save the output to `output/08-sprint-plan-<project-name>.md`.

## Output Template

Use `templates/sprint_plan_template.md` if it exists, otherwise follow the structure above.

Print: `✅ Sprint plan saved to output/08-sprint-plan-<project-name>.md`
