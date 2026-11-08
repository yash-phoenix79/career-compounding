# Learning Methodology

This is the standard applied to every backend concept. It is deliberately language-agnostic and designed to build transferable engineering judgment.

## A. The foundational questions

Answer these in your own words. Not every question needs equal depth for every topic; use judgment and go deeper where the concept warrants it.

### 1. Problem and motivation
1. What concrete problem necessitated this concept?
2. Who or what experiences that problem?
3. What constraints existed before this solution?
4. What happens if we do nothing?
5. What were the simpler alternatives, and why were they insufficient?

### 2. First principles and mental model
6. What are the irreducible primitives involved? (bytes, memory, CPU, disk, processes, threads, clocks, state, messages, etc.)
7. How would we solve the problem without this abstraction?
8. What assumptions does the solution make about the world?
9. What is the simplest mental model that predicts its behavior?
10. Which concepts must be understood first?

### 3. Internals and mechanics
11. What happens step by step, from input to output?
12. What state exists, where does it live, and who owns it?
13. What happens at the boundaries: process, machine, network, storage, or trust boundary?
14. Which algorithms, data structures, protocols, OS primitives, or storage mechanisms are involved?
15. What is synchronous, asynchronous, blocking, non-blocking, durable, or ephemeral here?
16. Can we trace the actual bytes, calls, state transitions, or disk/network operations?

### 4. Invariants and correctness
17. What must always be true for the system to be correct?
18. What guarantees does the abstraction provide—and explicitly not provide?
19. What ordering, consistency, atomicity, isolation, or delivery properties matter?
20. How would we prove or test those guarantees?

### 5. Failure modes and adversarial thinking
21. What can fail, at which boundary, and how is failure observed?
22. What happens under timeout, retry, duplicate input, partial success, process crash, network partition, overload, or stale data?
23. Can the system lose, duplicate, reorder, corrupt, expose, or indefinitely delay work/data?
24. What happens during recovery and restart?
25. How could a malicious or buggy client exploit the design?

### 6. Trade-offs and alternatives
26. What do we gain and sacrifice?
27. What are the costs in latency, throughput, memory, CPU, storage, complexity, operability, and money?
28. What alternatives exist, and when are they better?
29. What assumptions would make this choice wrong?
30. What is the simplest adequate solution at the current scale?

### 7. Production usage
31. Where does this appear in a real system?
32. What signals would tell us it is unhealthy? Which logs, metrics, traces, dashboards, or alerts matter?
33. How do we deploy, configure, secure, migrate, roll back, and operate it?
34. How does behavior change as load, data, tenants, or failure rates increase?
35. What operational runbook or recovery action would an on-call engineer need?

### 8. Implementation and verification
36. Can I implement a minimal version without copying a tutorial?
37. Can I use the real tool/library and explain what it abstracts?
38. What tests cover normal behavior, boundaries, concurrency, and failure?
39. Can I reproduce and debug a failure deliberately?
40. What evidence proves the implementation behaves as claimed?

### 9. Engineering judgment and transfer
41. When should I use this, and when should I not?
42. What signals tell me this abstraction is premature or unnecessary?
43. Which principles transfer to another language, framework, database, or infrastructure?
44. If the tool disappeared tomorrow, which underlying ideas would remain?
45. Can I explain the concept to another engineer, defend a design choice, and revise my view when evidence changes?

## B. The three-phase grilling protocol

### Phase 1 — Story & Philosophy: explain the system
I will challenge you to:
- Explain the problem before naming the technology.
- Draw the flow and identify the components and boundaries.
- Derive the mechanism from primitives.
- Predict behavior for unfamiliar inputs and edge cases.
- Compare alternatives and state guarantees precisely.
- Explain what is abstracted by a framework/runtime/library.

**Pass condition:** You can reconstruct and reason about the concept without relying on memorized definitions.

### Phase 2 — Implementation: prove you can build it
I will challenge you to:
- Implement a minimal version or focused slice.
- Explain each important line and dependency.
- Inspect actual requests, bytes, queries, state, or execution behavior.
- Write tests, including edge cases and failure cases.
- Debug a deliberately introduced bug.
- Reimplement the core idea in a second language only when that comparison adds real learning value.

**Pass condition:** You can build, test, and debug the essential behavior independently.

### Phase 3 — Production: make it survive reality
I will challenge you to:
- Design the concept into a larger system.
- Handle overload, partial failure, retries, duplicates, timeouts, security, and recovery where relevant.
- Define observability and operational responses.
- Evaluate scale, cost, consistency, and maintainability trade-offs.
- Review a flawed design and improve it.
- Defend your decisions under changing requirements.

**Pass condition:** You can make and defend a practical design, identify its limits, and explain how to operate it.

## C. Mastery rubric

Use this rubric per concept. Watching or reading is exposure, not mastery.

| Level | Evidence |
|---|---|
| 0 — Unseen | Have not studied it. |
| 1 — Familiar | Can recognize terms and summarize the source. |
| 2 — Explain | Can explain the problem, mental model, and core mechanics without notes. |
| 3 — Apply | Can implement a focused version and test normal and edge behavior. |
| 4 — Diagnose | Can reproduce failures, debug them, and explain guarantees and limitations. |
| 5 — Design | Can choose among alternatives and defend trade-offs in a realistic system. |
| 6 — Transfer | Can apply the underlying principles in a different language, stack, or unfamiliar scenario. |

Record the level honestly and link evidence. A level can differ by dimension: conceptual understanding may be strong while implementation remains weak.

## D. How a learning session should run

1. **Source extraction:** What does the video/chapter actually teach? Preserve its terminology and scope.
2. **Concept model:** Explain it from first principles. Separate source claims from additional context.
3. **Interactive grilling:** Ask one question at a time. Wait for my answer; do not reveal the full solution immediately.
4. **Correction:** Identify what is correct, incomplete, hand-wavy, or wrong. Explain why.
5. **Implementation challenge:** Give a small task with observable acceptance criteria.
6. **Production scenario:** Introduce a realistic failure or scaling constraint.
7. **Closure:** Summarize durable understanding, remaining gaps, evidence, and one next action.

Do not dump 45 questions on me at once. Select the highest-value questions for the concept and increase difficulty progressively.

## E. Standards for honest learning

- Distinguish **source-derived facts**, **well-established external facts**, and **our own design choices/inferences**.
- If the source skips a mechanism, say so; then fill the gap explicitly as an additional deep dive.
- Do not invent what a video or chapter says.
- Correct inaccuracies rather than preserving them for consistency.
- Prefer a small verified experiment over an impressive but untested explanation.
- Optimize for durable mental models, not note volume.
