---
mode: agent
description: "/change — Raise a formal Change Request (CR) document with impact analysis on scope, schedule, cost, and quality."
---

# Change Request Generator

## Trigger
This prompt runs when the user types `/change`, `/cr`, `/change-request`, or describes a "scope change" or "new requirement".

## Instructions

1. Ask the user to describe the change in plain language, OR accept a description already provided in the chat.

2. Read the BRD from `intake/`, FSD from `output/02-fsd-*.md`, and WBS from `output/04-wbs-*.md` to understand the current baseline.

3. Generate a formal Change Request document:

---

### CR Header
- **CR ID:** CR-<NNN> (auto-increment from last CR in output/ folder)
- **Date Raised:** Today's date
- **Priority:** Critical / High / Medium / Low
- **Type:** New Feature / Enhancement / Bug Fix / Removal / Regulatory / Configuration

### Section 1 — Change Description
- **Summary** (1 paragraph, plain language)
- **Detailed Description** (what exactly changes, with before/after comparison)
- **Business Justification** (why is this change needed?)
- **Requested By** (role, not name)

### Section 2 — Affected Areas (tick all that apply)
Check each area and describe impact:
- [ ] Requirements (BRD-FR-xx affected)
- [ ] FSD Sections (which FSD modules change)
- [ ] TDD / Architecture (new components, APIs, DB changes)
- [ ] UI / UX (new screens, flows)
- [ ] Infrastructure (new Azure resources, cost impact)
- [ ] Security (new auth flows, data classification)
- [ ] Testing (new test cases required)

### Section 3 — Impact Analysis

| Dimension | Current Baseline | New Baseline | Delta |
|-----------|-----------------|-------------|-------|
| Scope | | | +/- features |
| Timeline | | | +/- days |
| Effort | | | +/- story points |
| Cost (estimated) | | | +/- $ |
| Quality Risk | Low | | |

### Section 4 — Options Analysis
Present 3 options:
1. **Accept as-is** — full change implemented
2. **Partial accept** — implement core of change, defer rest
3. **Reject** — reasons for rejection

### Section 5 — Recommendation
State the recommended option with rationale.

### Section 6 — Approval Workflow
| Approver Role | Decision | Date | Notes |
|--------------|---------|------|-------|
| Product Owner | ⬜ Pending | | |
| Technical Lead | ⬜ Pending | | |
| Project Sponsor | ⬜ Pending | | |

### Section 7 — Implementation Plan (if approved)
- New WBS tasks required
- Sprint impact
- Updated milestones

4. Save to `output/13-change-request-<CR-ID>-<project-name>.md`.

Print: `✅ Change request CR-<NNN> saved.`
