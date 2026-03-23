# GitHub Copilot PM Spec-Kit
### From BRD to Full Project Artefacts — Powered by GitHub Copilot

This workshop kit demonstrates how GitHub Copilot can accelerate project delivery by
transforming a **Business Requirement Document (BRD)** into a complete suite of project
artefacts in under an hour.

> **Workshop participants:** See [SETUP.md](SETUP.md) for the full step-by-step setup guide.  
> **Facilitators:** See the [Distribution Guide](#distributing-to-workshop-participants) at the bottom of this file.

---

## What This Kit Generates

| # | Artefact | Description |
|---|---------|-------------|
| 1 | **BRD Summary** | Parsed + structured requirements with gap analysis |
| 2 | **Functional Specification (FSD)** | Screen-level requirements, user stories, acceptance criteria |
| 3 | **Technical Design (TDD)** | Architecture, API catalogue, DB schema, Azure resource map |
| 4 | **Work Breakdown Structure (WBS)** | Tasks × personas × effort estimates with Gantt input |
| 5 | **Project Management Plan** | Gantt chart, Risk Register, Communication Plan |
| 6 | **UI Prototype** | Mermaid flow + ASCII wireframes + clickable HTML |
| 7 | **Persona TODO Items** | GitHub-Issues-ready tasks for 5 engineering personas |

---

## Methodology: Spec-Kit Driven Development (SKDD)

This kit implements **SKDD** — a delivery methodology where the BRD is the single source of truth and AI generates the full artefact chain (FSD → TDD → WBS → Tasks) automatically. See [SKDD.md](SKDD.md) for the full methodology guide.

---

## Custom Agent Mode

A dedicated **PM Spec-Kit chat mode** is included. Once you open this folder in VS Code, you can switch Copilot Chat to the **PM Spec-Kit** mode — it becomes a specialist agent pre-loaded with all SKDD rules, the full command set, and workspace context.

**How to activate:** In the Copilot Chat panel → click the mode selector → choose **PM Spec-Kit**.

---

## Quick Start

### Step 1 — Open this folder in VS Code
```
File → Open Folder → GHCP-Spec-Kit-PM
```

### Step 2 — Drop your BRD in `intake/`

Supported formats:
- `.md` or `.txt` — drop directly, Copilot reads natively
- `.doc` / `.docx` — see `intake/README.md` for conversion instructions

No BRD yet? Use `intake/sample-brd.md` to test the pipeline.

### Step 3 — Open Copilot Chat

Press `Ctrl+Alt+I` (or click the Copilot icon in the VS Code sidebar).

### Step 4 — Run the Full Pipeline

Paste this into Copilot Chat:

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

Or run each step individually using the prompt files in `.github/prompts/`.

---

## Directory Structure

```
📁 GHCP-Spec-Kit-PM/
├── 📁 .github/
│   ├── 📄 copilot-instructions.md     ← Loaded by Copilot automatically
│   └── 📁 prompts/                    ← Step-by-step runnable prompts
│       ├── 01-parse-brd.prompt.md
│       ├── 02-generate-fsd.prompt.md
│       ├── 03-generate-tdd.prompt.md
│       ├── 04-generate-wbs.prompt.md
│       ├── 05-generate-pm-plan.prompt.md
│       ├── 06-generate-ui-prototype.prompt.md
│       └── 07-generate-persona-todos.prompt.md
│
├── 📁 intake/                         ← DROP YOUR BRD HERE
│   ├── README.md                      ← .doc conversion guide
│   └── sample-brd.md                  ← Ready-to-use sample BRD
│
├── 📁 templates/                      ← Output structure templates
│   ├── brd_template.md
│   ├── fsd_template.md
│   ├── tdd_template.md
│   ├── wbs_template.md
│   ├── pm_plan_template.md
│   ├── ui_prototype_template.md
│   ├── persona_todos_template.md
│   ├── resource_plan_template.md
│   └── service_scope_template.md
│
├── 📁 output/                         ← Generated artefacts land here
│
├── 📁 lab/                            ← Workshop lab guide
│   ├── 00-overview.md                 ← Start here
│   ├── 01-intake.md
│   ├── 02-generate-fsd.md
│   ├── 03-generate-tdd.md
│   ├── 04-generate-wbs.md
│   ├── 05-generate-pm-plan.md
│   ├── 06-generate-ui-prototype.md
│   └── 07-generate-persona-todos.md
│
├── 📁 memory/
│   └── constitution.md                ← Extended AI rules
│
└── 📁 specs/
    └── input_requirements.md          ← Legacy input (still supported)
```

---

## Engineering Personas

Persona TODO items are generated for these five roles:

| Persona | Covers |
|---------|--------|
| Frontend Engineer | React/Angular/Vue, UI, accessibility, tests |
| Backend Engineer | APIs, business logic, auth, background jobs |
| Data Engineer | Azure Data Factory, Fabric, SQL/NoSQL, ETL |
| Data Analyst | Power BI, DAX, KPIs, Fabric notebooks |
| SRE / Cloud Engineer | Azure infra (Bicep), CI/CD, monitoring, security |

---

## For Workshop Facilitators

See `lab/00-overview.md` for the full facilitator guide including:
- Timing breakdown (60-minute workshop plan)
- Common participant issues and solutions
- Tips for getting the best Copilot output

---

## Distributing to Workshop Participants

### Recommended: GitHub Template Repository

This is the cleanest way to give every participant their own isolated copy:

**One-time setup (you do this once):**

```bash
# 1. Create a new GitHub repo for the kit
gh repo create my-org/ghcp-pm-workshop --public

# 2. Push this project to it
cd GHCP-Spec-Kit-PM
git init
git add .
git commit -m "Initial workshop kit"
git remote add origin https://github.com/my-org/ghcp-pm-workshop.git
git push -u origin main

# 3. Mark it as a Template Repository:
# On GitHub → Settings → General → tick "Template repository"
```

**What participants do:**
1. Go to `https://github.com/my-org/ghcp-pm-workshop`
2. Click **"Use this template"** → **"Create a new repository"**
3. Clone their new repo → open in VS Code → done

The `.gitignore` is set up so each person's `output/` files stay local and don't get pushed (clean separation).

---

### Alternative: Share a ZIP

If participants don't have GitHub accounts:

```bash
# From the project root — creates a clean zip excluding output files and git history
git archive --format=zip --output=ghcp-pm-workshop.zip HEAD
```

Then share `ghcp-pm-workshop.zip` via Teams, email, or a shared drive.  
Participants extract it, open the folder in VS Code, and follow [SETUP.md](SETUP.md).

---

### Pre-Workshop Checklist (send to participants 48h before)

Send participants this checklist before the session:

```
Before the workshop, please:

✅ Install VS Code: https://code.visualstudio.com/
✅ Install the GitHub Copilot extension (search in VS Code Extensions)
✅ Confirm your GitHub Copilot subscription is active
✅ Get the workshop kit: [REPO/ZIP LINK]
   - Option A: "Use this template" on GitHub → clone your repo
   - Option B: Extract the ZIP → open folder in VS Code
✅ Prepare your BRD (any project, any format):
   - Save as .md or .txt into the intake/ folder
   - No BRD? Use intake/sample-brd.md
✅ Read SETUP.md inside the kit — it covers everything step by step
```

---

## Prerequisites

| Requirement | Notes |
|-------------|-------|
| VS Code 1.90+ | [code.visualstudio.com](https://code.visualstudio.com/) |
| GitHub Copilot extension | VS Code Extensions → "GitHub Copilot" |
| GitHub Copilot Chat extension | VS Code Extensions → "GitHub Copilot Chat" |
| GitHub Copilot subscription | Individual or organisation licence |
| Git (for clone option) | [git-scm.com](https://git-scm.com/) |
| Markdown Preview Mermaid (optional) | For diagram rendering in VS Code |

---

*Built to demonstrate GitHub Copilot's capabilities in project management and engineering workflows.*
