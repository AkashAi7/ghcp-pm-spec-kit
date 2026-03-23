# Intake Folder — Drop Your BRD Here

This is where you place your **Business Requirement Document (BRD)** before running the Copilot artefact pipeline.

---

## Supported Input Formats

| Format | Instructions |
|--------|-------------|
| `.md` | Drop directly into this folder — Copilot can read it natively |
| `.txt` | Drop directly into this folder — Copilot can read it natively |
| `.doc` / `.docx` | See conversion options below |
| Pasted content | Create a new `.md` file and paste your BRD text |

---

## Converting `.doc` / `.docx` Files

GitHub Copilot **cannot read binary Word files** directly. Use one of these methods:

### Option A — Save as Plain Text (quickest)
1. Open your `.doc` file in Microsoft Word
2. **File → Save As → Browse**
3. Change file type to **Plain Text (*.txt)**
4. Save into this `intake/` folder
5. Return to VS Code and run Step 1

### Option B — Save as Markdown (best quality)
1. Open your `.doc` file in Microsoft Word 365
2. **File → Save As → Browse**
3. Change file type to **Markdown (*.md)**  
   *(requires Word for Microsoft 365 — not available in older versions)*
4. Save into this `intake/` folder

### Option C — Copy & Paste
1. Open your `.doc` file in Word
2. Select all content (**Ctrl + A**)
3. Create a new file in this folder: `intake/my-brd.md`
4. Paste the content and save

### Option D — Use PowerShell (for advanced users)
```powershell
# Install the pandoc converter (one-time setup)
winget install --id JohnMacFarlane.Pandoc

# Convert .docx to Markdown
pandoc "my-brd.docx" -o "intake/my-brd.md"
```

---

## What Makes a Good BRD Input?

Your BRD does not need to be perfectly formatted. Copilot will extract and structure the information.
However, the more detail you provide, the better the generated artefacts.

A good BRD should include:
- **Project / product name**
- **Problem being solved** (why this project exists)
- **Business objectives** (what success looks like)
- **Functional requirements** (what the system must do)
- **Non-functional requirements** (performance, security, scalability)
- **Target users / personas**
- **Platform / technology preferences** (if any)
- **Constraints** (budget, timeline, existing systems)
- **Out of scope items**

---

## Example Files in This Folder

| File | Description |
|------|-------------|
| `sample-brd.md` | A complete sample BRD you can use to test the pipeline |

---

## After Dropping Your BRD

Open **Copilot Chat** in VS Code and run:

```
@workspace I have dropped my BRD in the intake/ folder. 
Please start with Step 1 — parse the BRD using .github/prompts/01-parse-brd.prompt.md
```

Or to run the **full pipeline at once**:

```
@workspace I have dropped my BRD in the intake/ folder.
Please run the full artefact pipeline steps 1 through 7 and save all outputs to output/.
```
