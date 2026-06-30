<p align="center">
  <img src="https://raw.githubusercontent.com/eltonrustaeus-bit/eltonopt/main/assets/eltonopt-logo.png" alt="EltonOPT v3.2 — Precision Prompt Architect" width="420">
</p>

# EltonOPT v3.2 — Precision Prompt Architect

A Claude Code slash command that transforms raw ideas into enterprise-grade development prompts.

EltonOPT automatically reads your project context (stack, dependencies, git history, conventions) and builds a fully self-contained prompt tailored to your codebase — with security risk scoring, compliance flags, blast-radius analysis, and test strategy included.

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

### Mode flags

```
/EltonOPT --compact <idea>       # minimal output for small tasks
/EltonOPT --no-questions <idea>  # one-shot, makes labeled assumptions
/EltonOPT --dry <idea>           # debug: print detected intent + INTEL only
```

## What it does

1. **Task-type gate** — routes SOFTWARE / META / NON_CODE tasks to the right-sized pipeline (no stack scan on a marketing prompt)
2. **Silently scans your project** — `CLAUDE.md`, `package.json`, git log, recent files, code conventions (with a non-git filesystem fallback)
3. **Classifies compound intent** — BUILD / DEBUG / REVIEW / ARCHITECT / OPTIMIZE / REFACTOR / MIGRATE / HARDEN, with precedence + negation handling
4. **Scans security surface** — auto-flags GDPR, PCI, the full OWASP Top 10, breaking-change and migration risk
5. **Computes blast radius** — counts importers of target files to score regression risk
6. **Asks up to two focused clarifying questions** (structured options when applicable)
7. **Outputs an enterprise-grade prompt** with role, context, pre-flight reads, task scope, observable success criteria, adversarial test cases, test strategy, rollback plan, and agent orchestration

## Output format

```
⚡ EltonOPT v3.2 — Precision Prompt:

[Complete enterprise-grade prompt — fully self-contained]

---
INTENT:        BUILD + HARDEN
TASK TYPE:     SOFTWARE
STACK:         Next.js + TypeScript + Supabase + Stripe
SECURITY RISK: HIGH — touches payment flow and user PII
BLAST RADIUS:  MEDIUM — 6 files
COMPLEXITY:    M — 2-4 hours, 3 files, no new dependencies
MODEL:         Sonnet 5 — agentic feature work at low cost
CONFIDENCE:    High
```

## What's new in v3.2

- **Current model roster** — recommends Haiku 4.5 / **Sonnet 5** (default) / Opus 4.8 / Fable 5; blocks retired model names
- **Task-type gate** — SOFTWARE / META / NON_CODE with a LITE pipeline for non-code work
- **Mode flags** — `--compact`, `--full`, `--no-questions`, `--dry`
- **Bug fixes** — blast-radius phase ordering, duplicate `OWASP_AUTHN` flag merged, four missing security-flag constraints added, Phase 6 infinite-loop capped at 2 passes, non-destructive `git revert` rollback default
- **Non-git fallback** — architectural scan uses filesystem mtime when there's no git history
- **Dependency-read cap** — avoids token bloat on large `package.json` files
- **Up to two clarifying questions** — uses structured options when the choice is discrete

### Carried over from earlier versions

- Security Risk Score (CRITICAL / HIGH / MEDIUM / LOW) on every output
- Mandatory Test Strategy naming specific functions and endpoints
- Rollback Plan for BUILD and MIGRATE intents
- Complexity estimate (S / M / L / XL)
- Reads `.claude/team-standards.md` if present
- Prompt-injection quarantine of all user input

## Supported stacks

Node/TS, Next.js, Vite, Astro, SvelteKit, Nuxt, Python, FastAPI, Rust, Go, PHP, Ruby, Java, Kotlin, Flutter, C#/.NET and more.

## Update

Re-run the install command to get the latest version.
