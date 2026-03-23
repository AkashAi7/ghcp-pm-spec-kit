# Lab 1 — Load Your BRD

**Time:** ~5 minutes  
**Goal:** Get your BRD into the `intake/` folder and verify Copilot can read it.

---

## Step 1: Choose Your BRD

**Option A — Use the sample BRD (fastest)**
The file `intake/sample-brd.md` is already in the workspace. Skip to Step 3.

**Option B — Use your own BRD**
Continue to Step 2.

---

## Step 2: Prepare Your BRD File

### If you have a `.md` or `.txt` file
Just copy/move it into the `intake/` folder. Done!

### If you have a `.docx` / `.doc` file

**Method 1 — Save As Text in Word:**
1. Open the `.doc` file in Microsoft Word
2. `File → Save As → Browse`
3. File type: **Plain Text (*.txt)**
4. Save into the `intake/` folder
5. In VS Code: rename the file extension from `.txt` to `.md` if you prefer

**Method 2 — Paste into a new file:**
1. Open your `.doc` in Word → `Ctrl+A` → `Ctrl+C`
2. In VS Code: right-click `intake/` → **New File** → name it `my-brd.md`
3. `Ctrl+V` to paste
4. Save (`Ctrl+S`)

**Method 3 — Pandoc converter (advanced):**
```powershell
# Install pandoc (one-time)
winget install JohnMacFarlane.Pandoc

# Convert
pandoc "C:\path\to\my-brd.docx" -o "intake/my-brd.md"
```

---

## Step 3: Verify in VS Code

1. In the VS Code Explorer panel (left sidebar), expand the `intake/` folder
2. You should see your BRD file listed
3. Click it to open — confirm the content is readable text

---

## Step 4: Test That Copilot Can See It

Open **Copilot Chat** (`Ctrl+Alt+I` or click the Copilot icon in the sidebar)

Paste this prompt:

```
@workspace What BRD files are in the intake/ folder? Give me a one-paragraph summary of the project.
```

**Expected result:** Copilot should name the file and give a brief summary of the project it describes.

If Copilot says it can't find any files, make sure:
- The `@workspace` keyword is included in your prompt
- The file is saved in the `intake/` folder (not somewhere else)
- The file has a `.md` or `.txt` extension

---

## Step 5: Run the Pipeline — Step 1

Now ask Copilot to parse and structure the BRD:

```
@workspace Read the BRD in intake/ and follow the instructions in 
.github/prompts/01-parse-brd.prompt.md to produce a structured BRD summary.
Save the output as output/01-brd-summary-<project-name>.md
```

Copilot will extract all requirements, number them (`BRD-FR-01`, `BRD-FR-02`, ...), and surface any gaps.

---

## What You Should See

After this lab, you should have:
- [ ] A BRD file in `intake/`
- [ ] A structured BRD summary in `output/01-brd-summary-*.md`
- [ ] A list of numbered functional requirements (`BRD-FR-01` through `BRD-FR-nn`)
- [ ] Any identified gaps listed as `GAP-01`, `GAP-02`, etc.

---

**Next:** [Lab 2 — Generate the FSD →](02-generate-fsd.md)
