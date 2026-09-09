# Karm

> **"Build it right before you ship it."**

Production-readiness evaluation skill for AI coding agents. Takes any product idea, requirement, or technical proposal and systematically evaluates what needs to happen before considering it production-ready.

## What Karm Does

When given an idea, requirement, feature, architecture, or problem statement, Karm evaluates:

1. Problem & requirements
2. Feature breakdown & task decomposition
3. Architecture & technology choices
4. Testing strategy (unit, integration, E2E, edge cases)
5. Performance & scalability
6. Security & reliability
7. Observability & operations
8. Cost analysis
9. AI/ML evaluation (when applicable)
10. Production readiness gate

**Deployment is optional.** Karm does not force production deployment for prototypes, hackathons, or PoCs.

## Install

### Claude Code

```bash
claude skill add Karm/SKILL.md
```

### Manual

Copy `Karm/SKILL.md` into your agent's skill directory:

```bash
cp Karm/SKILL.md ~/.claude/skills/
```

## Usage

Provide any idea, requirement, or architecture and Karm automatically activates:

```
Evaluate this architecture for production readiness:
[describe your system]
```

Karm produces a structured evaluation with PASS / PARTIAL / NOT READY verdicts across all categories, plus a priority-ranked action list.

## Output

Karm returns a structured report:

- Executive summary
- Problem & requirements
- Feature breakdown
- Architecture review
- Technology decisions
- Testing strategy
- Performance, scalability, security, reliability
- Cost analysis
- Production readiness scorecard (PASS/PARTIAL/FAIL per category)
- Priority-ranked risks and missing work

## Works For

- Software products, SaaS, web & mobile apps
- Backend systems, APIs, distributed systems
- AI/ML products, data products
- Internal tools, automation systems
- Developer tools, client projects
- Hackathon projects that may become real products

## License

MIT
