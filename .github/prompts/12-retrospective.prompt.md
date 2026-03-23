---
mode: agent
description: "/retro — Generate a sprint retrospective document with What Went Well, What Didn't, Action Items, and team health score."
---

# Sprint Retrospective Generator

## Trigger
This prompt runs when the user types `/retro`, `/retrospective`, or asks to "run a retro" or "retrospective".

## Instructions

1. Read the current sprint details from `output/08-sprint-plan-*.md`.
   Read open risks from `output/09-risk-register-*.md` if available.
   Read the last status report from `output/10-status-report-*.md` if available.

2. Ask the user which sprint number this retro is for (or infer from the latest sprint plan).

3. Generate the retrospective document:

---

### Section 1 — Sprint Summary
- Sprint number, dates, goal
- Planned SP vs. Completed SP (leave blanks the user fills in)
- Sprint outcome: ✅ Goal Met / ⚠️ Partial / ❌ Not Met

### Section 2 — What Went Well (Keep Doing)
Generate 5-7 prompts/starters for the team to fill in, based on the sprint tasks.
Format as a table with columns: Feedback | Category | Vote Count (for dot voting)

Categories: Process | Technical | Collaboration | Delivery | Quality

### Section 3 — What Didn't Go Well (Stop / Improve)
Generate 5-7 prompts/starters for areas likely to have friction based on risks and blockers.
Format as: Issue | Root Cause (5-Why) | Impact | Priority

### Section 4 — Action Items
| # | Action | Owner | Due Date | Success Criteria |
|---|--------|-------|---------|-----------------|
| A-01 | | | | |

(Pre-fill 3 action items based on top risks or common retrospective insights)

### Section 5 — Team Health Check
Rate each dimension 1-5 (5 = excellent). Leave blanks for team to fill:
- Delivering Value: ___/5
- Fun & Motivation: ___/5
- Speed: ___/5
- Quality: ___/5
- Learning: ___/5
- Support: ___/5

### Section 6 — Carry-Over Items
- List any sprint tasks not completed (from sprint plan) with reason.

### Section 7 — Next Sprint Preview
- Sprint N+1 goal (draft based on WBS)
- Items already committed

4. Use Mermaid for a simple **burndown chart template** (shows ideal line; team fills actuals).

5. Save to `output/12-retro-<project-name>-sprint-<N>.md`.

Print: `✅ Retrospective template saved to output/12-retro-<project-name>-sprint-<N>.md`
