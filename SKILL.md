---
name: software-project-orchestrator
description: "Orchestrate software projects from concept to deployment. Use when starting a new web app, mobile app, game, SaaS, or system; when the user wants a phased plan, architecture proposal, or build order; when continuing a project and needing to know what to do next. Always ask about tech stack and business rules if not already clear. Triggers on requests to plan a project, bootstrap a codebase, propose next steps, or manage development phases for software engineering work."
type: workflow
lifecycle: active
---

# Software Project Orchestrator

Guide the full lifecycle of a software project while minimizing repeated explanations.  
Propose clear, reviewable plans. Wait for user approval before large implementation steps.  
Never assume tech stack or business rules — ask when unclear.

## Core principles

- **Ask first on unknowns**: Tech stack and domain/business rules change per project. Confirm them early.
- **Plan → Review → Execute**: Always show a phased plan and get explicit approval before writing substantial code.
- **Keep context alive**: Maintain a short living summary of the project so later sessions do not require full re-explanation.
- **User is the reviewer**: You propose; the user corrects, rejects, or approves.
- **Prefer incremental delivery**: Small, verifiable milestones over big-bang implementation.

## Mandatory clarification step

Before proposing any architecture or build plan, ensure you have answers to these. If any are missing or vague, ask concisely:

1. **Project type and goal** — What is being built and for whom? (e.g. snake game, multi-tenant SaaS, internal tool)
2. **Tech stack for this project** — Preferred or required technologies (frontend, backend, mobile, database, hosting). Note that the user’s usual stack may not apply here.
3. **Key business / domain rules** — Critical logic, constraints, edge cases, or non-negotiable requirements that must be encoded correctly.
4. **Non-functional priorities** — Performance, security, accessibility, localization, offline support, etc. that matter most.
5. **Delivery constraints** — Timeline, team size (solo vs team), or must-have integrations.

If the user already provided clear answers in the conversation or in project files, do not re-ask.

## Workflow

1. **Gather context**  
   Run the clarification step above. Summarize what you understood in 4–6 bullets and confirm with the user.

2. **Propose phased plan**  
   Output a clear plan using the structure in `references/plan-template.md`.  
   Phases typically include: Foundation → Core features → Polish & quality → Deploy & handoff.  
   Adjust phases to the project size.

3. **Wait for approval**  
   Explicitly ask the user to approve, modify, or reject the plan. Do not start coding until approved.

4. **Execute the approved phase**  
   Implement only the current approved phase. Prefer small, testable commits or changes.  
   After completing a phase, summarize what was done and propose the next phase.

5. **Maintain living context**  
   After each major decision or phase, update (or suggest updating) a short `PROJECT_CONTEXT.md` or equivalent that captures:
   - Goal and audience
   - Chosen tech stack
   - Key business rules
   - Current phase and next action
   - Important architectural decisions

## Build-order guidelines

| Phase | Focus | Typical outputs |
|-------|-------|-----------------|
| 0 – Context | Clarification | Confirmed stack, rules, priorities |
| 1 – Foundation | Scaffolding, architecture skeleton, CI basics, design tokens | Repo structure, core types/models, initial UI shell |
| 2 – Core features | Primary user flows and domain logic | Working happy paths |
| 3 – Quality & polish | Edge cases, performance, UX refinements, tests | Robust, pleasant experience |
| 4 – Deploy & handoff | Production config, docs, monitoring | Live system + clear next steps |

## When the user continues an existing project

- Read existing context files (`PROJECT_CONTEXT.md`, README, architecture notes) first.
- Propose only the next logical step.
- Re-confirm any rule or stack choice that appears to have changed.

## References

- Detailed plan template → `references/plan-template.md`
- Example living context file → `references/project-context-example.md`
