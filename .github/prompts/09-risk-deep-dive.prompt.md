---
mode: agent
description: "/risks — Deep risk analysis with mitigation strategies, probability/impact matrix, and risk heat map."
---

# Risk Deep Dive

## Trigger
This prompt runs when the user types `/risks`, `/risk-register`, or asks to "analyse risks" or "list risks".

## Instructions

1. Read the BRD from `intake/`, the FSD from `output/02-fsd-*.md`, and the PM Plan risk section from `output/05-pm-plan-*.md` (if available).

2. Identify risks across these categories:
   - **Technical Risks** — integrations, tech debt, unknown APIs, third-party dependencies
   - **Schedule Risks** — tight milestones, dependencies, resource availability
   - **Resource Risks** — key-person dependency, skill gaps, bandwidth
   - **Business Risks** — stakeholder alignment, budget, scope creep
   - **Security & Compliance Risks** — data privacy, access control, audit requirements
   - **External Risks** — vendor reliability, regulatory changes, market shifts

3. For each risk, capture:

| Field | Description |
|-------|-------------|
| Risk ID | RISK-01, RISK-02, … |
| Category | Technical / Schedule / Resource / Business / Security / External |
| Description | Clear one-line description |
| Probability | Low / Medium / High |
| Impact | Low / Medium / High |
| Risk Score | P × I (1-9 scale) |
| Owner | Which persona owns mitigation |
| Mitigation Strategy | What will be done to reduce probability |
| Contingency Plan | What to do if the risk materialises |
| Status | Open / Mitigated / Accepted / Closed |

4. Produce a **Mermaid quadrant chart** (probability vs. impact) showing risk distribution.

5. Add a **Risk Heat Map table** (3×3 grid: Low/Medium/High probability vs. Low/Medium/High impact).

6. Add a **Top 5 Critical Risks** summary at the top.

7. Add a **Risk Review Schedule** — recommend review cadence (weekly for Critical, bi-weekly for High).

8. Save to `output/09-risk-register-<project-name>.md`.

Print: `✅ Risk register saved to output/09-risk-register-<project-name>.md`
