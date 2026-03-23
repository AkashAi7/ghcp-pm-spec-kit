# GitHub Copilot PM Spec-Kit

> Turn a Business Requirement Document (BRD) into a full set of project artefacts — in one chat session.

---

## What is this?

This is a hands-on lab kit. You bring a BRD (or use one of the samples provided), and GitHub Copilot generates everything your team needs to start a project:

| # | What gets generated |
|---|---------------------|
| 1 | BRD Summary — structured requirements |
| 2 | Functional Specification (FSD) |
| 3 | Technical Design Document (TDD) |
| 4 | Work Breakdown Structure (WBS) |
| 5 | Project Management Plan (Gantt + Risks) |
| 6 | UI Wireframes + HTML Prototype |
| 7 | Persona TODO lists (ready for GitHub Issues) |

---

## Prerequisites — Install These First

You need three things before starting. Install them in this order:

### 1. Install Git
Git is used to download (clone) this project to your computer.

- Go to [https://git-scm.com/downloads](https://git-scm.com/downloads)
- Download and install for your operating system
- Accept all defaults during installation

To verify it worked, open a terminal and run:
```
git --version
```
You should see something like `git version 2.x.x`.

---

### 2. Install VS Code
VS Code is the editor you will use for this lab.

- Go to [https://code.visualstudio.com/](https://code.visualstudio.com/)
- Download and install for your operating system

---

### 3. Install the GitHub Copilot Extension

> You need a GitHub account with an active Copilot licence (free tier works).

1. Open VS Code
2. Click the **Extensions** icon in the left sidebar (or press `Ctrl+Shift+X`)
3. Search for **GitHub Copilot**
4. Click **Install**
5. When prompted, click **Sign in to GitHub** and follow the steps

Once signed in, you will see the Copilot icon in the bottom status bar of VS Code.

---

## Getting the Project — Clone It

Now download this project to your computer. Open a terminal (Command Prompt, PowerShell, or Terminal on Mac/Linux) and run:

```bash
git clone https://github.com/AkashAi7/ghcp-pm-spec-kit.git
```

This creates a folder called `ghcp-pm-spec-kit` wherever you ran the command.

Then open it in VS Code:

```bash
cd ghcp-pm-spec-kit
code .
```

> **What does `code .` do?** It opens the current folder in VS Code. If it doesn't work, open VS Code manually and go to `File → Open Folder` → select the `ghcp-pm-spec-kit` folder.

---

## Step 1 — Pick a BRD

Go to the `intake/` folder. Either:
- Drop your own BRD file there (`.md` or `.txt`), or
- Use one of the ready-made samples from `sample-brds/`

> **Have a `.docx` file?** Open it in Word → Save As → Plain Text (`.txt`) → save it into `intake/`.

Copy the BRD file you want to use into the `intake/` folder before continuing.

---

## Step 2 — Open Copilot Chat

Press `Ctrl+Alt+I` or click the Copilot icon in the left sidebar of VS Code.

The Copilot Chat panel will open on the right (or bottom) side of VS Code.

At the **top of the chat panel**, you will see a mode/agent selector dropdown. Click it and choose **PM Spec-Kit**. This loads all the PM rules and commands automatically.

> **Don't see PM Spec-Kit in the list?** Make sure you opened the `ghcp-pm-spec-kit` folder in VS Code (not just a single file). The custom agent is tied to this workspace.

---

## Step 3 — Run Everything with One Command

In the Copilot Chat panel, type this single command and press Enter:

```
/pipeline
```

> **That's the "run all" command.** This one command triggers all 7 steps automatically:
> Parse BRD → FSD → TDD → WBS → PM Plan → UI Wireframes → Persona TODOs
>
> Copilot will read your BRD from `intake/` and generate each artefact one by one,
> saving them into the `output/` folder. No other input needed from you.

---

## Step 4 — Review Your Outputs

Open the `output/` folder. You will find one file per artefact, named clearly, e.g.:

```
output/
  01-brd-summary-<project>.md
  02-fsd-<project>.md
  03-tdd-<project>.md
  04-wbs-<project>.md
  05-pm-plan-<project>.md
  06-ui-wireframes-<project>.md
  06-ui-prototype-<project>.html   ← open this in a browser
  07-persona-todos-<project>.md
```

---

## Run Steps One at a Time (Optional)

If you prefer to go step by step, use these commands in chat:

| Command | What it does |
|---------|--------------|
| `/brd` | Parse and summarise the BRD |
| `/fsd` | Generate the Functional Specification |
| `/tdd` | Generate the Technical Design |
| `/wbs` | Generate the Work Breakdown Structure |
| `/plan` | Generate the PM Plan |
| `/ui` | Generate UI wireframes + HTML prototype |
| `/todos` | Generate persona TODO lists |

---

## Sample BRDs Included

Not sure what a BRD looks like? Several real-world samples are in `sample-brds/`:

| File | Project |
|------|---------|
| `Standard-BRD-001-ECommerce-Platform.md` | E-Commerce website |
| `Standard-BRD-002-Healthcare-Patient-Portal.md` | Healthcare patient portal |
| `Standard-BRD-003-IoT-Analytics-Dashboard.md` | IoT data dashboard |
| `Standard-BRD-004-FinTech-Banking-Platform.md` | Banking / FinTech platform |
| `Standard-BRD-005-ProjectManagement-SaaS.md` | Project management SaaS tool |

Copy any one of them into `intake/` to get started immediately.

---

## Folder Guide

```
intake/          ← Put your BRD here
sample-brds/     ← Sample BRDs to try out
output/          ← Generated artefacts appear here
templates/       ← Document templates used by Copilot
lab/             ← Step-by-step lab guide (start with lab/00-overview.md)
```

---

## Need Help?

- Lab walkthrough: [lab/00-overview.md](lab/00-overview.md)
- Setup guide: [SETUP.md](SETUP.md)
- Full command list: [COMMANDS.md](COMMANDS.md)


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
