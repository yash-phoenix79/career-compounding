# Software Engineering Growth Roadmap

**North star:** Become an exceptional engineer who understands systems from first principles, designs and builds reliable software, investigates failures, and ships useful AI-powered products. **SDE-2 is the near-term milestone and a side effect of real engineering capability, not the ultimate goal.**

**LOCKED operating contract:** The non-negotiables below are fixed. Do not renegotiate them, redesign the roadmap, or replace execution with resource hunting. Change this contract only if the user explicitly asks to revise it.

## Four non-negotiables

### Every day
1. **Backend from First Principles** — learn the next concept and connect it to a concrete example, experiment, or concise explanation.
2. **LLD practice** — move the current design exercise forward: requirements, object model, implementation, tests, or trade-offs.
3. **AI knowledge** — learn one small AI-engineering concept from AI Engineering from Scratch or the reference shelf, and capture a practical takeaway. Keep this deliberately small on workdays; do not start a separate project just to satisfy it.

### Every weekend
4. **Project contribution** — make a tangible contribution to one active project: implement a feature slice, fix a bug, add tests, improve reliability, document a design decision, or make a meaningful open-source contribution. Prefer the existing active project. Do not start a new project to avoid finishing the current one.

## Time and evidence rules

- Aim for **60 minutes total on a normal day**, with a **90-minute maximum planned learning time**. Split the session across the three daily non-negotiables; small focused increments count when they produce evidence.
- On a difficult day, preserve the contract with a small minimum: 5–15 focused minutes per daily area, or a concrete note and next action if energy is very low. Do not use this as a reason to abandon the routine.
- Weekend project contribution gets a dedicated block; it should produce a commit, tested change, or other reviewable artifact.
- Record actual evidence in `PROGRESS.md`. Passive reading or watching alone is not completion.
- Protect sleep and job delivery. Never use an all-nighter to compensate for a missed session.

## Current LLD task

The current task remains the library management system:
- Write 5–8 core use cases.
- Record assumptions and out-of-scope behavior.
- Identify entities, value objects, services, and responsibilities.
- Draw a class diagram.
- Implement core flows in Java.
- Add unit tests and explain trade-offs in `design.md`.

## Current daily resource anchors

- Backend: https://backend-from-first-principle.vercel.app/
- AI engineering: https://aiengineeringfromscratch.com/
- LLD: current exercise plus the LLD references in [RESOURCE_LIBRARY.md](RESOURCE_LIBRARY.md).

## Focus order

1. **Daily craft:** LLD + backend fundamentals + AI knowledge.
2. **SDE-2 readiness:** DSA, LLD/machine coding, HLD, project deep dives, behavioural stories, and communication. Keep DSA practice scheduled as a supporting interview workstream; do not silently drop it.
3. **HLD and distributed systems:** capacity, caching, queues, consistency, reliability, observability.
4. **AI engineering and agentic systems:** model APIs, structured outputs, tools, retrieval, evaluation, state, safety, tracing, cost and latency.
5. **Products and public proof:** contribute to and finish real project slices, document decisions, ship demos, and share useful lessons.

These are not all separate daily tracks. The three daily non-negotiables stay fixed; go deeper on one topic at a time.

## Engineering at work

Treat the Amazon role as part of the training ground:
- Investigate issues deeply and validate assumptions.
- Ask questions and surface blockers early.
- Communicate status, risks, and decisions clearly.
- Own outcomes end to end and verify fixes.
- Learn from production behaviour, reviews, incidents, and trade-offs.

## Weekly review

Every weekend:
1. Complete the project contribution.
2. Run tests or demonstrate behavior.
3. Update `PROGRESS.md` honestly.
4. Review what improved in backend, LLD, and AI knowledge.
5. Write one short lesson that could become a public post.
6. Choose exactly one next implementation task.

## Non-negotiable rules

- Daily: backend fundamentals, LLD practice, AI knowledge.
- Every weekend: a tangible project contribution.
- No roadmap redesign every week.
- No resource collecting instead of practice.
- No starting another project whenever the current one becomes difficult.
- No treating AI-generated code as understood code.
- No sacrificing sleep to compensate for a missed session.
- If a day is missed, resume with the next small task.
- Keep one main project active at a time.
- Every week must leave visible evidence of engineering progress.

## Full resource shelf

See [RESOURCE_LIBRARY.md](RESOURCE_LIBRARY.md) for the consolidated library across DSA, LLD, backend, CS fundamentals, HLD, distributed systems, AI engineering, projects, open source, engineering judgment, books, interviews, and public presence.
