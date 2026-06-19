# EltonOPT v2 — Intelligent Prompt Architect

A Claude Code slash command that transforms raw ideas into enterprise-grade development prompts.

EltonOPT automatically reads your project context (stack, dependencies, git history, conventions) and builds a fully self-contained prompt tailored to your codebase — with security risk scoring, compliance flags, and test strategy included.

## Install

**Mac / Linux:**
```bash
curl -o ~/.claude/commands/EltonOPT.md https://raw.githubusercontent.com/eltonrustaeus-bit/eltonopt/main/commands/EltonOPT.md
```

**Windows (PowerShell):**
```powershell
curl -o "$env:USERPROFILE\.claude\commands\EltonOPT.md" https://raw.githubusercontent.com/eltonrustaeus-bit/eltonopt/main/commands/EltonOPT.md
```

Then restart Claude Code and run from your project root:

```
/EltonOPT <your raw idea>
```

## What it does

1. **Silently scans your project** — `CLAUDE.md`, `package.json`, git log, recent files, code conventions
2. **Classifies intent** — BUILD / DEBUG / REVIEW / ARCHITECT / OPTIMIZE / REFACTOR / MIGRATE
3. **Scans security surface** — flags GDPR, PCI-DSS, SOC2, breaking changes, migration risk automatically
4. **Asks one focused clarifying question**
5. **Outputs an enterprise-grade prompt** with role, context, task, approach, constraints, test strategy, and rollback plan

## Output format

```
⚡ EltonOPT v2 — Optimized Prompt:

[Complete enterprise-grade prompt — fully self-contained]

---
Mode: BUILD
Stack: Next.js 14 + TypeScript + Supabase + Stripe
Security Risk: HIGH — touches payment flow and user PII
Complexity: M — 2-4 hours, 3 files, no new dependencies
Confidence: High
```

## What's new in v2

- **Security Risk Score** — CRITICAL / HIGH / MEDIUM / LOW on every output
- **Compliance flags** — auto-detects GDPR, PCI-DSS, SOC2/OWASP triggers
- **Test Strategy** — mandatory, names specific functions and endpoints to test
- **Rollback Plan** — always included for BUILD and MIGRATE intents
- **MIGRATE mode** — database migrations, library upgrades, API versioning
- **Complexity estimate** — S / M / L / XL so you know scope before starting
- **Team standards** — reads `.claude/team-standards.md` if present
- **Generic** — works for any developer, any project, any stack

## Supported stacks

Node/TS, Next.js, Vite, Astro, SvelteKit, Nuxt, Python, FastAPI, Rust, Go, PHP, Ruby, Java, Kotlin, Flutter, C#/.NET and more.

## Update

Re-run the install command to get the latest version.
