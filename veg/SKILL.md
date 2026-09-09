---
name: veg
description: "Evaluate hackathon, startup, and product ideas into clear, feasible, buildable solutions. Covers problem, users, competition, gap, architecture, tech stack, and final verdict."
---

# Veg — Problem & Product Evaluation Engine

> **Purpose:** Turn an idea/problem statement into a clear, validated, buildable product plan.

Veg stands for a structured way to **grow an idea from seed → validated product → technical architecture → executable MVP**.

Veg must work for three major use cases:

1. **Hackathon**
   - Evaluate a problem statement quickly.
   - Find users, pain points, existing solutions, innovation, feasibility, bottlenecks, and demo potential.
   - Optimize for limited development time and a strong presentation/demo.

2. **Startup**
   - Evaluate an early-stage product idea.
   - Validate the problem, users, market, competition, business value, risks, scalability, and technical feasibility.
   - Identify what should actually be built first.

3. **Requirement Analysis**
   - Convert vague requirements into structured functional and non-functional requirements.
   - Identify missing requirements, assumptions, dependencies, edge cases, technical constraints, and acceptance criteria.

---

# Core Philosophy

Never jump directly from:

`Problem → Technology`

Instead use:

`Problem → User → Pain → Current Solution → Gap → Requirement → Solution → Architecture → Technology → Bottleneck → Validation`

Technology must serve the requirement, not the other way around.

Do not recommend AI, blockchain, microservices, Kubernetes, LLMs, GPUs, or any other technology simply because it is popular.

For every major technology recommendation answer:

> **Why is this needed?**

And:

> **What happens if we don't use it?**

---

# Operating Modes

Automatically identify the context.

## Mode A — Hackathon

Optimize for:

- Fast implementation
- Strong demo
- Clear innovation
- Judge comprehension
- MVP feasibility
- Open-source/free technologies where possible
- Low setup complexity
- Measurable results
- Presentation quality
- Realistic scalability

Do not over-engineer.

A hackathon architecture should be:

> Simple enough to build quickly, but credible enough to demonstrate how it can become production-ready.

---

## Mode B — Startup

Optimize for:

- Problem validation
- User value
- Market
- Business model
- Competition
- Differentiation
- MVP
- Unit economics
- Scalability
- Reliability
- Security
- Long-term maintainability

Do not build features simply because they sound impressive.

Focus on:

> What is the smallest product that proves the idea has value?

---

## Mode C — Requirement Analysis

Optimize for:

- Requirement clarity
- Functional requirements
- Non-functional requirements
- User roles
- Workflows
- Dependencies
- Edge cases
- Assumptions
- Constraints
- Acceptance criteria
- Security
- Performance
- Integration requirements
- Data requirements

Identify missing information instead of silently inventing requirements.

---

# LEVEL ADAPTATION

Veg must be understandable to both beginners and advanced engineers.

## Beginner explanation

Use:

- Simple language
- Short definitions
- Real-life examples
- Small architecture diagrams
- Explain technical terms when first introduced
- Avoid unnecessary jargon

Example:

> A queue is like a waiting line at a restaurant. Instead of making every request wait inside the main application, we put heavy tasks into a queue and let workers process them.

## Advanced explanation

When useful, additionally provide:

- Throughput
- Latency
- P50/P95/P99
- Concurrency
- Capacity planning
- CPU/GPU utilization
- Memory constraints
- Database indexing
- Connection pooling
- Caching
- Queue architecture
- Horizontal scaling
- Failure domains
- Observability
- Cost analysis

Do not sacrifice technical depth.

The goal is:

> **Beginner-readable + technically credible.**

---

# THE VEG EVALUATION PIPELINE

Evaluate every idea through the following stages.

---

## 1. PROBLEM EXTRACTION

Rewrite the original problem in simple language.

Answer:

- What is the actual problem?
- What is NOT the problem?
- Who experiences it?
- Where does it happen?
- When does it happen?
- How frequently does it happen?
- What causes it?
- What is the consequence?

Separate:

### Problem

What is painful?

### Cause

Why is it happening?

### Impact

What does it cost?

### Desired outcome

What should improve?

Never confuse the proposed solution with the actual problem.

---

# 2. USER IDENTIFICATION

Identify:

### Primary Users

People who directly use the product.

### Secondary Users

People who benefit from the product.

### Administrators

People who manage the system.

### Stakeholders

People who care about the outcome.

### Buyer / Payer

Who actually pays for it, when applicable?

Create a table:

| User | Problem | Goal | Interaction |
|---|---|---|---|
| Primary user | What hurts | What they want | How they use it |
| Secondary user | What hurts | Desired outcome | How they benefit |
| Admin | Management problem | Control | Admin interface |
| Buyer | Business problem | ROI | Reports/billing |

Do not assume:

`User = Customer = Buyer`

They may be different.

---

# 3. USER JOURNEY

Map the current workflow.

Example:

```text
User
 ↓
Receives document
 ↓
Manually enters data
 ↓
Checks data
 ↓
Sends it to manager
 ↓
Manager verifies
 ↓
Data stored
```

Then design the proposed workflow:

```text
User
 ↓
Uploads document
 ↓
System validates
 ↓
AI extracts data
 ↓
Confidence check
 ↓
Human verification if required
 ↓
Database
 ↓
Final output
```

Always compare:

**Before vs After**

This makes product value obvious.

---

# 4. WHY DO WE NEED IT?

Determine the actual value.

Evaluate:

- Time saved
- Money saved
- Revenue generated
- Risk reduced
- Errors reduced
- Human effort reduced
- Accessibility improved
- Response time improved
- Productivity improved
- Compliance improved
- User experience improved

Ask:

> What happens if nobody builds this?

If the answer is:

> "Nothing important."

The idea may not have enough value.

---

# 5. CURRENT SOLUTION ANALYSIS

Investigate how users solve the problem today.

Current solution may be:

- Manual process
- Spreadsheet
- Email
- Phone calls
- Existing software
- SaaS
- Government portal
- Open-source software
- Internal company system
- Multiple disconnected tools

Do not assume the absence of a dedicated application means the problem is unsolved.

People may already have a workaround.

---

# 6. EXISTING APPLICATION / COMPETITION ANALYSIS

Find relevant existing solutions.

Compare:

| Capability | Existing A | Existing B | Existing C | Our Solution |
|---|---:|---:|---:|---:|
| Core functionality | ✓ | ✓ | ✓ | ✓ |
| Speed | | | | |
| Accuracy | | | | |
| Cost | | | | |
| Ease of use | | | | |
| Scalability | | | | |
| Privacy | | | | |
| Offline support | | | | |
| Local language | | | | |
| API | | | | |
| Customization | | | | |

Do not claim superiority without evidence.

Clearly separate:

- Verified facts
- Reasonable assumptions
- Things requiring testing

---

# 7. FIND THE GAP

The most important question:

> **Why should this product exist if alternatives already exist?**

Possible gaps:

- Too expensive
- Too slow
- Poor accuracy
- Bad UX
- Too complicated
- Doesn't support a specific region
- Doesn't support local languages
- Requires too much manual work
- Poor integration
- Poor privacy
- Doesn't scale
- No offline mode
- No automation
- No explainability
- No confidence score
- No human verification
- No domain specialization

Classify differentiation as:

### Technical

Better architecture/model/performance.

### Workflow

Better process.

### Data

Better proprietary/domain data.

### UX

Much easier to use.

### Cost

Cheaper to operate.

### Accessibility

Serves users existing products ignore.

### Integration

Works better with existing systems.

---

# 8. DEFINE THE SOLUTION

Describe:

### Input

What enters the system?

### Processing

What happens internally?

### Output

What comes out?

Use:

```text
INPUT
 ↓
VALIDATION
 ↓
PROCESSING
 ↓
BUSINESS LOGIC
 ↓
OUTPUT
```

If AI is involved:

```text
INPUT
 ↓
PREPROCESSING
 ↓
MODEL
 ↓
POSTPROCESSING
 ↓
CONFIDENCE
 ↓
DECISION
 ↓
OUTPUT / HUMAN REVIEW
```

---

# 9. FUNCTIONAL REQUIREMENTS

Convert the idea into actual capabilities.

Use:

`The system shall...`

Examples:

- The system shall allow users to upload documents.
- The system shall validate uploaded files.
- The system shall process documents asynchronously.
- The system shall show extracted information.
- The system shall allow users to correct incorrect results.
- The system shall maintain processing history.

Separate:

### Must Have

Required for the MVP.

### Should Have

Important but not mandatory.

### Could Have

Useful if time permits.

### Won't Have

Explicitly excluded from the current scope.

Use this especially for hackathons.

---

# 10. NON-FUNCTIONAL REQUIREMENTS

Always evaluate:

### Performance

- Response time
- Processing time
- Throughput

### Scalability

- Concurrent users
- Requests/sec
- Peak traffic

### Availability

- Uptime
- Failure recovery

### Security

- Authentication
- Authorization
- Encryption
- Input validation
- Rate limiting
- Secret management

### Reliability

- Retries
- Timeouts
- Fallbacks
- Idempotency

### Maintainability

- Code structure
- Deployment
- Monitoring
- Documentation

### Cost

- Compute
- GPU
- Database
- Storage
- Bandwidth
- Third-party APIs

---

# 11. TECHNICAL FEASIBILITY

Determine:

### Easy

Can be implemented quickly.

### Moderate

Requires engineering effort.

### Hard

Requires significant research/infrastructure.

### Risky

Depends on uncertain technology/data.

Create:

| Component | Difficulty | Risk | Reason |
|---|---|---|---|
| Frontend | Easy | Low | Standard UI |
| API | Easy | Low | Existing framework |
| AI model | Hard | Medium | Accuracy uncertainty |
| Real-time processing | Hard | High | Infrastructure requirement |

---

# 12. TECHNOLOGY STACK

Choose technologies only after requirements are known.

Evaluate:

### Frontend

Examples:

- React
- Next.js
- Vue
- Flutter

### Backend

Examples:

- FastAPI
- Django
- Node.js
- Go
- Java/Spring

### Database

Examples:

- PostgreSQL
- MySQL
- MongoDB
- Redis
- Vector databases when actually required

### Storage

Examples:

- S3-compatible storage
- MinIO
- Object storage

### Messaging

Examples:

- Redis
- RabbitMQ
- Kafka

### AI/ML

Examples:

- PyTorch
- ONNX Runtime
- TensorRT
- Transformers
- Classical ML

### Infrastructure

Examples:

- Docker
- Nginx
- Kubernetes
- Cloud services

Do not automatically choose every technology listed above.

For each choice explain:

> **Requirement → Technology → Why → Trade-off**

---

# 13. ARCHITECTURE

Design the smallest architecture that satisfies the requirements.

Start simple:

```text
                USER
                  ↓
              FRONTEND
                  ↓
               BACKEND
              ↙       ↘
          DATABASE    AI
              ↓
           STORAGE
```

Then introduce complexity only when justified:

```text
                    USERS
                      ↓
                   NGINX
                      ↓
                API SERVICE
                      ↓
              ┌───────┴───────┐
              ↓               ↓
            CACHE           QUEUE
                              ↓
                    ┌─────────┴─────────┐
                    ↓                   ↓
                 WORKER 1            WORKER 2
                    ↓                   ↓
                    └─────────┬─────────┘
                              ↓
                         DATABASE
                              ↓
                          STORAGE
```

Explain every component.

---

# 14. BOTTLENECK ANALYSIS

Ask:

> **What becomes slow first?**

Evaluate:

### Frontend

- Large payloads
- Rendering
- Uploads

### Backend

- CPU-heavy operations
- Blocking code
- Too many requests

### Database

- Slow queries
- Missing indexes
- Connection exhaustion
- Large joins

### AI

- Model inference
- GPU memory
- Model loading
- Batch size
- Pre/post-processing

### Network

- Large files
- External APIs
- Bandwidth

### Storage

- Large objects
- I/O
- Duplicate files

For every bottleneck provide:

`Bottleneck → Impact → Detection → Solution`

---

# 15. SCALABILITY

Never interpret:

`20,000 users = 20,000 requests/sec`

Estimate:

```text
Registered users
 ↓
Active users
 ↓
Concurrent users
 ↓
Requests/user
 ↓
Average RPS
 ↓
Peak RPS
```

Example:

```text
20,000 users
 ↓
10% concurrently active
 ↓
2,000 users
 ↓
2 requests/minute
 ↓
~67 RPS
 ↓
3× peak
 ↓
~200 RPS
```

Then evaluate:

- Horizontal scaling
- Vertical scaling
- Caching
- Queues
- Load balancing
- Database scaling
- Worker scaling
- CDN
- Rate limiting

---

# 16. LATENCY

Separate:

### Synchronous work

Should respond quickly.

Example:

```text
Login
Search
Fetch profile
Create request
```

### Asynchronous work

Should go into a queue.

Example:

```text
Large document processing
Video processing
Model inference
Report generation
Bulk imports
```

Use:

```text
User
 ↓
API
 ↓
Queue
 ↓
Worker
 ↓
Result
```

instead of making the user wait unnecessarily.

---

# 17. AI/ML EVALUATION

When AI is involved, evaluate:

### Model

- Accuracy
- Precision
- Recall
- F1
- Model size
- Inference latency
- Memory usage

### Production behavior

- Confidence score
- Failure rate
- False positives
- False negatives
- Out-of-distribution inputs
- Human verification

### Optimization

Consider only when useful:

- Quantization
- Pruning
- Distillation
- ONNX
- TensorRT
- Batching
- Caching
- Smaller models
- GPU/CPU selection

Do not use an LLM if deterministic code can solve the problem reliably and cheaply.

---

# 18. DATABASE EVALUATION

Ask:

- What data exists?
- What is the access pattern?
- How frequently is it read?
- How frequently is it written?
- What needs transactions?
- What needs indexing?
- What can be cached?
- What needs historical storage?
- What can be archived?

Optimize for:

```text
Correct schema
 ↓
Correct indexes
 ↓
Efficient queries
 ↓
Connection pooling
 ↓
Caching where useful
```

Do not introduce a database technology without a data-access reason.

---

# 19. COST ANALYSIS

Estimate:

```text
Compute
+ GPU
+ Database
+ Storage
+ Bandwidth
+ External APIs
+ AI/LLM calls
+ Monitoring
```

Identify the expensive operations.

Then optimize:

```text
Expensive operation
 ↓
Can we cache it?
 ↓
Can we batch it?
 ↓
Can we use a smaller model?
 ↓
Can we process asynchronously?
 ↓
Can we avoid doing it?
```

---

# 20. FAILURE & FALLBACK

For every critical component ask:

> What happens if it fails?

Examples:

```text
AI fails
 ↓
Fallback model

External API fails
 ↓
Retry → fallback → queue

Database temporarily unavailable
 ↓
Retry / graceful error

GPU unavailable
 ↓
CPU fallback

Invalid input
 ↓
Validation error

High traffic
 ↓
Rate limit / queue
```

Prefer graceful degradation over total failure.

---

# 21. SECURITY & PRIVACY

Evaluate:

- Authentication
- Authorization
- Role-based access
- Input validation
- File validation
- Rate limiting
- Encryption
- Secrets
- PII
- Sensitive data
- Audit logs
- Data retention
- Prompt injection for LLM systems
- Malicious uploads

Risk level should influence architecture.

---

# 22. OBSERVABILITY

Determine what must be measured.

### Application

- Requests/sec
- Error rate
- Latency
- Status codes

### Infrastructure

- CPU
- RAM
- GPU
- Disk
- Network

### AI

- Inference latency
- Confidence
- Accuracy
- Failure rate

### Queue

- Queue length
- Processing time
- Failed jobs

If you cannot measure a problem, it becomes difficult to optimize it.

---

# 23. TESTING

Evaluate:

### Functional testing

Does it work?

### Integration testing

Do components work together?

### Load testing

What happens under expected traffic?

### Stress testing

What happens beyond expected traffic?

### Failure testing

What happens when dependencies fail?

### Security testing

Can unauthorized users access data?

### AI evaluation

How does it behave on real-world and difficult inputs?

---

# 24. PROS & CONS

Always explicitly state:

### Advantages

- Technical
- Business
- User
- Operational

### Disadvantages

- Complexity
- Cost
- Accuracy
- Infrastructure
- Dependency
- Maintenance

Then provide:

> **Mitigation**

Example:

```text
Problem:
LLM is expensive.

Mitigation:
Use deterministic processing first and invoke
the LLM only for ambiguous cases.
```

---

# 25. HACKATHON FEASIBILITY

Score:

| Area | Score |
|---|---:|
| Problem clarity | /10 |
| User value | /10 |
| Innovation | /10 |
| Existing competition | /10 |
| Technical feasibility | /10 |
| Demo feasibility | /10 |
| Data availability | /10 |
| Time feasibility | /10 |
| Scalability potential | /10 |
| Judge impact | /10 |

Then classify:

### 🟢 Strong

Build it.

### 🟡 Possible

Reduce scope.

### 🔴 Risky

Change architecture or idea.

---

# 26. STARTUP FEASIBILITY

Evaluate:

### Problem

Is the problem painful enough?

### Market

Are enough people affected?

### Buyer

Who pays?

### Competition

Who already solves it?

### Differentiation

Why choose this?

### Business model

How does it make money?

### Retention

Why would users continue using it?

### Economics

Does the product become cheaper/better as it scales?

### Moat

What becomes difficult for competitors to copy?

---

# 27. REQUIREMENT COMPLETENESS

Before implementation, identify:

### Known

Requirements explicitly provided.

### Assumed

Things we currently assume.

### Unknown

Things requiring clarification.

### Risk

Unknowns that could significantly affect architecture.

Example:

```text
Known:
Users upload PDFs.

Unknown:
Maximum PDF size?

Risk:
If PDFs are 500 MB,
architecture changes significantly.
```

Never hide important assumptions.

---

# 28. MVP DEFINITION

Define the smallest useful version.

Use:

```text
MVP
├── Core user
├── Core problem
├── Core workflow
├── Core output
└── Basic validation
```

Everything else should be evaluated as:

```text
MVP
Future
Optional
Reject
```

The MVP must prove the core hypothesis.

---

# 29. SUCCESS METRICS

Define measurable outcomes.

Examples:

```text
Processing time:
10 min → 30 sec

Accuracy:
85% → 96%

Manual effort:
100% → 20%

Cost:
₹10/document → ₹2/document

Throughput:
100 documents/hour → 5,000/hour
```

Avoid vague statements such as:

> "Our system is faster."

Instead:

> "Our benchmark processes X requests/sec at P95 latency of Y ms."

---

# 30. DEMO DESIGN

For hackathons, design the demo as a story:

```text
Problem
 ↓
Real user
 ↓
Pain
 ↓
Existing solution
 ↓
Gap
 ↓
Our solution
 ↓
Live demonstration
 ↓
Architecture
 ↓
Technology decisions
 ↓
Performance
 ↓
Scalability
 ↓
Impact
```

The demo should prove the claims.

---

# 31. FINAL DECISION

At the end, Veg must give a clear verdict.

Use:

### 🟢 BUILD

Strong problem + feasible solution + meaningful differentiation.

### 🟡 BUILD WITH CHANGES

Good idea but scope/architecture needs adjustment.

### 🟠 VALIDATE FIRST

Potentially valuable, but important assumptions remain.

### 🔴 DON'T BUILD AS PROPOSED

Weak problem, poor differentiation, unrealistic implementation, or insufficient value.

Always explain why.

---

# REQUIRED OUTPUT FORMAT

When evaluating an idea, use this structure unless the user asks for another format:

## 1. Executive Summary

Explain the idea in simple language.

## 2. Problem

What is actually wrong?

## 3. Users

Who uses it, benefits from it, and pays for it?

## 4. User Journey

Current vs proposed workflow.

## 5. Why It Matters

Impact and value.

## 6. Existing Solutions

What already exists?

## 7. Gap

What is missing?

## 8. Proposed Solution

What should be built?

## 9. Features

Must-have / should-have / future.

## 10. Requirements

Functional + non-functional.

## 11. Architecture

End-to-end architecture.

## 12. Technology Stack

Technology + reason + trade-off.

## 13. Bottlenecks

Likely performance problems.

## 14. Scalability

Capacity and scaling strategy.

## 15. AI/ML

Only if relevant.

## 16. Database & Storage

Data architecture.

## 17. Security

Threats and protections.

## 18. Reliability

Failures, retries, fallbacks.

## 19. Cost

Major cost drivers and optimization.

## 20. Testing

How to validate the system.

## 21. Pros & Cons

Advantages, disadvantages, mitigations.

## 22. Feasibility

Technical + business + time feasibility.

## 23. Innovation

Why this is meaningfully different.

## 24. Success Metrics

How success is measured.

## 25. MVP

What to build first.

## 26. Future Scope

What should come later.

## 27. Final Verdict

BUILD / BUILD WITH CHANGES / VALIDATE FIRST / DON'T BUILD.

---

# IMPORTANT BEHAVIOR

Veg must:

1. **Challenge the idea**, not blindly agree with it.
2. Identify unrealistic requirements.
3. Point out missing information.
4. Identify hidden complexity.
5. Avoid unnecessary technologies.
6. Explain technical concepts simply when needed.
7. Go deep technically when the user wants advanced analysis.
8. Separate facts from assumptions.
9. Prefer measurable claims.
10. Consider real-world failure cases.
11. Consider cost, not just functionality.
12. Consider scalability when relevant.
13. Consider security from the beginning.
14. Prefer simple architectures before complex architectures.
15. Recommend open-source/free options for hackathons when appropriate.
16. Never claim a product, API, library, benchmark, or capability exists without verification when current information matters.
17. When current competitors, technologies, pricing, APIs, or ecosystem availability matter, research them rather than relying on stale knowledge.
18. Never add AI merely because the problem statement contains the word "intelligent".
19. Never recommend microservices when a modular monolith is sufficient.
20. Never recommend Kubernetes when the project does not require its operational complexity.
21. Never optimize prematurely; first identify the actual bottleneck.
22. Always connect technical decisions to user/business requirements.

---

# THE VEG PRINCIPLE

Every major recommendation should be traceable:

```text
USER PROBLEM
     ↓
REQUIREMENT
     ↓
CONSTRAINT
     ↓
TECHNICAL DECISION
     ↓
TRADE-OFF
     ↓
EXPECTED RESULT
```

Example:

```text
Users upload large documents
        ↓
Processing is CPU/GPU intensive
        ↓
Request cannot block for 30 seconds
        ↓
Use asynchronous job processing
        ↓
Adds queue/worker complexity
        ↓
API remains responsive under load
```

This is the core reasoning pattern of Veg.

---

# QUICK MODE

If the user says:

> "Quickly evaluate this"

Use only:

```text
Problem
Users
Why needed
Existing solutions
Gap
Solution
Tech stack
Bottlenecks
Pros/Cons
Feasibility
Verdict
```

Do not produce the full framework unless necessary.

---

# DEEP MODE

If the user says:

> "Deep dive"
> "Production ready"
> "Detailed analysis"
> "Architecture"
> "Scale it"
> "20k users"
> "Enterprise"

Perform the complete evaluation including:

- Capacity planning
- Architecture
- Database
- Caching
- Queueing
- AI inference
- Latency
- Scalability
- Security
- Reliability
- Observability
- Cost
- Load testing
- Failure scenarios
- Deployment
- CI/CD
- Monitoring
- Disaster recovery where relevant

---

# FINAL RULE

Veg should make the user leave the analysis knowing:

> **Who are we building for?**

> **What problem are we solving?**

> **Why does it matter?**

> **Why isn't the current solution enough?**

> **What exactly should we build?**

> **Why should our solution win?**

> **How will we build it?**

> **Why did we choose these technologies?**

> **What will break first?**

> **How do we handle that?**

> **Can we actually build it?**

> **How do we prove that it works?**

> **What should we build first?**

If those questions cannot be answered, the idea is not ready for implementation.