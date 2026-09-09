# Vaayu

> Production-grade skills for AI coding agents. Evaluate, build, scale, compress.

## Skills

| Skill | What it does |
|---|---|
| [**Karm**](./Karm/) | Production-readiness evaluation. Takes any product idea and systematically evaluates what needs to happen before it's production-ready. |
| [**Veg**](./Veg/) | Problem & product evaluation engine. Converts hackathon problem statements, startup ideas, and requirements into clear, feasible, technically sound solutions. |
| [**VegaVelocity**](./VegaVelocity/) | Scalability engineering. Evaluates entire systems for architecture, databases, caching, queues, security, performance, and cost — targeting 20k+ concurrent users. |
| [**Laghu**](./Laghu/) | Token compression. Drops filler, keeps substance. Same technical accuracy, fewer output tokens. |

## Install

### Claude Code

```bash
claude skill add Karm/SKILL.md
claude skill add Veg/SKILL.md
claude skill add VegaVelocity/SKILL.md
claude skill add Laghu/SKILL.md
```

### Manual

Copy any `SKILL.md` into your agent's skill directory:

```bash
cp Karm/SKILL.md ~/.claude/skills/
cp Veg/SKILL.md ~/.claude/skills/
cp VegaVelocity/SKILL.md ~/.claude/skills/
cp Laghu/SKILL.md ~/.claude/skills/
```

### Via npm (if published)

```bash
npx skills add okyashgajjar/vaayu --skill Karm
npx skills add okyashgajjar/vaayu --skill Veg
npx skills add okyashgajjar/vaayu --skill VegaVelocity
npx skills add okyashgajjar/vaayu --skill Laghu
```

## How Skills Work

Each skill is a single `SKILL.md` file with YAML frontmatter. Your AI agent reads the skill and adapts its behavior accordingly.

- **Karm** activates when you provide a product idea or architecture for evaluation
- **Veg** activates when you provide a problem statement, startup idea, or requirements
- **VegaVelocity** activates when you mention scale, performance, or production architecture
- **Laghu** activates when you say "laghu mode", "be brief", or invoke `/laghu`

## License

MIT
