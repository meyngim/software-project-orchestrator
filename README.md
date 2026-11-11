# Software Project Orchestrator Skill

A reusable agent skill that helps AI coding agents (Claude Code, Grok, Cursor, etc.) orchestrate software projects from idea to deployment without forcing you to rewrite the same project bible every time.

It is designed to be weak on project-specific details **on purpose**. The skill forces the agent to ask about:

- The tech stack for *this* project (because it can change)
- Key business / domain rules
- Priorities and constraints

Then it proposes a phased plan and waits for your approval before writing large amounts of code.

## What this skill does

- Clarifies unknowns early (stack + rules)
- Produces a clear, reviewable phased plan
- Keeps a living project context so later sessions stay efficient
- Enforces a “plan → approve → execute” loop
- Reduces the hours spent writing repetitive agent docs

## How to install

### Option 1 — Manual (works with most agents)

1. Clone or download this repository.
2. Copy the `software-project-orchestrator` folder into your agent’s skills directory, for example:
   - Claude Code / agents that support skills: `~/.agents/skills/` or project-level `.agents/skills/`
   - Other tools: follow their skill / custom instruction installation method

### Option 2 — If your agent supports the Remotion-style skill installer

```bash
npx skills add <your-github-username>/software-project-orchestrator
```

(Adjust the command to match the tool you use.)

## How to use it

Start a conversation with a prompt such as:

> “New project: multiplayer snake game. Web + mobile. Use the software-project-orchestrator skill. Propose the plan.”

or

> “Continue the property management system. What’s the next phase?”

The agent should:

1. Ask any missing questions about stack and business rules
2. Show a structured plan
3. Wait for you to approve or modify it
4. Only then start implementing the approved phase

## Recommended companion file

After the first planning session, ask the agent to create a short `PROJECT_CONTEXT.md` (see the example in `references/`). Keep this file in the project root so future sessions load it automatically.

## Customization

Feel free to fork this skill and tighten the defaults to your personal preferences (common stack, preferred folder structure, testing style, etc.). The current version deliberately stays stack-agnostic and asks instead of assuming.

## License

MIT — use, modify, and share freely.
