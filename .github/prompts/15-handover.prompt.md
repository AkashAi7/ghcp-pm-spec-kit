---
mode: agent
description: "/handover — Generate a project handover document for team transitions, end-of-phase, or project closure."
---

# Project Handover Document Generator

## Trigger
This prompt runs when the user types `/handover`, `/handoff`, `/closure`, or asks to "document a handover" or "close the project".

## Instructions

1. Read all available artefacts from `output/`:
   - BRD summary, FSD, TDD, WBS, PM Plan, Sprint Plan, Risk Register, Status Reports
   Use whichever files exist and note any gaps.

2. Generate a comprehensive handover document:

---

## Project Handover Document — <Project Name>

**Handover Type:** Phase Completion / Team Transition / Project Closure
**Handover Date:** <date>
**Handing Over:** <old team/owner>
**Receiving:** <new team/owner>

---

### Section 1 — Project Overview
- Project name, objective, original BRD reference
- What was delivered vs. what was in scope
- Final status (Completed / Partially Delivered / Cancelled)

### Section 2 — Artefacts Inventory
| Artefact | File | Status | Location |
|----------|------|--------|---------|
| BRD Summary | | Complete | output/ |
| FSD | | Complete | output/ |
| TDD | | Complete | output/ |
| WBS | | Complete | output/ |
| PM Plan | | Complete | output/ |
| Source Code | | | repo link |
| Infrastructure Config | | | repo/infra |
| Test Reports | | | |

### Section 3 — System Access & Credentials
> ⚠️ Do NOT paste credentials here. List where they are stored.

| System | Access Method | Where Credentials Live | Contact |
|--------|-------------|----------------------|---------|

### Section 4 — Environments
| Environment | URL / Connection | Status | Notes |
|-------------|----------------|--------|-------|
| Development | | | |
| Staging | | | |
| Production | | | |

### Section 5 — Outstanding Items
| Item | Priority | Recommended Owner | Notes |
|------|---------|-----------------|-------|
| (from open WBS tasks) | | | |

### Section 6 — Known Issues & Tech Debt
| Issue | Severity | Recommended Fix | Effort Est. |
|-------|---------|----------------|------------|

### Section 7 — Open Risks
(From risk register — open/amber/red risks only)

### Section 8 — Team Knowledge Transfer Notes
For each persona:
- **Frontend Engineer:** Key files, patterns, gotchas
- **Backend Engineer:** API design decisions, DB gotchas
- **Data Engineer:** Pipeline schedules, data sources, quirks
- **Data Analyst:** Report refresh schedules, data definitions
- **SRE / Cloud Engineer:** Infra runbook, monitoring alerts, cost controls

### Section 9 — Support & Operations
- How to raise incidents
- On-call rotation
- SLA commitments
- Runbook location

### Section 10 — Lessons Learned
| Lesson | Category | Recommendation for Next Project |
|--------|---------|-------------------------------|

### Section 11 — Sign-Off
| Role | Name | Signature | Date |
|------|------|----------|------|
| Project Sponsor | | | |
| Delivery Manager | | | |
| Receiving Owner | | | |

---

3. Save to `output/15-handover-<project-name>.md`.

Print: `✅ Handover document saved to output/15-handover-<project-name>.md`
