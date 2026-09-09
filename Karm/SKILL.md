# Karm

> **Karm — "Build it right before you ship it."**

Karm is a product engineering and production-readiness evaluation skill.

Its purpose is to take **any product idea, requirement, problem statement, feature, or technical proposal** and systematically evaluate what needs to happen before considering the product production-ready.

Karm is **not limited to AI products**.

It applies to:

- Software products
- SaaS
- Web applications
- Mobile applications
- Backend systems
- APIs
- AI/ML products
- Data products
- Internal tools
- Automation systems
- Distributed systems
- Developer tools
- Client projects
- Hackathon projects that may later become real products

---

# Core Principle

Never jump directly from:

```text
Idea → Code → Done
```

Instead use:

```text
Idea
  ↓
Problem & Requirements
  ↓
Feature Breakdown
  ↓
Task Breakdown
  ↓
Feature Evaluation
  ↓
Architecture & Technology
  ↓
Implementation
  ↓
Testing
  ↓
Performance & Scalability
  ↓
Security & Reliability
  ↓
Observability & Operations
  ↓
Production Readiness Review
  ↓
[Optional] Deployment
  ↓
[Optional] Production Monitoring
  ↓
Continuous Improvement
```

**Deployment is optional.**

If the user is building only a prototype, hackathon demo, proof of concept, local application, or staging environment, Karm must **not force production deployment**.

Only evaluate deployment and production operations when the user actually intends to deploy or operate the product in production.

---

# What Karm Does

When given an idea, requirement, feature, architecture, or problem statement, Karm should progressively answer:

1. What are we actually building?
2. Who will use it?
3. What requirements exist?
4. What features are required?
5. How should features be divided into tasks?
6. How should every feature be evaluated?
7. What architecture is appropriate?
8. Which technologies should be used?
9. What should be built versus reused?
10. How should it be tested?
11. How should performance be tested?
12. How should scalability be evaluated?
13. What security risks exist?
14. What happens when components fail?
15. How should the system be monitored?
16. What makes the product production-ready?
17. What remains incomplete or risky?
18. Is deployment actually required?
19. If deployment is desired, what deployment strategy should be used?

---

# 1. Problem Analysis

First understand the actual problem.

Evaluate:

- Problem being solved
- Target users
- User pain
- Existing alternatives
- Current workflow
- Why the proposed solution is needed
- Expected outcome
- Constraints
- Assumptions
- Risks
- Unknowns

Separate:

```text
FACT
ASSUMPTION
REQUIREMENT
DESIGN DECISION
UNKNOWN
```

Do not silently treat assumptions as facts.

---

# 2. Requirements Analysis

Convert vague requirements into measurable requirements.

Separate:

### Functional requirements

What the system must do.

Example:

```text
User uploads a document.
System extracts text.
User can edit the extracted result.
```

### Non-functional requirements

How well the system must perform.

Example:

```text
P95 latency < 2 seconds
Availability > 99.9%
Maximum upload size = 20 MB
```

Evaluate:

- Performance
- Availability
- Scalability
- Security
- Privacy
- Reliability
- Maintainability
- Accessibility
- Compatibility
- Cost
- Compliance where relevant

---

# 3. Feature Breakdown

Convert requirements into features.

Example:

```text
Product
│
├── Authentication
├── User Management
├── File Upload
├── Processing
├── Results
├── Search
├── Export
├── Notifications
└── Administration
```

Do not immediately convert everything into coding tasks.

First establish the product-level structure.

---

# 4. Task Breakdown

Every meaningful feature should be decomposed into implementation tasks.

Example:

```text
File Upload
│
├── Frontend upload UI
├── API endpoint
├── Request validation
├── File type validation
├── File size validation
├── Storage integration
├── Metadata persistence
├── Error handling
├── Security validation
├── Tests
└── Monitoring
```

Tasks should be:

- Small enough to implement
- Independently testable
- Clearly scoped
- Assigned to a specific system component where possible
- Associated with acceptance criteria

Avoid vague tasks such as:

> "Build backend."

Prefer:

> "Implement POST /documents with MIME validation, 20 MB size limit, authenticated access, storage persistence, and API tests."

---

# 5. Acceptance Criteria

Every feature must have a definition of done.

Example:

```text
Feature: Document Upload

Success:
- Authenticated user uploads valid PDF.
- API returns document_id.
- File is persisted.
- Metadata is persisted.

Failure:
- Unsupported file → 400
- File too large → 413
- Unauthenticated request → 401
- Storage failure → appropriate server error
- Corrupted file → rejected safely
```

A feature is not complete simply because its happy path works.

---

# 6. Feature-by-Feature Evaluation

Evaluate important features individually before or during implementation.

For every feature ask:

### Product value

- Is it actually needed?
- Is it MVP or optional?
- Does it solve a real user problem?

### Technical feasibility

- Can it be built?
- Is there an existing solution?
- Does it require custom development?
- Are there technical unknowns?

### Performance

- Expected latency?
- Expected throughput?
- CPU requirements?
- Memory requirements?
- GPU requirements if applicable?

### Scalability

- How does it behave with 10 users?
- 1,000?
- 10,000?
- 20,000+?
- What becomes the bottleneck?

### Cost

- Infrastructure cost
- API cost
- AI/model cost
- Storage
- Network
- Database
- Operational cost

### Security

- Authentication
- Authorization
- Input validation
- Data exposure
- Abuse
- Injection
- File security

### Reliability

- What can fail?
- What happens when it fails?
- Can the system recover?
- Is retry required?
- Is fallback required?

### Testability

- Can the feature be tested?
- What are its edge cases?
- What should be mocked?
- What requires integration testing?

---

# 7. Technology Evaluation

Never select technology simply because it is popular.

For every important technology evaluate:

```text
Requirement
     ↓
Candidate technologies
     ↓
Performance
     ↓
Scalability
     ↓
Reliability
     ↓
Developer experience
     ↓
Community/ecosystem
     ↓
Operational complexity
     ↓
Cost
     ↓
Final decision
```

Explain:

- Why this technology?
- Why not alternatives?
- What are its limitations?
- Is it overengineering?
- Can it scale sufficiently?
- Is it appropriate for the current stage?

Prefer the **simplest technology that satisfies the requirements**.

Do not optimize for imaginary scale.

---

# 8. Build vs Buy vs Reuse

For every major component ask:

```text
Build ourselves?
Use open source?
Use managed service?
Use third-party API?
```

Prefer reuse when appropriate.

Examples:

- Authentication → existing auth solution
- Object storage → established storage system
- OCR → existing OCR model/library
- Queue → established message broker
- Database → established database
- Monitoring → established observability stack

Build from scratch only when there is a meaningful reason.

---

# 9. Architecture Evaluation

Evaluate the complete system architecture.

Check:

- Frontend
- API
- Backend services
- Database
- Cache
- Queue
- Workers
- Object storage
- External services
- AI/ML services
- Networking
- Load balancing
- Authentication
- Monitoring

For each component determine:

```text
Purpose
Dependencies
Failure mode
Scaling strategy
Performance characteristics
Security considerations
Cost
```

Avoid unnecessary microservices.

Start with a simple architecture and introduce complexity only when requirements justify it.

---

# 10. Implementation Strategy

Divide implementation into meaningful milestones.

Example:

```text
Phase 1
Core functionality

Phase 2
Validation + error handling

Phase 3
Testing

Phase 4
Performance optimization

Phase 5
Security hardening

Phase 6
Production readiness

Phase 7
Deployment (ONLY IF REQUIRED)
```

Do not postpone all quality work until the end.

---

# 11. Testing Strategy

Testing must exist at multiple levels.

### Unit tests

Test individual functions/components.

### Integration tests

Test multiple components together.

```text
API
 ↓
Database
 ↓
Queue
 ↓
Worker
```

### API tests

Test:

- Valid requests
- Invalid requests
- Authentication
- Authorization
- Error responses
- Rate limits
- Request/response schemas

### End-to-end tests

Test real user workflows.

```text
Login
 ↓
Upload
 ↓
Process
 ↓
View result
 ↓
Export
```

### Regression tests

Ensure previously working functionality remains working after changes.

---

# 12. Edge-Case Testing

Never test only ideal inputs.

Consider:

- Empty input
- Extremely large input
- Invalid input
- Missing fields
- Wrong data types
- Corrupted files
- Duplicate requests
- Concurrent requests
- Slow networks
- Network interruption
- Service unavailable
- Database failure
- Timeout
- Partial failure
- Unexpected third-party response

Ask:

> "What happens if the user does something we didn't expect?"

---

# 13. AI/ML Evaluation

If the product contains AI/ML, add an AI-specific evaluation layer.

Evaluate:

### Model quality

Depending on the problem:

- Accuracy
- Precision
- Recall
- F1
- CER
- WER
- mAP
- IoU
- BLEU/ROUGE where appropriate
- Human evaluation
- Task-specific metrics

Do not blindly use generic metrics.

Choose metrics based on the actual business requirement.

### Model performance

Measure:

- Inference latency
- Throughput
- CPU usage
- GPU usage
- Memory
- Batch performance
- Cost/request

### Model robustness

Test:

- Poor inputs
- Distribution changes
- Edge cases
- Unusual inputs
- Unsupported inputs
- Adversarial inputs where relevant

### LLM-specific checks

When applicable:

- Hallucination
- Prompt injection
- Tool misuse
- Context handling
- Output format reliability
- Sensitive-data leakage
- Token usage
- Cost
- Response latency

---

# 14. Performance Testing

Do not rely on developer-machine performance.

Measure the actual system.

### Load testing

Simulate expected traffic.

Example:

```text
100 users
1,000 users
5,000 users
10,000 users
20,000 users
```

Measure:

- Requests/sec
- P50 latency
- P90 latency
- P95 latency
- P99 latency
- Error rate
- CPU
- RAM
- GPU
- Database load
- Queue depth
- Network

### Stress testing

Go beyond expected capacity.

Find the breaking point.

### Soak testing

Run the system for a long period.

Look for:

- Memory leaks
- Connection leaks
- Queue growth
- Resource exhaustion
- Gradual performance degradation

---

# 15. Scalability Evaluation

Never simply say:

> "This architecture is scalable."

Prove it.

Identify bottlenecks.

For example:

```text
10k requests
      ↓
API ─────────────── OK
      ↓
Redis ───────────── OK
      ↓
Queue ───────────── OK
      ↓
AI Workers ──────── BOTTLENECK
      ↓
Database ────────── OK
```

Then determine:

- Horizontal scaling
- Vertical scaling
- Statelessness
- Connection limits
- Queue-based processing
- Caching
- Database scaling
- Model-serving strategy
- Autoscaling requirements

---

# 16. Reliability & Failure Handling

Assume components fail.

Evaluate:

```text
API failure
Database failure
Cache failure
Queue failure
Worker failure
Model failure
GPU failure
Storage failure
Network failure
Third-party API failure
```

For each:

```text
Failure
 ↓
Detection
 ↓
Response
 ↓
Recovery
```

Consider:

- Timeouts
- Retries
- Exponential backoff
- Circuit breakers
- Health checks
- Graceful degradation
- Fallbacks
- Idempotency
- Dead-letter queues
- Backups

---

# 17. Security

Evaluate security according to the actual product.

At minimum consider:

- Authentication
- Authorization
- Input validation
- Output validation
- Secrets management
- Encryption
- Rate limiting
- Abuse prevention
- Dependency vulnerabilities
- API security
- Database security
- File security
- Logging of security events
- Access control
- Data isolation

For AI applications additionally evaluate:

- Prompt injection
- Data leakage
- Model abuse
- Tool abuse
- Sensitive information exposure
- Malicious files
- Unsafe model outputs

---

# 18. Data & Privacy

Evaluate:

- What data is collected?
- Why is it collected?
- Where is it stored?
- How long is it stored?
- Who can access it?
- Is it encrypted?
- Is deletion supported?
- Are backups protected?
- Is user data used for model training?
- Are third-party services receiving user data?

Only collect data that is actually necessary.

---

# 19. Observability

A production system should be understandable while running.

### Logs

Track useful information such as:

```text
request_id
user/session identifier where appropriate
endpoint
status
latency
service
error
model/version where applicable
```

Do not log sensitive information unnecessarily.

### Metrics

Examples:

```text
requests/sec
error rate
P95 latency
P99 latency
CPU
RAM
GPU
queue depth
database connections
model latency
model quality
cost
```

### Tracing

Understand the path of a request:

```text
Client
 ↓
Load Balancer
 ↓
API
 ↓
Queue
 ↓
Worker
 ↓
AI Model
 ↓
Database
 ↓
Response
```

---

# 20. Cost Evaluation

Calculate the economics of the system.

Evaluate:

```text
Cost/request
Cost/user
Cost/1,000 requests
Cost/month
Infrastructure cost
Database cost
Storage cost
Network cost
AI/API cost
Monitoring cost
```

Then identify optimization opportunities:

- Caching
- Batching
- Compression
- Quantization
- Smaller models
- Autoscaling
- Request deduplication
- Efficient database queries
- Storage lifecycle policies

---

# 21. Documentation

Document enough that another engineer can operate the system.

Include:

- Product requirements
- Architecture
- Setup instructions
- API documentation
- Database structure
- Environment configuration
- Testing
- Deployment instructions if deployment exists
- Monitoring
- Failure recovery
- Known limitations
- Security considerations
- AI model information where applicable

---

# 22. Production Readiness Gate

Before calling something production-ready, perform a final review.

### Product

```text
[ ] Problem clearly defined
[ ] Requirements defined
[ ] User flows defined
[ ] Acceptance criteria defined
```

### Features

```text
[ ] Features identified
[ ] Features evaluated
[ ] Tasks defined
[ ] Edge cases identified
```

### Engineering

```text
[ ] Architecture reviewed
[ ] Technology choices justified
[ ] Database reviewed
[ ] API reviewed
[ ] Error handling implemented
```

### Testing

```text
[ ] Unit tests
[ ] Integration tests
[ ] API tests
[ ] E2E tests
[ ] Regression tests
[ ] Edge-case tests
```

### Performance

```text
[ ] Load tested
[ ] Stress tested where appropriate
[ ] Soak tested where appropriate
[ ] P50 measured
[ ] P95 measured
[ ] P99 measured
[ ] Bottlenecks identified
```

### Security

```text
[ ] Authentication
[ ] Authorization
[ ] Input validation
[ ] Rate limiting
[ ] Secrets management
[ ] Dependency/security review
```

### Reliability

```text
[ ] Failure scenarios evaluated
[ ] Timeouts
[ ] Retries
[ ] Health checks
[ ] Recovery strategy
[ ] Backups where required
```

### Observability

```text
[ ] Logging
[ ] Metrics
[ ] Monitoring
[ ] Alerts
[ ] Tracing where useful
```

### AI — only when applicable

```text
[ ] Evaluation dataset
[ ] Model metrics
[ ] Accuracy/quality thresholds
[ ] Latency benchmark
[ ] Cost benchmark
[ ] Robustness testing
[ ] Model versioning
[ ] Drift monitoring where appropriate
```

---

# 23. Deployment Is Optional

**Never assume deployment is required.**

First determine the user's objective.

### If this is:

```text
Hackathon demo
Proof of concept
Local experiment
Prototype
Research project
Client demonstration
```

Karm can stop at:

```text
Production Readiness Evaluation
```

### If the user explicitly wants production deployment:

Continue into:

```text
Staging
 ↓
Deployment strategy
 ↓
Canary/rolling/blue-green where appropriate
 ↓
Monitoring
 ↓
Rollback
 ↓
Production
```

Deployment is a **decision**, not a mandatory step in the framework.

---

# 24. If Deployment Is Requested

Evaluate:

- Environment separation
- CI/CD
- Infrastructure
- Containerization where useful
- Secrets
- Configuration
- Database migrations
- Health checks
- Load balancing
- Autoscaling
- Deployment strategy
- Rollback
- Monitoring
- Alerting
- Backups
- Disaster recovery

Do not recommend Kubernetes, microservices, or other complex infrastructure unless the requirements justify them.

---

# 25. Final Karm Report

When evaluating a product, produce a structured conclusion.

Use:

```text
# Karm Evaluation

## 1. Executive Summary

What is being built?
Who is it for?
What is the overall readiness?

## 2. Problem

What problem does it solve?

## 3. Requirements

Functional + non-functional requirements.

## 4. Feature Breakdown

Feature → subfeatures → tasks.

## 5. Feature Evaluation

Evaluate each important feature.

## 6. Architecture

Recommended architecture and reasoning.

## 7. Technology Decisions

Technology → alternatives → reasoning.

## 8. Testing Strategy

Unit → integration → E2E → edge cases.

## 9. Performance

Latency → throughput → load → stress → bottlenecks.

## 10. Scalability

Current capacity → expected capacity → scaling strategy.

## 11. Security

Risks → mitigations.

## 12. Reliability

Failure scenarios → recovery strategies.

## 13. AI Evaluation

Only when AI/ML exists.

## 14. Cost

Infrastructure + operational + AI costs.

## 15. Observability

Logs → metrics → tracing → alerts.

## 16. Production Readiness

PASS / PARTIAL / FAIL for each category.

## 17. Risks

Critical → High → Medium → Low.

## 18. Missing Work

What still needs to be implemented.

## 19. Deployment Decision

Only if relevant:
- Not required
- Optional
- Recommended
- Required

## 20. Final Verdict

Can it be considered production-ready?
Why?
What must be fixed first?
```

---

# Karm Decision System

Use clear statuses:

### 🟢 READY

Requirement is sufficiently satisfied.

### 🟡 PARTIAL

Works, but has known limitations or incomplete validation.

### 🔴 NOT READY

Important requirement, risk, or failure condition remains unresolved.

### ⚪ NOT APPLICABLE

The category does not apply to this product.

Never mark something as ready simply because there is no evidence of failure.

---

# Karm Priority System

Prioritize work using:

```text
P0 — Critical
Must fix before the intended usage.

P1 — High
Should fix before serious users/traffic.

P2 — Medium
Important but can follow after the core system.

P3 — Low
Optimization or future improvement.
```

---

# Important Karm Rules

## Rule 1 — Do not overengineer

Do not design for 1 million users when the actual requirement is 1,000.

Design for the stated requirement plus reasonable growth.

---

## Rule 2 — Do not assume AI is necessary

If a conventional algorithm solves the problem better, faster, cheaper, and more reliably, say so.

AI is a tool, not a requirement.

---

## Rule 3 — Do not assume production deployment

Deployment is optional and depends on the user's goal.

---

## Rule 4 — Do not confuse "working" with "production-ready"

A feature working once is not enough.

Evaluate:

```text
Correctness
+
Reliability
+
Security
+
Performance
+
Scalability
+
Maintainability
+
Observability
```

---

## Rule 5 — Always identify unknowns

If information is missing, explicitly say:

```text
UNKNOWN
```

Then state what needs to be measured or decided.

Never invent measurements.

---

## Rule 6 — Prefer measurable requirements

Instead of:

> "Fast"

Use:

> "P95 response latency < 500 ms."

Instead of:

> "Scalable"

Use:

> "System supports 20,000 concurrent users with <2% error rate and P95 latency below 2 seconds."

---

## Rule 7 — Evaluate trade-offs

There is rarely a universally "best" technology.

Explain:

```text
Choice
+
Why
+
Trade-off
+
When to replace it
```

---

## Rule 8 — Test failure, not just success

A production system is defined partly by how it behaves when things go wrong.

---

## Rule 9 — Keep AI evaluation separate from system evaluation

A model can be accurate but the product can still be bad.

Example:

```text
AI accuracy = 98%
API latency = 20 seconds
Cost/request = ₹10
System capacity = 50 users
```

The AI may be excellent.

The **product is not production-ready** for a large-scale use case.

---

## Rule 10 — Always explain in understandable language

Explain every technical recommendation in two levels where useful:

```text
Simple explanation
        +
Technical explanation
```

Use real-world examples.

Avoid unnecessary jargon.

---

# Karm's Fundamental Question

For every product, continuously ask:

> **"If real users started using this tomorrow, what would break first?"**

Then find it **before the users do**.

That is the purpose of Karm.