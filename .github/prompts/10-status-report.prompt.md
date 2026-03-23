---
mode: agent
description: "/status — Generate a weekly project status report (RAG status, milestones, blockers, next week plan)."
---

# Project Status Report Generator

## Trigger
This prompt runs when the user types `/status`, `/status-report`, or asks for a "project update" or "weekly report".

## Instructions

1. Read available artefacts from `output/`:
   - Sprint plan: `08-sprint-plan-*.md` (for current sprint context)
   - WBS: `04-wbs-*.md` (for milestone tracking)
   - Risk register: `09-risk-register-*.md` or `05-pm-plan-*.md` (for open risks)

2. Ask the user (or infer if context is available):
   - Current date / reporting week
   - Overall RAG status: 🟢 Green / 🟡 Amber / 🔴 Red
   - Any blockers or issues to highlight

3. Generate the status report with these sections:

### Section 1 — Executive Summary
- Project name, reporting period, prepared by
- Overall RAG status with one-line justification
- Key highlight of the week (1-2 sentences)

### Section 2 — Milestone Tracker
| Milestone | Planned Date | Status | Notes |
|-----------|-------------|--------|-------|
| (from WBS) | | 🟢 On Track / 🟡 At Risk / 🔴 Delayed | |

### Section 3 — This Week Accomplishments
- Bullet list of completed tasks (from current sprint)

### Section 4 — Next Week Plan
- Bullet list of planned tasks (from next sprint)

### Section 5 — Blockers & Escalations
| Blocker | Impact | Owner | Resolution Plan | Target Date |
|---------|--------|-------|----------------|-------------|

### Section 6 — Risk Snapshot
- Top 3 open risks with current status (from risk register)

### Section 7 — Budget / Resource Utilisation (optional)
- Story points planned vs. completed this sprint
- Team capacity notes

### Section 8 — Decisions Required
- Any decisions needed from stakeholders this week

4. Use RAG emoji indicators: 🟢 Green, 🟡 Amber, 🔴 Red throughout.

5. Save to `output/10-status-report-<project-name>-week-<NN>.md` (NN = week number or date).

Print: `✅ Status report saved.`
