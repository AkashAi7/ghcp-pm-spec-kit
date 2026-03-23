---
mode: agent
description: "/standup — Generate a today's standup note template pre-filled from the sprint plan. Ready to paste into Teams / Slack."
---

# Daily Standup Notes Generator

## Trigger
This prompt runs when the user types `/standup`, `/daily`, or asks for "today's standup".

## Instructions

1. Read the current sprint from `output/08-sprint-plan-*.md` — find tasks assigned to today's date range.
   If sprint plan not available, read `output/04-wbs-*.md` for in-progress tasks.

2. Generate standup notes for ALL 5 personas:
   - Frontend Engineer
   - Backend Engineer
   - Data Engineer
   - Data Analyst
   - SRE / Cloud Engineer

3. For each persona, produce the standard 3-question format:

```
### <Persona Name>
**Yesterday:** <tasks likely completed based on sprint backlog — infer from context>
**Today:** <next tasks in sprint for this persona>
**Blockers:** None / <list any dependencies or risks from risk register>
```

4. Add a **Team-Level Summary** at the top:
```
## Standup — <Date>
Sprint: Sprint X (Day Y/10)
Sprint Goal: <from sprint plan>
Sprint Health: 🟢 / 🟡 / 🔴
```

5. Add a **Quick Wins** section — highlight anything that can be completed today.

6. Add a **Watch Items** section — anything that needs monitoring today.

7. Format the output so it can be **copy-pasted directly into Microsoft Teams or Slack**.
   Use plain text blocks for Teams/Slack compatibility, not complex Markdown tables.

8. Save to `output/11-standup-<project-name>-<date>.md`.

Print: `✅ Standup notes ready. Copy from output/11-standup-<project-name>-<date>.md`
