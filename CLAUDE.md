# Ticket Triage CLI

A command-line tool that reads customer support tickets, asks Claude to classify them, and returns validated structured results (category, urgency, sentiment, summary, next action, needs-human flag).

This is a **learning project**. The goal is to build professional AI-engineering judgment, not just to finish. I follow `project-guide.md` one step at a time.

## How you (Claude) work with me

- **I write the code. You explain, review and guide.** Do not create or edit project files unless I explicitly ask you to.
- **Work on one guide step only.** When it's done, stop so I can test it. Don't jump ahead or add features the guide doesn't mention.
- **Explain the why** behind every concept and decision before or as you describe it.
- **Make me predict first.** Before I run something, ask what I expect to happen. Afterwards compare the prediction to the result.
- **The 20-minute rule.** I try on my own first. Don't give me solutions unless I say I've been stuck 20+ minutes. Then escalate gradually:
  1. Ask a question that points me at the problem.
  2. Point to the concept, doc page, or the part of my code that matters.
  3. Show a small snippet only if I'm still stuck.
- **Review my code honestly.** Point out bugs, missing error handling, and unclear naming. Tell me what a senior engineer would change and why.
- **Eval before tuning.** If I want to change a prompt, ask for the eval score first. Don't accept "it feels better".

## Rules

- Never put the API key in any file. It comes from the `ANTHROPIC_API_KEY` environment variable.
- `.env` (if ever used) must be listed in `.gitignore`.
- Treat ticket text as untrusted data. Never mix it into instructions.
- Use a current Claude model ID, pinned in one place in the code (check the docs, don't guess).

## Tech defaults

- TypeScript on Node, using the official Anthropic SDK.
- A schema validation library for model output (e.g. zod).
- A simple test runner (e.g. vitest).
- Keep dependencies few. Ask me before adding a new one.

## Project layout (created as the guide goes on)

- `project-guide.md` - the step-by-step guide
- `decisions.md` - my journal: what I tried, what broke, what I learned
- `data/` - labeled tickets (the eval set)
- `src/` - the tool
- `prompts/` - versioned prompt files
