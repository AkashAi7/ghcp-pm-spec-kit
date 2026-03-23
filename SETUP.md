# Workshop Participant Setup Guide
## GitHub Copilot PM Spec-Kit

> **Estimated setup time:** 5–10 minutes  
> **Skill level:** No coding required — just VS Code + GitHub Copilot

---

## Prerequisites Checklist

Before the workshop, make sure you have all of the following:

| # | Requirement | How to check | Install link |
|---|------------|--------------|-------------|
| 1 | **VS Code** (any recent version) | Run `code --version` in a terminal | [code.visualstudio.com](https://code.visualstudio.com/) |
| 2 | **GitHub account** | [github.com](https://github.com) — sign up if you don't have one | [github.com/signup](https://github.com/signup) |
| 3 | **GitHub Copilot subscription** | Individual (paid) or via your org | [github.com/features/copilot](https://github.com/features/copilot) |
| 4 | **GitHub Copilot VS Code extension** | Open VS Code → Extensions (`Ctrl+Shift+X`) → search "GitHub Copilot" | Install both: **GitHub Copilot** + **GitHub Copilot Chat** |
| 5 | **Git** | Run `git --version` in a terminal | [git-scm.com](https://git-scm.com/) |

> **No Azure subscription required.** This workshop runs entirely inside VS Code using GitHub Copilot.

---

## Step 1 — Get Your Copy of the Kit

### Option A — GitHub Template (recommended)

1. Go to the workshop repository URL (provided by your facilitator)
2. Click the green **"Use this template"** button → **"Create a new repository"**
3. Set your repo name (e.g., `my-pm-workshop`) and visibility (Private is fine)
4. Click **"Create repository"**
5. Clone your new repo:

```bash
git clone https://github.com/<your-username>/my-pm-workshop.git
cd my-pm-workshop
code .
```

### Option B — Direct Clone (simplest)

If you don't need your own GitHub copy, just clone the shared repo directly:

```bash
git clone <FACILITATOR_REPO_URL> pm-workshop
cd pm-workshop
code .
```

### Option C — Download ZIP (no git required)

1. Open the GitHub repo URL in your browser
2. Click **Code → Download ZIP**
3. Extract the ZIP somewhere on your machine
4. Open VS Code → File → Open Folder → select the extracted folder

---

## Step 2 — Sign in to GitHub Copilot in VS Code

1. Open VS Code
2. Click the **Accounts** icon at the bottom-left (or the Copilot icon in the toolbar)
3. Sign in with your **GitHub account**
4. Verify Copilot is active: the Copilot icon in the status bar should be solid (not greyed out)

> If Copilot Chat asks you to choose a model, select **Claude Sonnet** or **GPT-4o** — both work well for this workshop.

---

## Step 3 — Prepare Your BRD

Bring a **Business Requirement Document (BRD)** for a project you're working on.

### Accepted formats

| Format | What to do |
|--------|-----------|
| **`.md` or `.txt`** | Drop the file directly into the `intake/` folder |
| **`.docx` / Word** | In Word: File → Save As → Plain Text (`.txt`) → save into `intake/` |
| **Google Doc** | File → Download → Plain Text (`.txt`) → save into `intake/` |
| **Paste from anywhere** | Create a new file: `intake/my-brd.md` and paste your content |

> **No BRD?** Use `intake/sample-brd.md` — it contains a full example BRD for a financial expense platform. You can run the whole pipeline on it to see the output.

### What makes a good BRD for this workshop?

Your BRD doesn't need to be perfect. Even a rough document with:
- A project name and description
- A list of what the system should do (functional requirements)
- A list of users / stakeholders
- Any known constraints or technology preferences

...is enough to generate a full set of artefacts.

---

## Step 4 — Open Copilot Chat

Press `Ctrl+Alt+I` (Windows / Linux) or `Cmd+Option+I` (Mac).

Or click the **chat bubble** icon in the VS Code sidebar.

Make sure you are in **Agent mode** (look for "Agent" in the chat mode selector at the top of the chat panel). If it shows "Ask" or "Edit", click it and switch to **Agent**.

---

## Step 5 — Run the Pipeline

Type this single command in Copilot Chat:

```
/pipeline
```

That's it. Copilot will:
1. Find your BRD in `intake/`
2. Generate all 7 artefacts one by one
3. Save each file into `output/` automatically
4. Confirm each step as it completes

**Or run individual steps:**

```
/brd      ← Just parse the BRD first to review it
/fsd      ← Generate the Functional Specification
/tdd      ← Generate the Technical Design Document
/wbs      ← Generate the Work Breakdown Structure
/plan     ← Generate the PM Plan (Gantt + risks)
/ui       ← Generate UI wireframes + HTML prototype
/todos    ← Generate persona task lists
```

---

## Step 6 — View Your Outputs

All generated files land in `output/`. Open them directly in VS Code:

| File | How to view |
|------|------------|
| `*.md` files | Right-click → **Open Preview** (renders Mermaid diagrams) |
| `*.html` file | Right-click → **Reveal in File Explorer** → double-click to open in browser |

> **Tip:** Install the **Mermaid Preview** VS Code extension for the best diagram rendering experience.

---

## Useful Extensions (Optional but Recommended)

| Extension | Why |
|-----------|-----|
| **Markdown Preview Enhanced** | Renders Mermaid diagrams in `.md` files |
| **Mermaid Chart** | Official Mermaid diagram support |
| **Live Preview** | View `.html` files inside VS Code |
| **Todo Highlight** | Highlights `TODO:` markers in generated task files |

Install in VS Code: `Ctrl+Shift+X` → search the name → Install

---

## Troubleshooting

### Copilot says "I can't find a BRD in intake/"
→ Make sure your file is saved as `.md` or `.txt` inside the `intake/` folder (not a subfolder).

### Copilot is using "Ask" mode and not creating files
→ Switch to **Agent mode** in the Copilot Chat panel (the dropdown at the top of the chat).

### Mermaid diagrams show as code, not diagrams
→ Install **Markdown Preview Enhanced** and use `Ctrl+Shift+V` to open the preview.

### The `/pipeline` command isn't recognised
→ The `copilot-instructions.md` file must be present in `.github/`. If you downloaded the ZIP, check that the `.github/` folder wasn't lost (it's a hidden folder on Mac/Linux).

---

## Workshop Agenda (Quick Reference)

| Time | Activity |
|------|----------|
| 0:00 | Introductions + setup check |
| 0:15 | Demo: facilitator runs `/pipeline` on sample BRD live |
| 0:30 | Participants drop their BRDs into `intake/` |
| 0:35 | Run `/pipeline` — watch the artefacts generate |
| 0:55 | Review outputs: FSD, TDD, WBS, Gantt, UI prototype |
| 1:10 | Try ongoing PM commands: `/sprint`, `/risks`, `/standup` |
| 1:25 | Q&A + discussion |
| 1:30 | End |

---

## Quick Command Reference

| Command | What it generates |
|---------|------------------|
| `/pipeline` | All 7 artefacts end-to-end |
| `/brd` | BRD summary + gap analysis |
| `/fsd` | Functional spec |
| `/tdd` | Technical design |
| `/wbs` | Work breakdown structure |
| `/plan` | PM plan: Gantt + risks + RACI |
| `/ui` | Wireframes + HTML prototype |
| `/todos` | Dev task lists (GitHub Issues ready) |
| `/sprint` | Sprint plan with Gantt |
| `/risks` | Risk register + heat map |
| `/status` | Weekly RAG status report |
| `/standup` | Daily standup for all 5 personas |
| `/retro` | Sprint retrospective |
| `/change <description>` | Formal change request |

See `COMMANDS.md` for the full reference.

---

*Questions? Ask your facilitator or open an issue on the workshop repository.*
