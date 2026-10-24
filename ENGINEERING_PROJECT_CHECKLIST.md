# Engineering Checklist for Building Solid Projects

Use this as a risk-based checklist, not a requirement to build every component for every project. Start simple; add complexity only when requirements, scale, risk, or evidence justify it.

## 1. Problem and users
- [ ] Define the problem, target users, and why it matters.
- [ ] Identify the core user journeys and highest-value use case.
- [ ] Write functional requirements and explicit non-goals.
- [ ] Define measurable success criteria and how they will be measured.
- [ ] Capture constraints: timeline, budget, team, platform, privacy, regulation, dependencies.
- [ ] Validate assumptions with users, data, or a small prototype.

## 2. Scope and product decisions
- [ ] Define a small, end-to-end MVP.
- [ ] Prioritize must-have vs. later features.
- [ ] Specify acceptance criteria and edge cases.
- [ ] Decide what failure or degraded behavior users should see.
- [ ] Identify accessibility, localization, and usability needs where relevant.

## 3. Domain and data
- [ ] Identify domain concepts, entities, value objects, and invariants.
- [ ] Define ownership of data and source of truth.
- [ ] Design schema, relationships, constraints, indexes, and migrations.
- [ ] Define validation, nullability, units, timestamps, and time-zone behavior.
- [ ] Plan data lifecycle: creation, updates, retention, deletion, export, backup.
- [ ] Decide consistency, transactions, idempotency, and concurrency rules.
- [ ] Consider data quality, provenance, and audit history when relevant.

## 4. Architecture and design
- [ ] Draw the simplest useful system/context diagram.
- [ ] Define components, responsibilities, boundaries, and dependency direction.
- [ ] Define APIs/contracts, request/response shapes, errors, and versioning.
- [ ] Choose sync vs. async communication and event boundaries where needed.
- [ ] Evaluate alternatives and record important decisions/trade-offs (ADRs).
- [ ] Keep the design as simple as possible; avoid speculative abstractions.
- [ ] Identify external dependencies and their failure modes.
- [ ] Consider extensibility only around likely points of change.

## 5. Implementation and code quality
- [ ] Use clear naming, cohesive modules, and small understandable functions.
- [ ] Separate business rules from infrastructure/UI where useful.
- [ ] Handle errors explicitly; avoid swallowed exceptions and ambiguous states.
- [ ] Validate inputs at trust boundaries.
- [ ] Use types/contracts to make invalid states harder to represent.
- [ ] Manage configuration and secrets outside source code.
- [ ] Follow language/framework conventions and pin/manage dependencies.
- [ ] Review generated code rather than trusting it blindly.
- [ ] Refactor when it improves clarity, correctness, or changeability.

## 6. Testing and verification
- [ ] Unit-test domain logic and important edge cases.
- [ ] Integration-test databases, queues, APIs, and external boundaries.
- [ ] Add end-to-end tests for critical user journeys.
- [ ] Test failure paths, retries, timeouts, duplicates, and partial failures.
- [ ] Test authorization, validation, concurrency, and data integrity.
- [ ] Use deterministic fixtures; isolate tests from production data/services.
- [ ] Add regression tests for every fixed bug.
- [ ] Set quality gates based on risk; coverage percentage alone is not proof of quality.
- [ ] Verify manually with a repeatable test/demo when appropriate.

## 7. Security and privacy
- [ ] Threat-model assets, trust boundaries, attackers, and likely abuse cases.
- [ ] Authenticate identities and authorize every sensitive action.
- [ ] Apply least privilege and secure defaults.
- [ ] Protect secrets, tokens, personal data, and sensitive logs.
- [ ] Validate/sanitize untrusted input; defend against injection and unsafe deserialization.
- [ ] Use TLS and appropriate encryption at rest.
- [ ] Add rate limits, quotas, abuse detection, and resource limits where relevant.
- [ ] Keep dependencies patched; scan dependencies and artifacts.
- [ ] Define retention/deletion and consent requirements.
- [ ] Test security controls; do not rely on a UI hiding sensitive operations.

## 8. Reliability and resilience
- [ ] Define expected behavior when dependencies are slow, unavailable, or incorrect.
- [ ] Set timeouts; use bounded retries with backoff and jitter where appropriate.
- [ ] Make retryable operations idempotent.
- [ ] Use circuit breakers, bulkheads, queues, or graceful degradation only when justified.
- [ ] Prevent duplicate work and handle race conditions.
- [ ] Define recovery, backup, restore, and disaster-recovery needs.
- [ ] Consider capacity limits, backpressure, and overload behavior.
- [ ] Set SLOs or practical reliability targets for user-critical paths.

## 9. Performance and scale
- [ ] Establish a baseline and realistic workload assumptions.
- [ ] Measure before optimizing; profile actual bottlenecks.
- [ ] Review algorithmic complexity, query plans, indexes, and N+1 calls.
- [ ] Define caching strategy, invalidation, TTLs, and stale-data behavior.
- [ ] Consider pagination, batching, streaming, and payload sizes.
- [ ] Load-test important paths and define resource limits.
- [ ] Identify scaling bottlenecks and the evidence that would justify scaling out.
- [ ] Avoid distributed systems complexity before it is needed.

## 10. Observability and operations
- [ ] Use structured, useful logs with correlation/request IDs.
- [ ] Capture metrics for traffic, errors, latency, saturation, and domain outcomes.
- [ ] Trace requests across components when complexity warrants it.
- [ ] Build dashboards and alerts around actionable symptoms/SLOs.
- [ ] Redact secrets and sensitive information from telemetry.
- [ ] Add health/readiness checks and safe diagnostic endpoints.
- [ ] Document common failure modes and debugging steps.
- [ ] Define who responds to incidents and how issues are communicated.

## 11. Delivery and DevEx
- [ ] Keep the repository understandable: README, clear structure, license if appropriate.
- [ ] Provide reproducible local setup and sample/environment configuration.
- [ ] Automate formatting, linting, tests, and static/security checks in CI.
- [ ] Build artifacts reproducibly and manage dependency versions.
- [ ] Separate development, staging, and production configuration/data.
- [ ] Use safe migrations and backward-compatible rollout strategies.
- [ ] Support rollback or roll-forward recovery.
- [ ] Use feature flags only when they solve a real rollout problem.
- [ ] Make the build and deployment process repeatable.

## 12. Deployment and maintenance
- [ ] Choose hosting/runtime based on workload, operational burden, and cost.
- [ ] Configure secrets, permissions, networking, TLS, and environment settings.
- [ ] Verify deployment with smoke tests and post-deploy checks.
- [ ] Define backup schedules and test restoration when data matters.
- [ ] Plan dependency upgrades, patching, and deprecation.
- [ ] Track known issues, technical debt, ownership, and next maintenance actions.
- [ ] Have a way to disable a broken feature or recover from a bad release.

## 13. Cost and sustainability
- [ ] Estimate infrastructure, storage, network, third-party API, and AI inference costs.
- [ ] Set budgets, quotas, and alerts for variable-cost services.
- [ ] Measure cost per request, task, user, or business outcome where useful.
- [ ] Consider operational burden and team capacity, not only cloud price.
- [ ] Avoid premature optimization, unnecessary services, and unused infrastructure.

## 14. Documentation and communication
- [ ] README: what it does, why, prerequisites, setup, usage, tests, deployment.
- [ ] Architecture diagram and key design decisions.
- [ ] API/schema documentation and example requests.
- [ ] Runbook: deploy, debug, recover, rollback.
- [ ] Record assumptions, limitations, risks, and known failure modes.
- [ ] Document meaningful changes and communicate blockers early.
- [ ] Keep documentation close to the code and update it as behavior changes.

## 15. AI-assisted engineering (applies to all projects)
- [ ] Use AI to accelerate exploration, implementation, tests, and reviews—not as an authority.
- [ ] Write down requirements and acceptance criteria before asking AI to implement.
- [ ] Give AI bounded tasks, relevant context, constraints, and repository conventions.
- [ ] Inspect every diff; understand code, dependencies, security, and failure behavior.
- [ ] Run tests, static checks, and targeted experiments; never accept claims of tests passing without evidence.
- [ ] Verify API/library facts against current official docs when consequential.
- [ ] Watch for hallucinated APIs, overengineering, hidden assumptions, and unneeded dependencies.
- [ ] Never paste credentials, private data, or confidential company code into unapproved tools.
- [ ] Keep human ownership of architecture, correctness, review, and production decisions.
- [ ] Track AI-generated changes and validate them like any other code.

## 16. Additional checklist when the project itself uses AI/LLMs
- [ ] Decide whether an LLM is needed; compare deterministic code, search, and simpler baselines.
- [ ] Define task boundaries, user expectations, and what the system must never do.
- [ ] Select model(s) based on quality, latency, privacy, availability, and total cost.
- [ ] Version prompts, model configuration, tools, and datasets.
- [ ] Design retrieval/data grounding and source attribution when using RAG.
- [ ] Validate tool inputs/outputs and enforce authorization outside the model.
- [ ] Treat retrieved content and user input as untrusted; defend against prompt injection.
- [ ] Require confirmation for consequential or irreversible actions.
- [ ] Add structured output validation, fallbacks, timeouts, and bounded retries.
- [ ] Build an evaluation dataset and task-specific quality metrics before optimizing.
- [ ] Evaluate correctness, hallucination, robustness, safety, and regressions.
- [ ] Test adversarial inputs, refusal behavior, data leakage, and tool misuse.
- [ ] Trace model calls, tool calls, retrieval, token usage, latency, errors, and cost.
- [ ] Use human review or escalation for high-impact/low-confidence cases.
- [ ] Decide what to store, for how long, and how users can inspect/delete their data.
- [ ] Re-evaluate quality and cost whenever models, prompts, tools, or data change.

## 17. Launch readiness and feedback
- [ ] Critical user journey works end-to-end in a production-like environment.
- [ ] Critical tests and security checks pass.
- [ ] Known risks, limitations, and failure modes are documented.
- [ ] Monitoring, alerts, support/feedback path, and rollback/recovery are ready.
- [ ] Success metrics have baselines and owners.
- [ ] Collect user feedback and production evidence.
- [ ] Prioritize the next iteration from observed failures and usage—not guesses.

## A practical definition of done
A project slice is done when:
1. It solves a defined user problem and meets acceptance criteria.
2. Its important success and failure paths are tested.
3. Security, data integrity, and error behavior are considered for its risk level.
4. It can be built, configured, deployed, and debugged repeatably.
5. Its limitations and important trade-offs are understood.
6. There is evidence: tests, a demo, metrics, or a reviewable commit.

## Keep the process lightweight
For a small learning project, document the problem, MVP, design, tests, README, and basic security/error handling. For a production or AI system, expand the checklist according to data sensitivity, impact, reliability needs, and cost. The goal is sound engineering judgment—not maximum ceremony.
