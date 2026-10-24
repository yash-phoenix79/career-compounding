# Software Engineering Growth Roadmap

**North star:** Become a strong engineer who can understand systems from first principles, design, build, debug, and operate reliable software, and ship useful AI-powered products. **SDE-2 is the near-term milestone and a side effect of real engineering capability, not the ultimate goal.**

**Do not redesign this roadmap every week.** The full resource catalogue lives in [RESOURCE_LIBRARY.md](RESOURCE_LIBRARY.md).

## Daily operating loop: keep the ball moving

Every day, move both anchors forward:

1. **LLD practice:** Continue the current design exercise. Clarify requirements, model responsibilities, implement in Java, test, and record trade-offs.
2. **Backend from First Principles:** Study the next relevant concept from https://backend-from-first-principle.vercel.app/ and connect it to code, a small experiment, or a concise explanation.
3. **Evidence:** Record what you actually produced in `PROGRESS.md`. Reading/watching alone does not count as completion.

**Default session:** 60 minutes total; maximum planned learning time 90 minutes. Split the time between LLD and backend based on the task. On a rough day, do 15 minutes and write the next action. Preserve continuity, not perfection.

## Current task

The current LLD task remains the library management system:
- Write 5–8 core use cases.
- Record assumptions and out-of-scope behavior.
- Identify entities, value objects, services, and responsibilities.
- Draw a class diagram.
- Implement the core flows in Java.
- Add unit tests and explain trade-offs in `design.md`.

Backend learning should continue alongside this task. For each concept, capture:
- What problem does it solve?
- What happens under the hood?
- What small experiment or code can demonstrate it?
- What failure mode or trade-off matters?

## Focus order

1. **LLD and implementation craft** — object modeling, responsibilities, interfaces, SOLID, patterns, testability, machine coding.
2. **Backend fundamentals** — HTTP, networking, APIs, Java backend, databases, testing, and production basics.
3. **SDE-2 readiness** — DSA, LLD/machine coding, HLD, project deep dives, behavioural stories, and communication.
4. **HLD and distributed systems** — capacity, caching, queues, consistency, reliability, observability.
5. **AI engineering and agentic systems** — model APIs, structured outputs, tools, retrieval, evaluation, state, safety, tracing, cost and latency.
6. **Products and public proof** — build real slices, document decisions, ship demos, share useful lessons.

These are not simultaneous tracks. LLD and backend are the current daily anchors. DSA is a deliberate supporting interview workstream. Expand into deeper HLD, distributed systems, and AI engineering as the fundamentals and schedule allow.

## Engineering at work

Treat the Amazon role as part of the training ground:
- Investigate issues deeply and validate assumptions.
- Ask questions and surface blockers early.
- Communicate status, risks, and decisions clearly.
- Own outcomes end to end and verify fixes.
- Learn from production behaviour, reviews, incidents, and trade-offs.

## Weekly review

At least one hour on the weekend:
1. Finish or improve a concrete artifact.
2. Run tests or demonstrate behavior.
3. Update `PROGRESS.md` honestly.
4. Write one short lesson that could become a public post.
5. Choose exactly one next task.

## Non-negotiable rules

- No roadmap redesign every week.
- No resource collecting instead of practice.
- No starting another project whenever the current one becomes difficult.
- No treating AI-generated code as understood code.
- No sacrificing sleep to compensate for a missed session.
- If a day is missed, resume with the next small task.
- Keep one main project active at a time.
- Every week should leave visible evidence of engineering progress.

## Full resource shelf

See [RESOURCE_LIBRARY.md](RESOURCE_LIBRARY.md) for the complete resource library across DSA, LLD, backend, CS fundamentals, HLD, distributed systems, AI engineering, real-world projects, open source, engineering judgment, books, interviews, and public presence.
