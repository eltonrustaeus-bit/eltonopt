# EltonOPT — Intelligent Prompt Architect

A Claude Code slash command that transforms raw ideas into enterprise-grade development prompts.

EltonOPT automatically reads your project context (stack, dependencies, git history, conventions) and builds a fully self-contained prompt tailored to your codebase.

## What it does

1. Silently scans your project — `CLAUDE.md`, `package.json`, git log, recent files
2. Classifies your intent — BUILD / DEBUG / REVIEW / ARCHITECT / OPTIMIZE / REFACTOR
3. Asks one focused clarifying question
4. Outputs a production-grade prompt with role, context, task, approach, and constraints

## Install

```bash
curl -o ~/.claude/commands/EltonOPT.md https://raw.githubusercontent.com/elton-rustaeus/eltonopt/main/commands/EltonOPT.md
```

Then in any Claude Code session:

```
/EltonOPT add Stripe webhook for subscription renewals
```

## Usage

```
/EltonOPT <your raw idea>
```

EltonOPT reads the current working directory — run it from your project root.

## Output format

```
⚡ EltonOPT — Optimized Prompt:

[Complete enterprise-grade prompt]

---
Mode: BUILD
Stack: Next.js 14 + TypeScript + Supabase
Confidence: High
```
