# 🧪 Workshop Lab Guide — GitHub Copilot PM Spec-Kit

**From BRD to Full Project Artefacts in 60 Minutes**

---

## What You Will Build Today

Starting with a single Business Requirement Document (BRD), you will use
**GitHub Copilot** to automatically generate a full suite of project artefacts:

| # | Artefact | File Produced |
|---|---------|---------------|
| 1 | Parsed BRD Summary | `output/01-brd-summary-*.md` |
| 2 | Functional Specification Document | `output/02-fsd-*.md` |
| 3 | Technical Design Document | `output/03-tdd-*.md` |
| 4 | Work Breakdown Structure | `output/04-wbs-*.md` |
| 5 | Project Management Plan | `output/05-pm-plan-*.md` |
| 6 | UI Wireframes + HTML Prototype | `output/06-ui-*.md` + `.html` |
| 7 | Persona-Wise TODO Items | `output/07-persona-todos-*.md` |

---

## Prerequisites

Before starting the labs, ensure you have:

- [ ] **VS Code** installed (version 1.90+)
- [ ] **GitHub Copilot** extension installed and signed in
   → Install from: Extensions (`Ctrl+Shift+X`) → search "GitHub Copilot"
- [ ] This repository cloned or unzipped on your machine
- [ ] The workspace opened in VS Code: `File → Open Folder → GHCP-Spec-Kit-PM`

### Verify Copilot is Working
Open **Copilot Chat** (`Ctrl+Alt+I`) and type:
```
Hello! What is this workspace for?
```
Copilot should respond with context about this PM Spec-Kit — confirming it has read
the `.github/copilot-instructions.md` file automatically.

---

## Lab Structure

| Lab | Title | Time |
|-----|-------|------|
| [Lab 1](01-intake.md) | Load Your BRD | 5 min |
| [Lab 2](02-generate-fsd.md) | Generate the FSD | 10 min |
| [Lab 3](03-generate-tdd.md) | Generate the TDD | 10 min |
| [Lab 4](04-generate-wbs.md) | Generate the WBS | 10 min |
| [Lab 5](05-generate-pm-plan.md) | Generate the PM Plan | 8 min |
| [Lab 6](06-generate-ui-prototype.md) | Generate UI Prototype | 8 min |
| [Lab 7](07-generate-persona-todos.md) | Generate Persona TODOs | 8 min |
| [Lab 8](08-persona-wise-development.md) | From User Stories to Code — Persona-Wise Dev | 20–30 min |

> **Lab 8** is the implementation lab. After the pipeline generates all artefacts,
> each team member picks their persona and uses Copilot to implement actual code
> from their TODO list — guided by the persona instruction files in `persona-instructions/`.

---

## Persona Instruction Files

The `persona-instructions/` folder contains a custom Copilot instruction file for each engineering role.
These files define tech stack defaults, code conventions, testing requirements, and implementation prompts
specific to each persona. They are used in **Lab 8** but can be used at any time during development.

| File | Persona |
|------|---------|
| `persona-instructions/frontend-engineer.instructions.md` | Frontend Engineer |
| `persona-instructions/backend-engineer.instructions.md` | Backend Engineer |
| `persona-instructions/data-engineer.instructions.md` | Data Engineer |
| `persona-instructions/data-analyst.instructions.md` | Data Analyst |
| `persona-instructions/sre-cloud-engineer.instructions.md` | SRE / Cloud Engineer |

To use one, reference it in Copilot Chat:
```
#file:persona-instructions/frontend-engineer.instructions.md
```

---

## Quick-Start: Run the Full Pipeline at Once

If you want to generate **all artefacts in one shot**, paste this into Copilot Chat:

```
@workspace I have dropped my BRD in the intake/ folder.
Please run the full artefact pipeline:
1. Parse the BRD and save to output/
2. Generate FSD using templates/fsd_template.md
3. Generate TDD using templates/tdd_template.md
4. Generate WBS using templates/wbs_template.md
5. Generate PM Plan using templates/pm_plan_template.md
6. Generate UI Prototype (wireframes + HTML) using templates/ui_prototype_template.md
7. Generate Persona TODOs using templates/persona_todos_template.md
Save each as a separate file in output/.
```

---

## Tips for the Best Results

1. **Be specific in your BRD** — the more detail you provide, the better the output.
2. **Iterate with follow-up prompts** — if a section isn't detailed enough:
   ```
   Expand the Approval Workflow section of the FSD with more detailed acceptance criteria.
   ```
3. **Reference previous outputs** — Copilot Chat has context of files you mention:
   ```
   Using output/02-fsd-*.md, expand the API section in the TDD.
   ```
4. **Run prompt files directly** — In VS Code Copilot Chat, you can type `/` to browse and run prompt files.

---

## Workspace Navigation

```
📁 GHCP-Spec-Kit-PM/
├── 📁 .github/
│   ├── 📄 copilot-instructions.md    ← Copilot reads this automatically
│   └── 📁 prompts/                   ← Run these step by step
│       ├── 01-parse-brd.prompt.md
│       ├── 02-generate-fsd.prompt.md
│       ├── 03-generate-tdd.prompt.md
│       ├── 04-generate-wbs.prompt.md
│       ├── 05-generate-pm-plan.prompt.md
│       ├── 06-generate-ui-prototype.prompt.md
│       └── 07-generate-persona-todos.prompt.md
├── 📁 intake/                        ← DROP YOUR BRD HERE
│   ├── README.md
│   └── sample-brd.md                 ← Use this if you don't have a BRD yet
├── 📁 templates/                     ← Artefact structure templates
│   ├── fsd_template.md
│   ├── tdd_template.md
│   ├── wbs_template.md
│   ├── pm_plan_template.md
│   ├── ui_prototype_template.md
│   └── persona_todos_template.md
├── 📁 output/                        ← Generated artefacts land here
├── 📁 lab/                           ← You are here
└── 📄 README.md                      ← Main documentation
```

---

## Facilitator Notes

**For workshop facilitators** — timing guidance:

- **00:00–05:00** — Introduction, explain the workflow, participants open VS Code
- **05:00–10:00** — Lab 1: Load BRD, verify Copilot is reading it
- **10:00–20:00** — Lab 2–3: FSD + TDD generation (guided, explain the output)
- **20:00–35:00** — Lab 4–5: WBS + PM Plan (participants work independently)
- **35:00–50:00** — Lab 6–7: UI Prototype + Persona TODOs
- **50:00–60:00** — Review outputs, discussion, Q&A

**Common Issues:**
- If Copilot isn't reading the workspace: ensure `@workspace` is in the prompt
- If output files aren't saved: remind participants Copilot generates content; they need to click "Insert into file" or copy to a new file
- Encourage participants to **bring their own BRD** for the most engaging experience
