---
mode: agent
description: "STEP 8 — Persona-wise development: map your TODO items to code stubs, file scaffolds, and Copilot prompts. Run /dev <persona> after /pipeline completes. Valid: frontend | backend | data-engineer | data-analyst | sre"
---

# Step 8 — Persona-Wise Development: User Stories → Code

## How to use this prompt

Type one of the following in Copilot Chat (with the pm-spec-kit agent selected):

```
/dev frontend
/dev backend
/dev data-engineer
/dev data-analyst
/dev sre
```

If no persona is specified, ask the user to choose one before continuing.

---

## Prerequisites

- `output/07-persona-todos-<project-name>.md` must exist (run `/todos` first if missing).
- `output/02-fsd-<project-name>.md` must exist for requirement traceability.
- `output/04-wbs-<project-name>.md` must exist for task ID traceability.
- The matching `persona-instructions/<persona>.instructions.md` file must be loaded as context.

---

## Instructions

### 1. Identify the persona

Read the persona argument from the user's message:
- `frontend` → Frontend Engineer → load `persona-instructions/frontend-engineer.instructions.md`
- `backend` → Backend Engineer → load `persona-instructions/backend-engineer.instructions.md`
- `data-engineer` → Data Engineer → load `persona-instructions/data-engineer.instructions.md`
- `data-analyst` → Data Analyst → load `persona-instructions/data-analyst.instructions.md`
- `sre` → SRE / Cloud Engineer → load `persona-instructions/sre-cloud-engineer.instructions.md`

**Read the persona instruction file in full before generating any code. Apply all conventions, tech stack defaults, and testing requirements from it.**

### 2. Load the TODO list

Read `output/07-persona-todos-<project-name>.md`.
Extract only the TODO items for the selected persona.

### 3. For each TODO item, generate the following

#### a) Traceability header (always include this)
```
// TODO ID:  <e.g. FE-001>
// WBS Task: <WBS task ID and title>
// FSD Req:  <FSD requirement ID, e.g. FSD-FR-04>
// Sprint:   <sprint number from the TODO list>
```

#### b) File scaffold
Create the file(s) that this TODO requires, with:
- Correct folder path following the conventions in the persona instruction file
- Correct file extension and naming convention
- Skeleton structure (imports, function/class stubs, type signatures)
- TODOs inside the file showing what needs to be implemented

#### c) Implementation prompt
Write a ready-to-use Copilot prompt the developer can paste into Chat to implement the stub:
```
Implement [function/component name] in [file path].
Requirements: [FSD requirement text]
Acceptance criteria: [from the TODO item]
Follow conventions in persona-instructions/<persona>.instructions.md
```

#### d) Test scaffold (where applicable)
Generate a matching test file stub with:
- At least one `describe` / `it` block per acceptance criterion
- Correct test framework for the persona (Vitest for frontend, xUnit/.NET Test or Jest for backend, pytest for data, etc.)
- Traceability comment linking back to the TODO ID

### 4. Output format

For each TODO item, output:

```
---
## <TODO ID> — <TODO title>

**Source:** WBS <id> | FSD <id> | Sprint <n>

### File: `<path/to/file>`
<code scaffold>

### Test: `<path/to/test-file>`
<test scaffold>

### Copilot implementation prompt
<ready-to-use prompt>
---
```

### 5. Completion message

After processing all TODO items for the persona, print:

```
✅ Step 8 done — <Persona Name> development scaffolds generated.

Files to create:
  <list of all file paths>

Run the Copilot implementation prompts above file-by-file, or run:
  /dev <next-persona>   to scaffold another team member's work.
```

---

## Traceability rule

Every generated file MUST contain a header comment block with the TODO ID, WBS task, and FSD requirement.
Never generate a file without this header — it is the link between the spec and the code.
