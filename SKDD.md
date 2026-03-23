# Spec-Kit Driven Development (SKDD)
### A Methodology for AI-Accelerated Project Delivery

---

## What is SKDD?

**Spec-Kit Driven Development** is a software delivery methodology where:

1. A **Business Requirement Document (BRD)** is the single source of truth
2. An AI agent generates the **full artefact chain** from that BRD automatically
3. Engineers work from **structured, traceable, AI-generated specs** — not ad-hoc documents
4. Every downstream artefact is **derived from and linked back** to the BRD

The core insight: *the bottleneck in most projects isn't the code — it's the gap between what the business wants and what engineers build.* SKDD eliminates that gap by generating every translation layer (FSD → TDD → WBS → tasks) in minutes rather than weeks.

---

## The SKDD Artefact Chain

```
                    ┌─────────────────────────────────────────────────────┐
                    │           BUSINESS REQUIREMENT DOCUMENT              │
                    │                 (Single source of truth)             │
                    └──────────────────────┬──────────────────────────────┘
                                           │
                         ┌─────────────────▼─────────────────┐
                         │        BRD SUMMARY + GAP ANALYSIS  │
                         │  Structured requirements, NFRs,    │
                         │  stakeholders, identified gaps      │
                         └─────────────────┬─────────────────┘
                                           │
                    ┌──────────────────────▼──────────────────────────────┐
                    │            FUNCTIONAL SPECIFICATION (FSD)            │
                    │   Screen-level requirements, user stories,           │
                    │   acceptance criteria, state machines, data dict     │
                    └──────────────────────┬──────────────────────────────┘
                                           │
                    ┌──────────────────────▼──────────────────────────────┐
                    │           TECHNICAL DESIGN DOCUMENT (TDD)            │
                    │   Architecture, API catalogue, DB schema,            │
                    │   Azure resource map, security model, CI/CD          │
                    └──────────┬───────────────────────────┬──────────────┘
                               │                           │
               ┌───────────────▼──────┐       ┌───────────▼──────────────┐
               │  WORK BREAKDOWN      │       │  UI WIREFRAMES +         │
               │  STRUCTURE (WBS)     │       │  HTML PROTOTYPE          │
               │  Tasks × personas    │       │  Clickable flows,        │
               │  × effort × sprints  │       │  ASCII wireframes        │
               └───────────┬──────────┘       └──────────────────────────┘
                           │
               ┌───────────▼──────────┐
               │  PROJECT MGMT PLAN   │
               │  Gantt, risks, RACI, │
               │  comms, budget       │
               └───────────┬──────────┘
                           │
               ┌───────────▼──────────┐
               │  PERSONA TODOS       │
               │  GitHub Issues-ready │
               │  tasks per engineer  │
               └───────────┬──────────┘
                           │
               ┌───────────▼──────────────────────────────────────────────┐
               │  ONGOING PM LIFECYCLE                                     │
               │  Sprint plans · Risk register · Status reports            │
               │  Daily standups · Retrospectives · Change requests        │
               │  Release notes · Project handover                         │
               └──────────────────────────────────────────────────────────┘
```

---

## SKDD Principles

### 1. One Source, Many Views
The BRD is written once. Every other document is a *view* of that BRD tailored for a specific audience:
- **FSD** = BRD for product and UX
- **TDD** = BRD for engineers  
- **WBS** = BRD for project managers
- **Persona TODOs** = BRD for individual engineers

### 2. Traceability by Default
Every requirement in the FSD references a BRD section (`BRD-FR-02`).  
Every WBS task references an FSD or TDD section (`FSD-M03`).  
Every persona TODO references a WBS ID (`WBS-2.3.1`).  
This chain means: *when requirements change, you know exactly what else changes.*

### 3. Generate, Review, Refine — Not Write From Scratch
Engineers and PMs don't write specs from scratch. They:
1. **Generate** — AI produces the first draft from the BRD
2. **Review** — Team reviews for accuracy (domain knowledge check)
3. **Refine** — Minor edits to align with team conventions or constraints

This cuts spec authoring time from days/weeks to hours.

### 4. Living Artefacts
SKDD artefacts are not one-time outputs. They evolve:
- `/change <description>` → formal change request propagates through the chain
- `/status` → weekly RAG report against the original plan
- `/retro` → sprint review feeds back into future artefacts
- `/handover` → project closure document built from the full artefact set

### 5. Persona-Aligned Work Items
Rather than assigning tasks to named individuals, SKDD assigns to **engineering personas**:
- **Frontend Engineer** — UI, accessibility, client-side logic
- **Backend Engineer** — APIs, business logic, auth
- **Data Engineer** — pipelines, integrations, storage
- **Data Analyst** — reporting, BI, analytics
- **SRE / Cloud Engineer** — infrastructure, CI/CD, security, monitoring

This makes the kit universally applicable regardless of team size or structure.

---

## SKDD vs Traditional Approaches

| Dimension | Traditional PM | SKDD |
|-----------|---------------|------|
| Spec authoring | Manual, weeks | AI-generated in minutes |
| Traceability | Often missing | Built-in, structural |
| Artefact consistency | Varies by author | Uniform templates |
| Change impact | Manual trace | `/change` propagates automatically |
| Task granularity | Often vague | Sprint-assigned with ACs |
| UI prototyping | Figma/separate tooling | Embedded in the same pipeline |
| Time BRD → working task list | 2–4 weeks | Under 1 hour |

---

## Is This Project Using SKDD?

**Yes.** This repository *is* the SKDD reference implementation.

The `intake/sample-brd.md` demonstrates the input.  
The `output/` folder demonstrates all artefacts the methodology produces.  
The `.github/prompts/` folder contains the AI agent rules that enforce SKDD discipline.  
The `.github/chatmodes/pm-spec-kit.chatmode.md` is the dedicated AI agent for running SKDD.  
The `templates/` folder enforces structural consistency across all artefacts.

Every time a participant drops a BRD into `intake/` and types `/pipeline`, they are practicing SKDD.

---

## When to Use SKDD

SKDD works best for:
- ✅ New software projects where requirements exist but specs don't yet
- ✅ Projects where engineering and business are misaligned on scope
- ✅ Teams that skip documentation and pay for it during delivery
- ✅ Workshop/training contexts to demonstrate AI-accelerated delivery
- ✅ Consultancies that need consistent artefact delivery across clients

SKDD is less suitable for:
- ❌ Pure research/prototyping (no requirements to base specs on)
- ❌ Existing projects with complete documentation already in place
- ❌ Projects where the BRD itself is the deliverable (not the downstream artefacts)

---

## Getting Started with SKDD

1. Write or collect a BRD (even a rough one works)
2. Drop it in `intake/`
3. Open GitHub Copilot Chat → switch to **PM Spec-Kit** mode
4. Type `/pipeline`
5. Review outputs in `output/`
6. Iterate: edit the BRD → re-run any step → outputs update

*Your BRD is the seed. SKDD grows it into a complete project delivery package.*
