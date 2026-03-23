# Lab 6 — Generate the UI Prototype

**Time:** ~8 minutes  
**Prerequisites:** Lab 2 complete — `output/02-fsd-*.md` exists  
**Goal:** Produce a user flow diagram, ASCII wireframes, and a clickable HTML prototype.

---

## What This Lab Produces

1. **User Flow Diagram** (Mermaid) — shows all screens and how users navigate between them
2. **ASCII Wireframes** — text-based mockups of each key screen (renders in any text editor)
3. **HTML Prototype** — a single `.html` file you can open in a browser to click through the UI

---

## Step 1: Generate Wireframes and Flow Diagram

```
@workspace Follow the instructions in .github/prompts/06-generate-ui-prototype.prompt.md
Read output/02-fsd-*.md to identify all screens.
Use templates/ui_prototype_template.md for structure.
Save wireframes as output/06-ui-wireframes-<project-name>.md
```

---

## Step 2: View the User Flow Diagram

1. Open `output/06-ui-wireframes-<project-name>.md`
2. Click **Preview** (`Ctrl+Shift+V`)
3. The flowchart should show all screens with navigation arrows

---

## Step 3: Generate the HTML Prototype

This is the most impressive part — a clickable browser prototype generated entirely by Copilot:

```
@workspace Based on the wireframes in output/06-ui-wireframes-*.md and the FSD,
generate a single self-contained HTML prototype file.

Requirements:
- Pure HTML + CSS + vanilla JavaScript (no frameworks, no CDN dependencies except Google Fonts)
- Screens to include: Login, Dashboard, Expense Submission Form, Approval Queue, Analytics
- Navigation between screens using show/hide JavaScript
- Use a clean design: white background, Microsoft blue (#0078D4) primary colour, Inter font
- Include a yellow prototype banner at the top: "⚠️ UI PROTOTYPE — For Demonstration Only"
- Use realistic-looking placeholder data (not Lorem Ipsum)
- Fully responsive (works on mobile screens ≥ 375px)

Save as output/06-ui-prototype-<project-name>.html
```

---

## Step 4: Open the Prototype in Your Browser

1. In VS Code Explorer, right-click `output/06-ui-prototype-*.html`
2. Select **"Reveal in File Explorer"**
3. Double-click the `.html` file — it opens in your default browser
4. Click through the screens!

Alternatively, use the VS Code **Live Preview** extension:
- Install: Extensions → search "Live Preview" (by Microsoft)
- Right-click the `.html` file → "Show Preview"

---

## Step 5: Iterate on the Design

**Add more screens:**
```
Add a "Profile & Settings" screen to the HTML prototype where users can 
update their notification preferences and default expense category.
```

**Improve styling:**
```
Update the HTML prototype to use a card-based design for the expense list.
Each card should show: expense reference, amount (bold), category icon, status badge.
```

**Add interactivity:**
```
In the expense submission form, add JavaScript so that when the user types an 
amount over £200 in the "Meals" category, a red warning banner appears:
"Policy limit: Daily meal allowance is £50. This expense exceeds the limit."
```

---

## What You Should Have

After this lab:
- [ ] `output/06-ui-wireframes-<project-name>.md` with Mermaid flow + ASCII screens
- [ ] `output/06-ui-prototype-<project-name>.html` opens in browser
- [ ] At least 4 screens navigable in the HTML prototype
- [ ] Prototype banner visible (labelled "For Demonstration Only")
- [ ] Realistic placeholder data shown (not Lorem Ipsum)

---

**← Previous:** [Lab 5](05-generate-pm-plan.md)  
**Next:** [Lab 7 — Generate Persona TODOs →](07-generate-persona-todos.md)
