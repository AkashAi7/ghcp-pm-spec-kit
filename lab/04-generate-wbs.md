# Lab 4 — Generate the Work Breakdown Structure (WBS)

**Time:** ~10 minutes  
**Prerequisites:** Labs 2 and 3 complete  
**Goal:** Break the full scope into granular tasks with persona assignments and effort estimates.

---

## What is a WBS?

The WBS takes the entire project scope (from FSD + TDD) and fragments it into
bite-sized work packages — each assigned to a persona with an effort estimate.

A good WBS answers:
- **What** exactly needs to be built (task level)
- **Who** builds it (persona)
- **How much effort** it requires (story points)
- **What depends on what** (dependencies)

---

## Step 1: Run the WBS Prompt

```
@workspace Follow the instructions in .github/prompts/04-generate-wbs.prompt.md
Read output/02-fsd-*.md and output/03-tdd-*.md as sources.
Use templates/wbs_template.md for structure.
Generate a WBS and save it as output/04-wbs-<project-name>.md
```

---

## Step 2: Review the WBS Tree

Open the generated WBS and verify the Mermaid WBS tree renders:

1. Open `output/04-wbs-<project-name>.md`
2. Click **Preview** (`Ctrl+Shift+V`)
3. The tree diagram should show Project → Phases → Work Packages

---

## Step 3: Review Completeness

Check every FSD-FR-xx has at least one corresponding WBS task:

```
Compare the WBS tasks to the FSD requirements. Are there any FSD-FR-xx 
requirements that don't have a corresponding WBS task? List any gaps.
```

---

## Step 4: Adjust Effort Estimates

The default estimates are ballpark figures. You can refine them:

```
The backend team is senior engineers — reduce backend story point estimates by 20%.
Also, the data engineering work is more complex because SAP integration is not REST-based.
Increase the SAP pipeline tasks to 13 SP each.
Update the WBS effort summary table accordingly.
```

---

## Step 5: Sprint Allocation

Ask Copilot to assign tasks to sprints:

```
Based on the WBS tasks and effort estimates, allocate each task to a 2-week sprint.
Assume a team velocity of 30 story points per sprint.
Add a Sprint column to each WBS table and update the summary.
```

---

## What You Should Have

After this lab:
- [ ] `output/04-wbs-<project-name>.md` saved
- [ ] WBS tree diagram renders in Preview
- [ ] 3-level hierarchy: Phase → Work Package → Tasks
- [ ] Every task has: Task ID, Description, Persona, SP, FSD/TDD Ref, Dependencies
- [ ] Effort summary table per persona and phase
- [ ] Sprint assignments added

---

**← Previous:** [Lab 3](03-generate-tdd.md)  
**Next:** [Lab 5 — Generate the PM Plan →](05-generate-pm-plan.md)
