# Demo Script — GitHub Copilot PM Spec-Kit

> **Total runtime:** ~5–7 minutes  
> **Tone:** Conversational, confident, beginner-friendly  
> **Audience:** Developers, PMs, and tech leads new to GitHub Copilot

---

## [INTRO — 30 seconds]

**Say:**

> "Hey everyone — today I'm going to show you something really cool.
> Most teams spend days or even weeks turning a requirements document
> into actual project plans, technical specs, and task lists.
> What if Copilot could do that for you in under 5 minutes?
> That's exactly what this kit does. Let me show you."

---

## [SCENE 1 — Show the Repo — 30 seconds]

*Screen: GitHub repo page at github.com/AkashAi7/ghcp-pm-spec-kit*

**Say:**

> "This is the GitHub Copilot PM Spec-Kit. It's a free, open lab kit.
> Anyone can clone it and start using it immediately.
> All you need is VS Code and a GitHub Copilot licence."

*Action: Point to the README on screen*

> "The README walks you through every step — from installing Git,
> to cloning the repo, to running the pipeline.
> No prior experience needed."

---

## [SCENE 2 — Clone and Open — 30 seconds]

*Screen: Terminal*

**Say:**

> "Let me clone it right now."

*Action: Type in terminal:*
```
git clone https://github.com/AkashAi7/ghcp-pm-spec-kit.git
cd ghcp-pm-spec-kit
code .
```

> "One command to clone, one to open it in VS Code.
> VS Code launches with the full workspace ready."

---

## [SCENE 3 — Show the BRD — 45 seconds]

*Screen: VS Code — open `sample-brds/Standard-BRD-002-Healthcare-Patient-Portal.md`*

**Say:**

> "Now, this is a Business Requirement Document — a BRD.
> This is the Healthcare Patient Portal BRD — one of five sample BRDs included in the kit.
> It describes the project goals, functional requirements, users, and constraints.
> This is what real projects start with."

*Scroll slowly through the BRD*

> "Normally, a BA or PM would spend days turning this into specs,
> a work breakdown, a project plan, wireframes...
> We're going to do all of that in about 90 seconds."

*Action: Copy the BRD file into `intake/`*

```
copy sample-brds\Standard-BRD-002-Healthcare-Patient-Portal.md intake\
```

> "I've dropped it into the intake folder. That's where Copilot reads from."

---

## [SCENE 4 — Switch to PM Spec-Kit Agent — 30 seconds]

*Screen: VS Code — Copilot Chat panel*

**Say:**

> "Now I open Copilot Chat — Ctrl+Alt+I.
> At the top of the chat panel, I click this dropdown — the mode selector —
> and I switch to PM Spec-Kit."

*Action: Click mode selector → choose PM Spec-Kit*

> "This activates a custom AI agent pre-loaded with all the PM rules,
> templates, and output structure. It knows exactly what to generate and where to save it."

---

## [SCENE 5 — Run the Pipeline — 60 seconds]

*Screen: Copilot Chat panel*

**Say:**

> "Now for the magic. I just type one command."

*Action: Type in chat:*
```
/pipeline
```

> "That's it. One command.
> Copilot is now reading the BRD... parsing requirements...
> generating the Functional Specification...
> writing the Technical Design Document...
> building the Work Breakdown Structure..."

*Let the output stream — show each artefact being generated*

> "...generating the Project Management Plan with Gantt and risks...
> creating UI wireframes...
> and breaking everything down into persona-specific TODO lists
> for Frontend, Backend, Data, and DevOps engineers."

*Wait for completion*

> "Done."

---

## [SCENE 6 — Show the Outputs — 60 seconds]

*Screen: VS Code Explorer — open `output/` folder*

**Say:**

> "Everything is saved here in the output folder.
> Let's take a quick look at what was generated."

*Open `output/02-fsd-healthcare-patient-portal.md`*

> "Here's the Functional Specification — full user stories, screen requirements,
> acceptance criteria — all traceable back to the BRD sections."

*Open `output/04-wbs-healthcare-patient-portal.md`*

> "The Work Breakdown Structure — tasks broken down by phase,
> with effort estimates and persona assignments."

*Open `output/06-ui-prototype-healthcare-patient-portal.html` in browser*

> "And this — this is the UI prototype.
> A clickable HTML wireframe generated entirely from the BRD.
> No designer involved. No Figma licence needed."

---

## [SCENE 7 — Show Persona TODOs — 30 seconds]

*Screen: `output/07-persona-todos-healthcare-patient-portal.md`*

**Say:**

> "And finally — the Persona TODOs.
> Every task, assigned to the right engineer, formatted and ready to paste
> straight into GitHub Issues or a sprint board.
> Frontend, Backend, Data Engineer, Data Analyst, and SRE — all covered."

---

## [OUTRO — 30 seconds]

*Screen: README or repo homepage*

**Say:**

> "From a BRD to a complete project plan, specs, wireframes, and task lists —
> in under 5 minutes, with one command.
>
> This kit is free and open source.
> Clone it, try it with your own BRD, and let GitHub Copilot do the heavy lifting.
>
> The repo link is in the description. Give it a star if you find it useful."

*Pause.*

> "Thanks for watching."

---

## Key Lines to Remember

| Moment | Line |
|--------|------|
| Hook | *"What if Copilot could turn your requirements doc into a full project plan in under 5 minutes?"* |
| One command | *"That's it. One command."* |
| After output | *"Done."* — let the silence land |
| Close | *"From BRD to full project plan — in under 5 minutes."* |
