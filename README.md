# Vaayu

> Production-grade skills for AI coding agents. Evaluate, build, scale, compress.

Four open-standard `SKILL.md` skills that work in [Agent Skills](https://agentskills.io)-compatible tools: Claude Code, Codex, Gemini CLI, Cursor, Windsurf, Cline, Roo Code, Goose, OpenCode, GitHub Copilot, and more.

## Skills

| Skill | What it does | Works without writing code |
|---|---|---|
| [**karm**](./karm/) | Production-readiness evaluation. Turns any product idea, requirement, or architecture into a build-ready plan covering features, testing, security, performance, scalability, and cost. | No |
| [**veg**](./veg/) | Problem & product evaluation. Converts hackathon problem statements, startup ideas, and requirements into clear, feasible, buildable solutions. | **Yes** |
| [**vega-velocity**](./vega-velocity/) | Scalability engineering. Evaluates entire systems for architecture, databases, caching, queues, security, performance, and cost — targeting 20k+ concurrent users. | **Yes** |
| [**laghu**](./laghu/) | Token compression. Drops filler, keeps substance. Same technical accuracy, fewer output tokens. | No |

`veg` and `vega-velocity` are pure analysis skills — no code needed, safe for claude.ai.

## Install

### npm (any agent)

```bash
# install one or all skills
npx skills add okyashgajjar/vaayu --skill karm
npx skills add okyashgajjar/vaayu --skill veg
npx skills add okyashgajjar/vaayu --skill vega-velocity
npx skills add okyashgajjar/vaayu --skill laghu
```

Mutual targeting supported, e.g. `-a codex`, `-a gemini`, `-a cursor`.

### Claude Code

```bash
claude skill add karm/SKILL.md
claude skill add veg/SKILL.md
claude skill add vega-velocity/SKILL.md
claude skill add laghu/SKILL.md
```

Or copy to `~/.claude/skills/`:

```bash
cp karm/SKILL.md ~/.claude/skills/
cp veg/SKILL.md ~/.claude/skills/
cp vega-velocity/SKILL.md ~/.claude/skills/
cp laghu/SKILL.md ~/.claude/skills/
```

### claude.ai (web)

Upload the ready-made zips from `claudeai/` at **Customize &gt; Skills &gt; + Create skill &gt; Upload a skill**. Requires a Max/Pro/Team/Enterprise plan with code execution enabled.

| Skill | Zip |
|---|---|
| veg | `claudeai/veg.zip` |
| vega-velocity | `claudeai/vega-velocity.zip` |

### Direct (any agent, manual)

Each skill is a folder with a matching `SKILL.md`. Copy the folder into your agent's skill directory (`.claude/skills/`, `.agents/skills/`, `.cursor/skills/`, `.gemini/skills/`, etc.) — or use `sync-skill`:

```bash
npx sync-skill claude codex       # Claude → Codex
npx sync-skill claude cursor      # Claude → Cursor
```

## Agent compatibility

All skills use only the portable core of the Agent Skills spec: `name` + `description` frontmatter, lowercase hyphenated folder names, progressive disclosure. No Claude Code extensions (hooks, subagents, dynamic context).

| Agent | Skill directory | Notes |
|---|---|---|
| Claude Code | `.claude/skills/`, `~/.claude/skills/` | Native. `claude skill add`. |
| OpenAI Codex | `.agents/skills/`, `~/.agents/skills/` | Native. Also `~/.codex/skills/`. |
| Gemini CLI | `.gemini/skills/`, `.agents/skills/` | Native since v0.25. |
| Cursor | `.cursor/skills/` (also reads `.claude/skills/`) | Native — lowercase folder names required, satisfied. |
| Windsurf | `.windsurf/skills/`, `.agents/skills/` | Native. |
| Cline, Roo Code, Kilo Code, Goose | `.agents/skills/`, `.clinerules/skills/`, etc. | Native. |
| OpenCode | `.opencode/skills/`, `.claude/skills/`, `.agents/skills/` | Native. |
| GitHub Copilot | ~/.copilot/skills/, `.github/skills/` | Native (also reads `~/.claude/skills/`). |
| claude.ai | — | Zip upload from `claudeai/`. No code-involved skills (`veg`, `vega-velocity`). |
| Antigravity, Trae | adapter | Uses `.agent/skills/` (singular) or rule conversion. |

## How the skills trigger

Each skill has a compact, exact `description` (≤200 chars, claude.ai limit). Agents match it against task intent:

- **karm** — product idea / architecture needs a production-readiness plan
- **veg** — hackathon or startup problem statement needs evaluation
- **vega-velocity** — mention of scale, performance, or production architecture
- **laghu** — "laghu mode", "be brief", "compress", "less tokens", `/laghu`

## Development

```bash
npm run validate   # confirms all SKILL.md files present
```

Stuck to portable core on purpose: every skill is one `SKILL.md` — works everywhere, minimal context cost.

## License

MIT