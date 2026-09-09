# Laghu

> **"Say less. Mean more."**

Token-compression skill for AI coding agents. Drops filler, keeps substance. Same technical accuracy, significantly fewer output tokens.

*Laghu (लघु) — Sanskrit for light, brief, concise.*

## What Laghu Does

Makes your AI agent respond in compressed prose. Code, commands, errors, and technical terms stay byte-exact. Everything else gets tightened.

### What Gets Compressed

- Filler words (`just`, `really`, `basically`, `actually`)
- Pleasantries (`sure`, `certainly`, `happy to help`)
- Hedging (`might`, `perhaps`, `could be`)
- Articles (`a`, `an`, `the`) at full/ultra levels
- Redundant phrases (`it is important to note that`)

### What Never Gets Compressed

- Code blocks and inline code
- CLI commands
- Error messages (exact text)
- File paths and URLs
- Function/variable/class names
- API endpoints and config keys
- Technical terms (Redis, PostgreSQL, Docker, etc.)
- Security warnings
- Irreversible action confirmations

## Install

### Claude Code

```bash
claude skill add laghu/SKILL.md
```

### Manual

Copy `laghu/SKILL.md` into your agent's skill directory:

```bash
cp laghu/SKILL.md ~/.claude/skills/
```

## Usage

Activate by saying:

- "laghu mode"
- "be brief"
- "compress your responses"
- "less tokens"
- `/laghu`

Deactivate with:

- `/laghu off`
- "normal mode"

## Intensity Levels

| Level | Behavior |
|---|---|
| `/laghu lite` | Drop filler and hedging. Keep articles and full sentences. Professional but tight. |
| `/laghu full` (default) | Drop articles, use fragments, short synonyms. Classic Laghu. |
| `/laghu ultra` | Strip conjunctions. One word when one word suffices. State each fact once. |

## Example

### Before (normal)

```
I'll help you set up a PostgreSQL connection pool. It's important to note
that you should use a connection pooler like PgBouncer or the built-in
pooling in your application framework. The reason for this is that
creating a new database connection for every request is expensive.
```

### After (Laghu full)

```
Use connection pool for PostgreSQL. PgBouncer or framework built-in pool.
New connection per request = expensive.
```

## Key Principles

- Fragments are fine
- Short synonyms preferred (`fix` > `implement a solution for`)
- One fact per sentence
- No tool-call narration
- Preserve user's language (Hindi Laghu, Spanish Laghu, etc.)
- Never announce the mode in output

## License

MIT
