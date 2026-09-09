# Veg

> **"Turn an idea into a validated, buildable product plan."**

Problem & product evaluation engine for AI coding agents. Converts hackathon problem statements, startup ideas, and requirements into clear, feasible, differentiated, technically sound solutions.

> [!TIP]
> **Pure analysis — zero code execution.** Veg runs anywhere a skill runs:
> claude.ai, Claude Code, Codex, Gemini CLI, Cursor, Windsurf, Cline,
> Antigravity, Copilot, and every Agent Skills-compatible agent. No sandbox,
> no runtime, no permissions needed.

## What Veg Does

Veg evaluates ideas through three operating modes:

### Hackathon Mode

- Problem clarity & user value
- Innovation & competition analysis
- Technical feasibility & demo potential
- Time-constrained architecture decisions
- Open-source/free tech recommendations

### Startup Mode

- Problem validation
- Market & competition analysis
- Business model & unit economics
- MVP definition
- Scalability & differentiation

### Requirement Analysis Mode

- Functional & non-functional requirements
- User roles & workflows
- Edge cases & acceptance criteria
- Dependencies & constraints
- Missing information identification

## Install

### Claude Code

```bash
claude skill add veg/SKILL.md
```

### Manual

Copy `veg/SKILL.md` into your agent's skill directory:

```bash
cp veg/SKILL.md ~/.claude/skills/
```

## Usage

```
Quickly evaluate this hackathon problem statement:
[your problem statement]
```

Or:

```
Deep dive into this startup idea:
[your idea]
```

Veg automatically detects the context (hackathon, startup, or requirement analysis) and adapts accordingly.

## Output

Veg produces a structured evaluation:

1. Executive summary
2. Problem extraction
3. User identification & journey
4. Why it matters
5. Existing solutions & gap analysis
6. Proposed solution & features
7. Architecture & technology stack
8. Bottlenecks & scalability
9. Security, reliability, cost
10. Feasibility scores
11. Final verdict: BUILD / BUILD WITH CHANGES / VALIDATE FIRST / DON'T BUILD

## Key Principles

- Technology must serve requirements, not the other way around
- Never recommend AI, blockchain, or microservices just because they're popular
- Prefer simplest technology that satisfies requirements
- Challenge ideas, don't blindly agree
- Separate facts from assumptions

## License

MIT
