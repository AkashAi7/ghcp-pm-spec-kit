# PM Spec-Kit — Command Reference

> Quick cheat sheet for all available commands.  
> Use in **Copilot Chat** (type the command) or via **`Ctrl+Shift+P` → Run Task** in VS Code.

---

## How Commands Work

There are **3 ways** to trigger any command:

| Method | How |
|--------|-----|
| **Chat Command** | Type `/command` in Copilot Chat |
| **VS Code Task** | `Ctrl+Shift+P` → `Tasks: Run Task` → pick from "PM:" list |
| **Prompt File** | `Ctrl+Shift+P` → `GitHub Copilot: Run Prompt` → select file |

You can also reference files in chat using `#`:
- `#file:intake/my-brd.md` → attach your BRD to the chat message
- `#file:output/04-wbs-<project>.md` → attach a specific artefact

---

## Core Pipeline Commands

These run **in order** to generate the full artefact suite from a BRD.

| Command | Alias | What It Does | Output File |
|---------|-------|-------------|------------|
| `/pipeline` | `/full`, `/all` | Runs all 7 steps automatically | `output/01` → `output/07` |
| `/brd` | `/parse`, `/step1` | Parse BRD → structured summary | `01-brd-summary-*.md` |
| `/fsd` | `/spec`, `/step2` | Functional Spec Document | `02-fsd-*.md` |
| `/tdd` | `/design`, `/step3` | Technical Design Document | `03-tdd-*.md` |
| `/wbs` | `/breakdown`, `/step4` | Work Breakdown Structure | `04-wbs-*.md` |
| `/plan` | `/pmplan`, `/step5` | PM Plan (Gantt + Risk + Comms) | `05-pm-plan-*.md` |
| `/ui` | `/wireframes`, `/step6` | UI Prototype + HTML | `06-ui-*.md` + `.html` |
| `/todos` | `/tasks`, `/step7` | Persona TODO lists | `07-persona-todos-*.md` |

**One-shot:** Drop your BRD in `intake/` → type `/pipeline` → all 8 files created automatically.

---

## Ongoing PM Commands

Use these **throughout the project lifecycle** — after the initial pipeline has run.

| Command | Alias | What It Does | Output File |
|---------|-------|-------------|------------|
| `/sprint` | `/sprint-plan` | Sprint plan from WBS | `08-sprint-plan-*.md` |
| `/risks` | `/risk-register` | Deep risk analysis + heat map | `09-risk-register-*.md` |
| `/status` | `/status-report` | Weekly RAG status report | `10-status-report-*-weekNN.md` |
| `/standup` | `/daily` | Daily standup notes for all personas | `11-standup-*-<date>.md` |
| `/retro` | `/retrospective` | Sprint retrospective template | `12-retro-*-sprintN.md` |
| `/change` | `/cr` | Formal change request + impact analysis | `13-change-request-CR-*.md` |
| `/release` | `/release-notes` | Release notes for a version | `14-release-notes-*-v*.md` |
| `/handover` | `/closure` | Handover / project closure document | `15-handover-*.md` |

---

## `#` File Shortcuts

Use these in Copilot Chat to attach specific files as context:

```
#file:intake/                     → List what's in the BRD folder
#file:intake/my-brd.md            → Attach your BRD
#file:output/02-fsd-myproject.md  → Attach the FSD
#file:output/04-wbs-myproject.md  → Attach the WBS
#file:output/08-sprint-plan-*.md  → Attach the sprint plan
```

**Combine with a command:**
> `Analyse the risks in #file:output/02-fsd-myproject.md and run /risks`

> `Using #file:intake/my-brd.md generate just the /fsd`

---

## Command Examples (copy & paste into Copilot Chat)

```
/pipeline
```
> Runs the full pipeline. Requires a BRD in `intake/`.

```
/brd
```
> Just parses the BRD and saves a structured summary.

```
/sprint
```
> Generates sprint breakdown from the existing WBS.

```
/status
```
> Generates this week's project status report.

```
/standup
```
> Generates today's standup notes for all 5 personas.

```
/change We need to add a mobile app to the scope
```
> Produces a formal change request with impact analysis for the mobile app addition.

```
/release v1.0.0
```
> Generates release notes for version 1.0.0.

```
/retro sprint 2
```
> Generates the Sprint 2 retrospective document.

```
/risks
```
> Produces a full risk register with heat map and mitigation strategies.

```
/handover
```
> Generates the project handover document for closure or team transition.

---

## Prompt Files (for manual / Command Palette use)

| File | Description |
|------|-------------|
| `00-run-full-pipeline.prompt.md` | Master orchestrator — runs all 7 steps |
| `01-parse-brd.prompt.md` | BRD parsing |
| `02-generate-fsd.prompt.md` | FSD generation |
| `03-generate-tdd.prompt.md` | TDD generation |
| `04-generate-wbs.prompt.md` | WBS generation |
| `05-generate-pm-plan.prompt.md` | PM Plan |
| `06-generate-ui-prototype.prompt.md` | UI Prototype |
| `07-generate-persona-todos.prompt.md` | Persona TODOs |
| `08-sprint-plan.prompt.md` | Sprint planning |
| `09-risk-deep-dive.prompt.md` | Risk analysis |
| `10-status-report.prompt.md` | Status report |
| `11-standup-notes.prompt.md` | Daily standup |
| `12-retrospective.prompt.md` | Sprint retro |
| `13-change-request.prompt.md` | Change request |
| `14-release-notes.prompt.md` | Release notes |
| `15-handover.prompt.md` | Project handover |

---

## VS Code Tasks (Keyboard Access)

`Ctrl+Shift+P` → `Tasks: Run Task` → all tasks start with `PM:`

| Task Name | What It Does |
|-----------|-------------|
| `PM: Run Full Pipeline` | Full pipeline automation |
| `PM: Step 1 — Parse BRD` | |
| `PM: Step 2 — Generate FSD` | |
| `PM: Step 3 — Generate TDD` | |
| `PM: Step 4 — Generate WBS` | |
| `PM: Step 5 — Generate PM Plan` | |
| `PM: Step 6 — Generate UI Prototype` | |
| `PM: Step 7 — Generate Persona TODOs` | |
| `PM: Sprint Plan` | |
| `PM: Risk Deep Dive` | |
| `PM: Weekly Status Report` | |
| `PM: Daily Standup Notes` | |
| `PM: Sprint Retrospective` | |
| `PM: Change Request` | |
| `PM: Release Notes` | |
| `PM: Handover Document` | |

---

## Quick Start (30 seconds)

1. Drop your BRD file into `intake/my-brd.md`
2. Open Copilot Chat (`Ctrl+Alt+I`)
3. Type: `/pipeline`
4. Watch all 8 files appear in `output/`

That's it.
