# Software Engineering Growth Roadmap

**North star:** Become a strong software engineer who can design, build, evaluate, and ship reliable AI-powered products.

**Operating rule:** Learn by producing artifacts. Every session must leave evidence in this repository or in the linked project being built. Do not redesign the roadmap every week.

## The loop

Study one concept → design a solution → implement a small slice → test it → ask AI to critique it → write down the trade-off → share a useful lesson when appropriate.

## Focus order

1. **LLD and implementation craft** — object modeling, responsibilities, interfaces, SOLID, patterns, testability, machine coding.
2. **HLD and distributed systems** — requirements, APIs, data models, capacity, caching, queues, consistency, reliability, observability.
3. **AI engineering** — model APIs, structured outputs, tool use, retrieval, evaluations, safety, tracing, cost and latency.
4. **Agentic systems** — bounded workflows, state, tools, permissions, retries, checkpoints, human approval, evals and observability.
5. **Products and public proof** — build real slices, document decisions, ship demos, share learnings.

These are not five simultaneous tracks. Finish a focused LLD pass first, then move into HLD while continuing to apply LLD in code. Introduce AI engineering after you can build and test a normal backend service. Add agentic behavior only where a workflow benefits from it.

## Daily operating contract

- Default session: **60 minutes**. Maximum planned learning time: **90 minutes**.
- On a rough workday: do 15 minutes and record the next step. Preserve continuity, not perfection.
- One active learning task at a time.
- One main project at a time. Use design exercises as small folders in this repository; later apply the strongest ones to a product.
- Do not count videos watched or pages read as completion. Count designs, tests, implementations, explanations and shipped slices.
- Protect sleep and job delivery. This plan must survive a normal working week.

## Phase 1: LLD foundations (Weeks 1–4)

### Week 1 — Object modeling
- [ ] Requirements and use cases for a library management system
- [ ] Identify entities, value objects, services and responsibilities
- [ ] Draw a class diagram
- [ ] Implement core flows in Java
- [ ] Add unit tests and explain the design in `design.md`

### Week 2 — SOLID and changeability
- [ ] Learn SOLID through code examples
- [ ] Refactor the library system around one changing requirement
- [ ] Compare composition with inheritance
- [ ] Document one over-abstraction you avoided

### Week 3 — Patterns as tools
- [ ] Implement Strategy and Factory in small examples
- [ ] Implement Observer or State where it naturally fits
- [ ] Explain the problem each pattern solves and its cost
- [ ] Avoid using patterns just to demonstrate patterns

### Week 4 — Machine coding
- [ ] Design and implement a parking lot or notification service
- [ ] Include validation, error cases and tests
- [ ] Complete a timed 2-hour implementation
- [ ] Write a short design-review retrospective

**LLD exit test:** Given an unfamiliar problem, independently clarify requirements, identify responsibilities, sketch a defensible design, implement the core behavior, test it, and explain trade-offs.

## Phase 2: HLD foundations (Weeks 5–8)

- [ ] Requirements and API design: URL shortener
- [ ] Data modeling, indexes and caching: rate limiter
- [ ] Queues and asynchronous work: notification service
- [ ] Scaling, consistency, failures and observability: social feed
- [ ] Write one complete design document with assumptions, diagrams, data flows, failure modes and trade-offs

**HLD exit test:** Explain the design, estimate rough scale, identify bottlenecks and failure modes, and justify alternatives without reciting a memorized architecture.

## Phase 3: AI engineering (Weeks 9–10)

- [ ] Call a model API from a backend service
- [ ] Validate structured output and handle failures
- [ ] Add tool/function calling with a narrow schema
- [ ] Create a small evaluation set with expected outcomes
- [ ] Measure quality, latency and cost
- [ ] Add tracing and explicit handling for untrusted model output

**Exit test:** A working feature with tests or evaluations, failure handling, and a short report on quality, latency and cost.

## Phase 4: Agentic systems (Weeks 11–12)

- [ ] Define one bounded multi-step workflow
- [ ] Give the agent only the tools it needs
- [ ] Add explicit state and step limits
- [ ] Add retries, timeouts and idempotency where relevant
- [ ] Require approval for consequential external actions
- [ ] Add traces and evaluations for success, failure and tool misuse
- [ ] Document when a deterministic workflow is better than an agent

**Exit test:** A small agentic workflow that is observable, testable, bounded and safe to interrupt.

## Reference shelf

Use these as references, not as a queue to consume all at once.

- LLD: https://github.com/ashishps1/awesome-low-level-design
- Java patterns: https://github.com/iluwatar/java-design-patterns
- HLD: https://github.com/donnemartin/system-design-primer
- Backend practice: https://spring.io/guides
- Distributed systems practice: https://github.com/jepsen-io/maelstrom
- AI engineering: https://github.com/anthropics/anthropic-cookbook
- Agent workflows: https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/

## Weekly review

Every weekend, spend at least one hour:
1. Finish or improve a concrete artifact.
2. Run tests or demonstrate the behavior.
3. Update `PROGRESS.md`.
4. Write one short lesson that could become a public post.
5. Choose exactly one next task.

Do not add a new project until the current project has a working slice or a clearly documented reason to pause.
