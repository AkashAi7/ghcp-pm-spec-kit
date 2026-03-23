# Lab 5 — Generate the Project Management Plan

**Time:** ~8 minutes  
**Prerequisites:** Lab 4 complete — `output/04-wbs-*.md` exists  
**Goal:** Produce a Gantt chart, risk register, and communication plan.

---

## What is in a PM Plan?

The PM Plan ties the WBS into a **deliverable schedule** and anticipates what could go wrong.

| Component | Purpose |
|-----------|---------|
| **Gantt Chart** | Visual timeline showing when each task starts/ends |
| **Risk Register** | Known risks, their likelihood, impact, and mitigation plans |
| **Communication Plan** | Who gets what information, how often, in what format |

---

## Step 1: Generate the PM Plan

```
@workspace Follow the instructions in .github/prompts/05-generate-pm-plan.prompt.md
Read output/04-wbs-*.md as the source.
Use templates/pm_plan_template.md for structure.
Generate the PM Plan and save it as output/05-pm-plan-<project-name>.md
```

---

## Step 2: View the Gantt Chart

1. Open `output/05-pm-plan-<project-name>.md`
2. Click **Preview** (`Ctrl+Shift+V`)
3. The Gantt chart should render as a timeline

If the bars appear but have wrong dates:
```
Update the Gantt chart start date to today's date and adjust all durations so 
the project runs exactly 18 weeks total.
```

---

## Step 3: Customise the Risk Register

The generated risks are generic. Tailor them to your specific project:

```
Add 3 more risks specific to this project's context:
1. A risk related to the OCR integration accuracy
2. A risk about GDPR compliance for the data we're storing
3. A risk about user adoption by the finance team
```

---

## Step 4: Identify the Critical Path

```
Looking at the WBS and Gantt chart, what is the critical path for this project?
List the tasks that, if delayed, would push back the go-live date.
Add a Critical Path section to the PM Plan.
```

---

## Step 5: Generate the RACI Matrix

If the RACI Matrix needs expanding:
```
Generate a detailed RACI matrix for this project covering:
Requirements sign-off, Architecture decisions, Each development sprint,
Test sign-off, UAT coordination, Go-Live decision, and Budget management.
Use the five engineering personas plus PM and Stakeholders.
```

---

## What You Should Have

After this lab:
- [ ] `output/05-pm-plan-<project-name>.md` saved
- [ ] Gantt chart renders in Preview with phases and milestones
- [ ] Risk register with ≥ 10 risks, scores, and mitigations
- [ ] Risk matrix (probability × impact)
- [ ] Communication plan with meeting cadence
- [ ] RACI matrix
- [ ] Critical path identified

---

**← Previous:** [Lab 4](04-generate-wbs.md)  
**Next:** [Lab 6 — Generate UI Prototype →](06-generate-ui-prototype.md)
