# VegaVelocity

> **"I don't slow down your application EVER!"**

Production-readiness and scalability engineering skill for AI coding agents. Evaluates entire products — not just AI/ML — for architecture, databases, caching, queues, infrastructure, security, performance, reliability, observability, and cost.

## What VegaVelocity Does

Takes any product idea, hackathon problem statement, client requirement, or existing architecture and produces a complete production-readiness evaluation targeting 20,000+ concurrent users.

### Core Evaluation Areas

- **Workload modeling** — concurrent users, RPS, peak traffic, expensive operations
- **Architecture** — stateless backends, async processing, scaling boundaries
- **Database** — schema, indexes, connection pooling, replication, sharding
- **Caching** — Redis, TTL, invalidation, stampede protection
- **AI/ML** — inference capacity, GPU scheduling, batch processing, robustness
- **Security** — auth, authorization, injection, uploads, secrets
- **Performance** — SLOs, load/stress/spike testing, bottleneck analysis
- **Reliability** — retries, backpressure, circuit breakers, disaster recovery
- **Observability** — logs, metrics, traces, alerting
- **Cost** — infrastructure, compute, GPU, storage, AI inference per request

## Install

### Claude Code

```bash
claude skill add vega-velocity/SKILL.md
```

### Manual

Copy `vega-velocity/SKILL.md` into your agent's skill directory:

```bash
cp vega-velocity/SKILL.md ~/.claude/skills/
```

## Usage

```
Architecture review for a document processing system serving 20k concurrent users:
[describe your system]
```

Or:

```
Tech stack comparison for high-throughput AI inference:
[context]
```

### Operating Modes

- **Hackathon Mode** — fast implementation, strong demo, minimal infra
- **Client Mode** — extract requirements, map to architecture, define acceptance criteria
- **Idea Mode** — reasonable assumptions, initial architecture, identify what could change everything

## Output

VegaVelocity produces:

1. Executive verdict (feasibility, risks, bottleneck, architecture direction)
2. Workload model with explicit estimates
3. Recommended architecture with request/async/data flows
4. Technology selection with trade-offs
5. Bottleneck analysis (P0/P1/P2 ranked)
6. Security, reliability, performance plan
7. Cost estimation
8. Implementation roadmap (MVP → production hardening → scale validation)
9. Production readiness scorecard

## Design Principles

1. Measure before optimizing
2. Scale expensive work independently
3. Keep request path short
4. Protect shared resources
5. Design for failure
6. Prefer simplicity until complexity is justified
7. 20k is a test target, not a marketing number
8. Cost is part of performance

## License

MIT
