# Demo Shooting Guide — GitHub Copilot PM Spec-Kit

> Use this guide to plan, set up, and record a clean demo video.
> Target length: **5–7 minutes**

---

## Before You Start — Prep Checklist

Run through this list before you hit record:

- [ ] Repo cloned fresh: `git clone https://github.com/AkashAi7/ghcp-pm-spec-kit.git`
- [ ] `intake/` folder is **empty** (no leftover BRD files)
- [ ] `output/` folder is **empty** (no leftover generated files)
- [ ] VS Code is open with the `ghcp-pm-spec-kit` folder
- [ ] GitHub Copilot is signed in and working
- [ ] PM Spec-Kit agent mode is visible in the chat panel dropdown
- [ ] Browser is open and ready (for the HTML prototype scene)
- [ ] Terminal is open inside VS Code (`` Ctrl+` ``)
- [ ] Font size in VS Code set to **16–18pt** so it reads clearly on screen
- [ ] Screen recording software is running (OBS, Camtasia, Loom, etc.)
- [ ] Microphone tested — no background noise
- [ ] Notifications silenced (Windows: Focus Assist ON)

---

## Screen Setup

### Resolution
- Record at **1920×1080** minimum
- If on a 4K display, scale down or set the recording region to 1080p

### VS Code Layout
- **Explorer panel** visible on the left
- **Terminal** open at the bottom (split view)
- **Copilot Chat** docked to the right sidebar
- Theme: any dark theme works well on video (Default Dark+, One Dark Pro)

### Font Sizes
| Area | Recommended Size |
|------|-----------------|
| VS Code editor | 16–18pt |
| Terminal | 15–16pt |
| Copilot Chat | default |

---

## Scene-by-Scene Shooting Plan

### Scene 1 — Intro (browser)
**Show:** GitHub repo page  
**Duration:** 30 seconds  
**Tips:**
- Zoom browser to 110% so the README is readable
- Scroll slowly — don't rush
- Pause on the "What gets generated" table for 3 seconds

---

### Scene 2 — Clone & Open (terminal)
**Show:** Terminal (PowerShell or Command Prompt)  
**Duration:** 30 seconds  
**Commands to type live:**
```
git clone https://github.com/AkashAi7/ghcp-pm-spec-kit.git
cd ghcp-pm-spec-kit
code .
```
**Tips:**
- Type at a natural pace — not too fast
- Let VS Code fully load before continuing
- If `code .` doesn't work, open manually and cut that part in editing

---

### Scene 3 — Show the BRD (VS Code editor)
**Show:** `sample-brds/Standard-BRD-002-Healthcare-Patient-Portal.md`  
**Duration:** 45 seconds  
**Tips:**
- Open the file from the Explorer panel (click, don't type path)
- Scroll slowly through the first 3 sections — Goals, Users, Functional Requirements
- Stop scrolling when you say *"We're going to do all of that in 90 seconds"*
- Then switch to terminal and copy the file:

```
copy sample-brds\Standard-BRD-002-Healthcare-Patient-Portal.md intake\
```
*(On Mac/Linux: `cp sample-brds/Standard-BRD-002-Healthcare-Patient-Portal.md intake/`)*

---

### Scene 4 — Switch Agent Mode (Copilot Chat)
**Show:** Copilot Chat panel — mode selector dropdown  
**Duration:** 20–30 seconds  
**Tips:**
- Click the mode selector dropdown **slowly and deliberately**
- Hover over "PM Spec-Kit" for 1 second before clicking
- If the dropdown isn't visible, press `Ctrl+Alt+I` first to open chat

---

### Scene 5 — Run `/pipeline` (Copilot Chat — MAIN MOMENT)
**Show:** Copilot Chat — full panel visible  
**Duration:** 60–90 seconds  
**Tips:**
- Type `/pipeline` slowly and clearly
- Press Enter and **step back** — let Copilot stream output
- Keep talking over the output (use script Scene 5 lines)
- Do NOT cut this scene — the live streaming is the "wow" moment
- If Copilot pauses between artefacts, fill with commentary from the script
- Keep the Explorer panel visible so viewers see `output/` files appearing in real time

> **Recording tip:** If the pipeline takes longer than expected, narrate what's happening.
> Say *"You can see it's now writing the WBS..."* etc.

---

### Scene 6 — Review Outputs (VS Code Explorer + editor)
**Show:** `output/` folder in Explorer, then open 3 files  
**Duration:** 60 seconds  
**Open these files in this order:**
1. `output/02-fsd-healthcare-patient-portal.md` — scroll through user stories section
2. `output/04-wbs-healthcare-patient-portal.md` — scroll through task table
3. Open `output/06-ui-prototype-healthcare-patient-portal.html` in browser

**Tips:**
- For the HTML prototype: right-click the file → "Open with" → your browser
- Zoom the browser to 100%
- Click through 2–3 screens of the prototype to show it's interactive
- Keep each file on screen for at least 5 seconds before moving on

---

### Scene 7 — Persona TODOs (VS Code editor)
**Show:** `output/07-persona-todos-healthcare-patient-portal.md`  
**Duration:** 30 seconds  
**Tips:**
- Scroll to the **Frontend Engineer** section first, then **Backend Engineer**
- Point out that tasks are formatted as GitHub Issues checkboxes

---

### Scene 8 — Outro (repo page or VS Code)
**Show:** GitHub repo README or VS Code with output folder visible  
**Duration:** 30 seconds  
**Tips:**
- End on the repo URL visible on screen
- Smile — warm close
- Leave 2 seconds of silent pause before stopping the recording

---

## Editing Notes (Post-Production)

| Cut point | What to do |
|-----------|------------|
| Git clone output | Speed up 2× — nobody needs to watch git counting objects |
| VS Code loading | Cut to when it's fully loaded |
| Copilot streaming | Keep at real speed — this is the key moment |
| File scrolling | Slow down, don't rush — viewers need time to read |
| Any typos in chat | Cut and re-record the scene — don't leave typos in the final cut |

### Recommended Overlays
- **Lower third text** when switching scenes: e.g. *"Step 3 — Running the pipeline"*
- **Zoom/highlight** the `/pipeline` command when typed
- **Callout box** on the output folder when files start appearing

### Music
- Keep background music **off** or very subtle (instrumental, low volume)
- The live Copilot output has its own satisfying rhythm — let it breathe

---

## Quick Re-shoot Checklist (if something goes wrong)

| Problem | Fix |
|---------|-----|
| PM Spec-Kit not in agent list | Close and reopen VS Code with the folder |
| `/pipeline` produces no output | Check intake/ has the BRD file; try `/brd` first |
| output/ files already exist | Delete them and re-run |
| Wrong BRD loaded | Check intake/ has only one file |
| HTML prototype blank | Open manually in browser, not VS Code preview |

---

## Final File Checklist Before Upload

- [ ] Intro title card added
- [ ] Repo URL visible in outro
- [ ] Audio levels consistent throughout
- [ ] No personal info visible (email, other repo names, notifications)
- [ ] Video trimmed cleanly at start and end
