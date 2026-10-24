# Engineering Playbook: Evidence-Based Practices for Building and Shipping

Research synthesis of public guidance from Google, DORA, AWS, OpenAI, Anthropic, and Basecamp. This does not claim every strong builder follows one identical process or reveal private internal playbooks.

## Executive summary

Strong engineering is a repeatable feedback loop:

**Understand the problem → define observable success → reduce uncertainty → design the smallest coherent solution → implement in small changes → verify → review → release safely → observe real outcomes → improve.**

Recurring evidence-backed themes:
1. Small, self-contained changes are easier to review, test, merge, and roll back.
2. Automated tests, CI, deployment automation, version control, and observability improve delivery speed and safety.
3. Documentation should be short, accurate, and updated with code.
4. AI coding agents work better with repository context, bounded tasks, explicit acceptance criteria, and verification.
5. AI products need evaluations, traces, regression suites, and outcome checks—not subjective "seems good" testing.
6. Architecture and process should match workload risk; defer irrelevant checklist items.
7. Optimize for useful shipped outcomes and learning, not activity, tool count, or architectural sophistication.

## 1. End-to-end workflow

### Phase 0 — Choose a problem worth solving
- Identify a real user, pain point, and current workaround.
- Describe the desired outcome in one sentence.
- Validate the problem with a user, workflow observation, or available data.
- Define success metrics and a baseline where possible.
- State constraints, risks, assumptions, and non-goals.
- Reject or defer ideas with weak user value or excessive MVP scope.

Artifacts: short problem brief, success metric, assumptions and non-goals.

### Phase 1 — Shape the smallest useful slice
- Define one end-to-end user journey.
- Write observable, testable acceptance criteria.
- Separate MVP requirements from future ideas.
- Investigate high-impact unknowns first.
- Break work into small, independently reviewable slices.
- Plan around uncertainty and risk, not just code volume.

Artifacts: lightweight PRD or issue, acceptance criteria, prioritized backlog.

### Phase 2 — Design only as much as needed
- Map system context and key components.
- Identify domain entities, invariants, data ownership, and interfaces.
- Choose the simplest architecture that satisfies current requirements.
- Identify failure modes, trust boundaries, privacy, and operational needs.
- Record consequential decisions and trade-offs.
- For uncertain decisions, build a short spike rather than speculate indefinitely.

Artifacts: architecture sketch, API/data contract, decision record if useful.

### Phase 3 — Prepare the repository and developer workflow
- Ensure a new developer can build and run the project from the README.
- Use Git and small, coherent changes.
- Add formatter, linter, static checks, and tests appropriate to the stack.
- Set up fast CI feedback early.
- Make test data and local dependencies reproducible.
- Add repository-specific agent instructions only if using coding agents repeatedly.
- Keep secrets out of code and logs.

### Phase 4 — Implement one vertical slice at a time
For each slice:
1. Read relevant code and conventions.
2. Define expected behavior and failure cases.
3. Add or update a test where practical.
4. Make the smallest implementation that satisfies the contract.
5. Run targeted checks, then broader checks as risk warrants.
6. Inspect the diff for unrelated changes, complexity, security, and regressions.
7. Update documentation alongside behavior.
8. Commit a coherent change with a useful message.
9. Capture evidence and the next step.

Prefer small changes over a huge feature branch. A slice should be understandable without reconstructing the whole project.

### Phase 5 — Verify quality
- Unit tests for core logic.
- Integration tests at real boundaries.
- End-to-end tests for critical journeys.
- Regression tests for discovered bugs.
- Static analysis, linting, type checking, and dependency/security scans as appropriate.
- Test failure paths, retries, concurrency, authorization, and data integrity based on risk.
- Use realistic test data and deterministic test environments.
- Measure performance before optimizing.
- Coverage percentage is not a substitute for meaningful assertions.

### Phase 6 — Review
Review design, correctness, complexity, tests, security, naming, documentation, observability, migrations, compatibility, and rollback risk.

Ask: "Would another engineer understand this change, verify it, and safely modify or roll it back later?"

### Phase 7 — Release safely
- Automate build, test, and deployment where practical.
- Keep configuration separate from source.
- Use staged rollout, feature flags, canaries, or rollback where useful for risk.
- Use backward-compatible schema/API changes when needed.
- Run smoke tests after deployment.
- Verify user-facing behavior and monitor regressions.
- Know how to disable, roll back, or recover from a bad release.

### Phase 8 — Operate and learn
- Observe user-visible latency, errors, traffic, resource saturation, and domain outcomes.
- Create actionable alerts.
- Convert meaningful incidents into tests or design improvements.
- Collect user feedback and inspect real usage.
- Compare outcomes with the original success metric.
- Prioritize the next change based on evidence.

## 2. Engineering concerns every project should consider

Use this as a review map. Not every project needs an elaborate implementation for every category.

### Product and domain
- Problem/user fit, scope, requirements, acceptance criteria, success measures
- Domain model, invariants, data ownership, source of truth
- Usability, accessibility, edge cases, non-goals

### Architecture and interfaces
- Component boundaries, dependencies, API contracts, versioning
- Database schema, migrations, transactions, consistency, concurrency
- Sync/async boundaries, queues/events only when justified
- Simplicity, decision rationale, evolution paths

### Correctness and code health
- Readability, cohesive modules, explicit error handling
- Unit/integration/end-to-end/regression tests
- Reproducible builds, static checks, code review
- Dependency health, compatibility, maintainability

### Security and privacy
- Authentication, authorization, least privilege
- Input validation, injection defenses, safe deserialization
- Secrets handling, sensitive logging, encryption as appropriate
- Threat model, abuse/rate limits, retention/deletion
- Dependency and artifact scanning

### Reliability and performance
- Timeouts, bounded retries, idempotency, partial failures
- Backpressure, capacity limits, recovery/backup needs
- Query plans, indexing, caching, pagination, profiling
- Workload assumptions, load tests, SLOs for critical paths

### Operations and delivery
- Structured logs, metrics, traces, correlation IDs
- CI, deployment automation, environment management
- Health checks, smoke tests, runbooks, alerts
- Rollback/recovery, migration safety, incident learning

### Cost and sustainability
- Hosting, database, network, vendor/API, inference costs
- Quotas, budgets, usage metrics, cost per useful outcome
- Operational burden, service count, resource efficiency

### Documentation and collaboration
- Setup, usage, tests, architecture, APIs, deployment, troubleshooting
- Keep docs accurate and update them with code
- Clear issues, acceptance criteria, small PRs, early blocker communication
- Record important assumptions and limitations

## 3. AI-assisted software engineering workflow

Treat a coding agent as a capable teammate that needs context, bounded work, and independent verification.

### Before implementation
- Read repository instructions and relevant code.
- Ask for a plan before large or ambiguous changes.
- Give the agent the problem, paths/components, constraints, acceptance criteria, and verification commands.
- Define scope and explicit non-goals.
- Require it to identify unknowns rather than inventing facts.
- Separate planning from permission to modify files or perform external actions.

### During implementation
- Give one coherent task at a time.
- Prefer small slices, not "build the entire app."
- Ask the agent to follow established repository patterns.
- Require tests and relevant documentation alongside code.
- Keep humans responsible for product decisions, architecture, privacy, security, and production risk.
- Use persistent repository instructions for durable conventions; don't duplicate the whole plan in every prompt.

### After implementation
- Inspect the full diff.
- Run actual test/build/lint commands.
- Read tests to verify they assert intended behavior.
- Inspect dependencies, secrets, authorization, input validation, and error paths.
- Check for unrelated changes and needless abstractions.
- Verify every claim of success with observed command output.
- Review and approve commits, pushes, deployments, and other external effects according to the workflow.
- Record what changed, checks actually run, results, known gaps, and next action.

### Optional AI repository artifacts
- AGENTS.md: durable repository rules and conventions.
- GOALS.md: outcomes, scope, non-goals, success conditions.
- PLANS.md: high-level roadmap or phases.
- Issue/PR: one bounded change, acceptance criteria, test evidence.
- harness/build/: phase-specific plan for larger projects.
- harness/build-log.md: actual progress and verification evidence.

Do not create all these automatically. Start with a README and issues; add a harness when complexity or repeated agent work justifies it.

## 4. If the product uses LLMs or agents

Treat model behavior as probabilistic software behavior that needs evaluation.
- Define expected behavior and failure boundaries before tuning prompts.
- Create a small initial eval set from requirements, manual checks, and real failures; 20–50 cases can be a useful start, not a universal quota.
- Use deterministic/code-based graders where possible, model-based grading where needed, and human review to calibrate nuanced judgments.
- Verify actual end state, not only the agent's final message.
- Inspect traces/transcripts when evaluations fail.
- Distinguish capability evaluations (what the system can learn to do) from regression evaluations (what it must continue doing).
- Isolate evaluation trials so shared state does not contaminate results.
- Track task success, error modes, latency, token use, and cost.
- Test prompt injection, data leakage, unauthorized tools, unsafe actions, and invalid structured output.
- Enforce authorization in ordinary code, not model instructions alone.
- Re-run evaluations when models, prompts, tools, retrieval, or data change.
- Combine offline evaluations with production monitoring, user feedback, and A/B testing when feasible.

## 5. Practical toolchain

Pick tools that support the workflow. This is not a shopping list.

| Need | Lean default | Alternatives / when to upgrade |
|---|---|---|
| Version control | Git + GitHub | GitLab/Bitbucket if standard |
| Planning | GitHub Issues + README | Linear/Jira for multi-person workflows |
| Editor | VS Code or IntelliJ IDEA for Java | Use whichever makes navigation, tests, and debugging fastest |
| AI coding | One agent: Codex, Claude Code, or IDE agent | Add another only for a distinct strength or independent review |
| Repository instructions | README; AGENTS.md for durable agent context | Phase plans/harness for long-running work |
| Java build | Maven or Gradle | Standardize per repo |
| Tests | JUnit 5 + Mockito where appropriate | Testcontainers for realistic integration boundaries |
| Code quality | Formatter + static analysis + compiler warnings | SonarQube or broader scanning as risk warrants |
| CI | GitHub Actions | GitLab CI, Jenkins, or existing company CI |
| API exploration | OpenAPI + curl/Postman | Contract testing as boundaries grow |
| Local environment | Docker Compose when dependencies need it | Dev containers for repeatable team setup |
| Database | PostgreSQL for relational data by default | NoSQL only when access patterns justify it |
| Observability | Structured logs + basic metrics | OpenTelemetry; Prometheus/Grafana; managed platforms |
| Security | Secret manager + dependency scanning | SAST/DAST and container scanning based on risk |
| Deployment | Simplest managed platform fitting the project | IaC and staged rollout as production needs grow |
| AI evals | Versioned test cases + small evaluation script | OpenAI Evals, Promptfoo, Braintrust, LangSmith, Langfuse, Arize Phoenix depending on stack |
| Product analytics | Small set of outcome metrics | Analytics platform when real usage justifies it |

### Suggested default stack for a solo backend/AI project
- GitHub repository + Issues
- Java + Spring Boot + Maven or Gradle for backend practice
- PostgreSQL if persistence is needed
- JUnit; Testcontainers when database integration needs realistic validation
- GitHub Actions for build/test
- Docker Compose only if it makes dependencies reproducible
- Structured logs and health endpoints
- One AI coding agent, with repository instructions and bounded tasks
- For LLM behavior: versioned eval cases, traces, and explicit cost/latency metrics
- Deploy to a managed service only once the local end-to-end slice is solid

Do not adopt Kubernetes, microservices, Kafka, Redis, vector databases, or multi-agent frameworks by default. Introduce them to solve a measured or clearly specified need.

## 6. What public guidance from strong engineering organizations says

### Google Engineering Practices
Public code review guidance emphasizes design, functionality, complexity, tests, naming, comments, style, and documentation. Small-change guidance explains that focused changes are faster to review, easier to reason about, less risky, easier to merge, and simpler to roll back. Google documentation guidance recommends minimum viable documentation and updating docs with code.

Lesson: small coherent changes, thoughtful review, current documentation.

Sources:
- https://google.github.io/eng-practices/review/
- https://github.com/google/eng-practices/blob/master/review/developer/small-cls.md
- https://google.github.io/styleguide/docguide/best_practices.html

### DORA research
DORA's continuous-delivery guidance identifies version control, CI, automated testing, deployment automation, continuous testing, test data management, database change management, and observability. It emphasizes delivery outcomes and continuous improvement, not tool adoption for its own sake.

Lesson: make the path from change to tested release repeatable and low-risk; shorten feedback loops.

Source:
- https://dora.dev/capabilities/continuous-delivery/

### AWS Well-Architected Framework
AWS organizes workload review around operational excellence, security, reliability, performance efficiency, cost optimization, and sustainability. Its guidance is a set of review questions and trade-offs, not a universal architecture template.

Lesson: review the system across these dimensions, prioritizing based on criticality and context.

Sources:
- https://docs.aws.amazon.com/wellarchitected/2024-06-27/framework/the-pillars-of-the-framework.html
- https://wa.aws.amazon.com/index.en.html

### OpenAI — using Codex in engineering
OpenAI's public guidance describes starting large changes with a plan, using bounded tasks, structuring requests like good GitHub issues, maintaining repository context with AGENTS.md, iteratively improving the agent environment, and using a task queue for secondary ideas.

Lesson: provide context and acceptance criteria, plan ambiguous work before editing, keep tasks manageable, and improve the workflow from observed failures.

Sources:
- https://openai.com/business/guides-and-resources/how-openai-uses-codex/
- https://developers.openai.com/cookbook/examples/codex/iterating-development-workflows-with-codex
- https://learn.chatgpt.com/docs/prompting

### Anthropic — evaluating AI agents
Anthropic's public guidance emphasizes evaluations because agent behavior spans multiple turns, tools, and state changes. It recommends explicit tasks and graders, inspecting transcripts, isolating trials, combining code-based, model-based, and human evaluation, and using regression and capability suites alongside production monitoring and user feedback.

Lesson: for AI products, define success before tuning, verify outcomes rather than trusting final text, and treat evals as living test infrastructure.

Sources:
- https://www.anthropic.com/research/demystifying-evals-for-ai-agents
- https://www.anthropic.com/engineering/building-effective-agents

### Basecamp — Shape Up
Shape Up describes shaping a problem before committing to implementation, using appetite/time boxes, cutting scope, and dividing work into scopes that can be built and finished independently. It is a product-development method, not a universal requirement for every solo project.

Lesson: bound time and scope; finish a meaningful slice rather than letting an idea expand indefinitely.

Source:
- https://basecamp.com/shapeup

## 7. Working definition of done

A feature is done when:
1. The user problem and acceptance criteria are clear.
2. The behavior is implemented in a coherent, reviewable slice.
3. Relevant tests and checks were actually run and results recorded.
4. Security, data integrity, and failure behavior are addressed at the appropriate risk level.
5. Documentation and configuration are sufficient for another person to run and understand it.
6. The change can be released and debugged appropriately for its intended environment.
7. Known limitations and the next improvement are explicit.

A project is not production-ready merely because it runs locally or has a polished UI.

## 8. Builder loop

### Daily
- Pick one concrete deliverable, not a broad topic.
- Read the minimum context needed to start.
- Build or investigate one bounded slice.
- Run a check or experiment that provides evidence.
- Record what changed, what you learned, what failed, and the next action.
- Stop before fatigue pushes you into an all-nighter.

### Weekly
- Ship one reviewable project improvement.
- Review tests, architecture, reliability, security, and cost proportional to the stage.
- Inspect feedback or usage if available.
- Identify one recurring friction point and improve the workflow.
- Update the plan only when evidence justifies a change.

## 9. Core principles
- Build for a real problem, not for a tech-stack résumé.
- Prefer the smallest coherent solution.
- Make changes small, testable, and reversible.
- Keep feedback loops fast.
- Automate repeatable checks.
- Observe real behavior after release.
- Use AI to accelerate execution, not outsource judgment.
- For AI systems, evaluations are a product requirement, not optional polish.
- Scale architecture and process to risk.
- Measure progress through shipped, verified outcomes.

## Research note
This playbook synthesizes public documents and guidance. It does not claim access to private internal playbooks or that all high-performing teams follow an identical process. Tool suggestions are options; choose a small, consistent toolchain and expand only when there is a concrete need.
