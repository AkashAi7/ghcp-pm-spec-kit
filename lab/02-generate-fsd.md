# Lab 2 — Generate the Functional Specification Document (FSD)

**Time:** ~10 minutes  
**Prerequisites:** Lab 1 complete — `output/01-brd-summary-*.md` exists  
**Goal:** Expand each BRD requirement into a detailed, screen-level functional specification.

---

## What is an FSD?

While the BRD says *"Users must be able to log in"*, the FSD says:

> *"The login screen displays an email field (validated RFC 5322 on blur), a password field with show/hide toggle, a 'Forgot Password' link, and a Sign In button (disabled until both fields are non-empty). After 3 consecutive failed attempts, the account is locked for 15 minutes and error code ERR-LOGIN-003 is shown."*

The FSD is the **contract** between stakeholders and the development team.

---

## Step 1: Run the FSD Prompt

Open Copilot Chat and paste:

```
@workspace Follow the instructions in .github/prompts/02-generate-fsd.prompt.md
Read output/01-brd-summary-*.md as the source.
Use templates/fsd_template.md for structure.
Generate a complete FSD and save it as output/02-fsd-<project-name>.md
```

This will take a minute — Copilot will generate each module in turn.

---

## Step 2: Review and Iterate

Once the FSD is generated, review it. Look for:

**Check these sections:**
- [ ] Every BRD-FR-xx has a corresponding FSD-FR-xx entry
- [ ] User stories are present (`As a [persona]...`)
- [ ] Acceptance criteria use Given/When/Then format
- [ ] Business rules are explicitly stated
- [ ] Each section has back-references like `→ BRD-FR-03`

**If a section needs more detail:**
```
Expand FSD-FR-05 (the approval workflow) with more detailed acceptance criteria,
including edge cases for when a manager is on leave.
```

**If you want more screen-level detail:**
```
Add detailed UI descriptions for the expense submission screen — include 
exact field labels, validation messages, and error states.
```

---

## Step 3: Add a Data Dictionary

If the Data Dictionary section is sparse:

```
Based on the FSD, generate a complete Data Dictionary for all entities
(User, ExpenseClaim, Receipt, Approval, AuditLog).
Include field names, types, constraints, and descriptions.
Append it to output/02-fsd-<project-name>.md
```

---

## Tips

- **Traceability is key**: Every FSD requirement should trace back to a BRD requirement.
  If Copilot misses a `→ BRD-FR-xx` reference, ask it to add them:
  ```
  Add BRD reference tags (→ BRD-FR-xx) to each FSD requirement in the document.
  ```

- **Use personas**: The personas defined in the BRD should appear in user stories.
  If they're missing, ask:
  ```
  Rewrite the user stories using the stakeholder personas identified in the BRD.
  ```

---

## What You Should Have

After this lab:
- [ ] `output/02-fsd-<project-name>.md` saved
- [ ] Each BRD-FR-xx expanded into a detailed FSD-FR-xx entry
- [ ] User stories and acceptance criteria for each requirement
- [ ] Data Dictionary section populated
- [ ] Integration Points section included

---

**← Previous:** [Lab 1](01-intake.md)  
**Next:** [Lab 3 — Generate the TDD →](03-generate-tdd.md)
