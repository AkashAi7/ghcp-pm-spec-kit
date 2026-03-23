# Lab 7 — Generate Persona-Wise TODO Work Items

**Time:** ~8 minutes  
**Prerequisites:** Labs 2, 3, and 4 complete  
**Goal:** Produce GitHub-Issues-ready task lists for each engineering team persona.

---

## The Five Personas

| Persona | Covers |
|---------|--------|
| 👩‍💻 **Frontend Engineer** | React/Angular/Vue, UI components, accessibility, E2E tests |
| ⚙️ **Backend Engineer** | REST APIs, business logic, auth, background jobs, unit tests |
| 🗄️ **Data Engineer** | Azure SQL, Cosmos DB, Azure Data Factory, Microsoft Fabric, ETL pipelines |
| 📊 **Data Analyst** | Power BI reports, DAX measures, KPIs, Fabric notebooks, data validation |
| ☁️ **SRE / Cloud Engineer** | Azure infrastructure (Bicep), GitHub Actions CI/CD, monitoring, security |

---

## Step 1: Generate Persona TODOs

```
@workspace Follow the instructions in .github/prompts/07-generate-persona-todos.prompt.md
Read output/04-wbs-*.md and output/03-tdd-*.md as sources.
Use templates/persona_todos_template.md for structure.
Generate all persona TODO items and save as output/07-persona-todos-<project-name>.md
```

---

## Step 2: Review the TODOs

For each persona, verify the tasks look right:

**Frontend:** Do the tasks match the wireframes from Lab 6?
**Backend:** Does every FSD-FR-xx have a corresponding backend task?
**Data Engineer:** Are Fabric, ADF, and schema tasks all covered?
**Data Analyst:** Are the Power BI reports and DAX measures defined?
**SRE/Cloud:** Are Bicep templates, CI/CD, and monitoring covered?

---

## Step 3: Enrich a Specific Persona

Want more detail for a specific role? Ask Copilot:

```
Expand all Backend Engineer TODO items. For each one, add:
- The specific API endpoint (method + path) 
- The expected request payload shape
- The expected response codes and shapes
- The OpenAPI spec implications
```

```
Expand all SRE/Cloud Engineer TODO items. For each Azure resource provisioning task,
add a Bicep resource snippet showing the key properties to configure.
```

---

## Step 4: Export as GitHub Issues

The TODO file includes a GitHub Issues Export section. Use it to create real issues:

1. Go to your GitHub repository
2. **Issues → New Issue**
3. Copy the title, labels, and body from the export section
4. Create the issue

**Or use GitHub CLI to bulk-create issues:**

```powershell
# Install GitHub CLI if needed
winget install GitHub.cli
gh auth login

# Create an issue from a template
gh issue create --title "TODO-FE-001 · Implement Login Screen" `
  --body "See output/07-persona-todos-*.md for full description" `
  --label "frontend,sprint-1" `
  --milestone "Sprint 1"
```

---

## Step 5: Generate a Sprint Backlog

Turn the TODOs into a sprint-organised backlog:

```
From the persona TODOs in output/07-persona-todos-*.md, 
generate a Sprint Backlog for Sprint 1.
List all tasks assigned to Sprint 1, grouped by persona,
sorted by priority (story points descending).
Show total story points per persona and grand total.
```

---

## Step 6: Discussion — What Did Copilot Get Right and Wrong?

This is a great moment to reflect on the generated content with your team / facilitator:

**Discussion questions:**
1. Are the story point estimates realistic for your team's actual velocity?
2. Are there any tasks that Copilot missed or got wrong in terms of technical detail?
3. How would you use this as a starting point vs. building from scratch?
4. Which artefact was most valuable? Which needs the most human input?

---

## What You Should Have

After this lab (and the full pipeline):
- [ ] `output/07-persona-todos-<project-name>.md` saved
- [ ] Detailed TODO items for all 5 personas
- [ ] Master checklist at the end of the file
- [ ] GitHub Issues Export section ready to use
- [ ] **All 7 output files** saved in `output/`

---

## You've Completed the Pipeline! 🎉

Your `output/` folder should now contain:

```
output/
├── 01-brd-summary-<project-name>.md
├── 02-fsd-<project-name>.md
├── 03-tdd-<project-name>.md
├── 04-wbs-<project-name>.md
├── 05-pm-plan-<project-name>.md
├── 06-ui-wireframes-<project-name>.md
├── 06-ui-prototype-<project-name>.html
└── 07-persona-todos-<project-name>.md
```

This represents **weeks of traditional PM/engineering work** — generated in about an hour using GitHub Copilot.

---

**← Previous:** [Lab 6](06-generate-ui-prototype.md)  
**← Back to Overview:** [Lab Guide Overview](00-overview.md)
