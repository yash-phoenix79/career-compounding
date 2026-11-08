# Backend Engineering — Learning Plan and Operating Agreement

**Status:** Locked operating methodology; revise only when evidence shows a better approach.
**North star:** Develop SDE-3-capable engineering depth while making SDE-2 the next practical career milestone. Build capability through demonstrated execution, ownership, technical judgment, and impact—not title-chasing.

## Engineering philosophy

> Don't collect technologies. Build mental models.
>
> Don't memorize architecture diagrams. Understand the forces that produced them.
>
> Don't just write code that works. Understand why it works, when it stops working, and how to prove it.

The aim is to become an AI-native engineer with strong computer science and software engineering fundamentals, backend and distributed-systems depth, production ownership, design judgment, and increasing technical influence.

SDE-2 and SDE-3 descriptions are capability targets, not promises of promotion. Promotions also depend on scope, sustained impact, communication, ownership, and the organization's leveling expectations.

## Why first-principles learning compounds

The introductory lesson makes a practical claim: understanding backend fundamentals creates skills that transfer across codebases, languages, frameworks, projects, and teams. The seven benefits below are source-derived themes, translated into concrete behaviors for this program.

| Benefit | What it means in practice | How we will deliberately use it |
|---|---|---|
| Understand unfamiliar codebases | Recognize recurring system parts and trace behavior without being overwhelmed by repository structure. | For each unfamiliar code path, map entry point, routing, middleware, business logic, data access, dependencies, and failure boundaries before editing. |
| Faster onboarding | Apply existing mental models of HTTP, APIs, persistence, auth, and request flow in a new stack. | Learn the concept once; then identify how the current language/framework expresses it. Read framework documentation for implementation details, not to rediscover the underlying problem. |
| Build projects faster | Make architecture and implementation decisions from requirements rather than blindly following tutorials. | Start projects by stating requirements, constraints, data flow, contracts, and failure cases; then build the smallest coherent slice. |
| Reduce syntax fatigue | Separate the problem being solved from the syntax used by a particular language. | When entering a new language, learn enough syntax to implement one known backend concept. Avoid studying language features without a concrete engineering use. |
| Choose the right tools | Select tools based on workload and constraints rather than identity or familiarity with a stack. | Compare candidates against explicit requirements such as data model, consistency, latency, throughput, concurrency, operational cost, and team capability. |
| Become more employable | Contribute across unfamiliar environments because fundamentals and judgment are portable. | Build evidence of independent debugging, implementation, design reasoning, and effective onboarding across systems—not just a list of technologies. |
| Develop engineering intuition | Recognize recurring patterns and predict where behavior or failures are likely to originate. | Repeatedly trace real execution paths, inspect production-style behavior, test hypotheses, and record patterns that transfer to other systems. |

**Important distinction:** These are benefits to develop, not guaranteed outcomes. First-principles knowledge accelerates reasoning, but does not replace language fluency, repository familiarity, testing, collaboration, or production experience.

### The transfer test

At the end of a meaningful topic, ask:

1. What principle did I learn that is independent of this specific language or framework?
2. Where else would the same principle appear?
3. If the framework/library disappeared, what underlying mechanism would I still understand?
4. Could I recognize and apply this principle in an unfamiliar codebase?
5. What evidence demonstrates that I can transfer it—not merely describe it?

Use this test in daily logs and weekly reviews. This is how we make transfer explicit rather than assuming it happens automatically.

## The QDD learning cycle

Every substantial concept follows:

1. **Question — identify the problem.** Why does this exist? What problem does it solve? What happens without it?
2. **Understand — derive the mental model.** Identify primitives, assumptions, internals, state ownership, boundaries, invariants, and guarantees.
3. **Build — implement it.** Create a minimal working version or focused experiment; explain the important code and dependencies.
4. **Break — challenge it.** Exercise edge cases, concurrency, timeouts, retries, duplicate inputs, partial failure, crashes, overload, and recovery as relevant.
5. **Design — exercise judgment.** Compare alternatives, trade-offs, operating costs, security, scale, and when not to use the abstraction.
6. **Prove — produce evidence.** Tests, reproducible experiments, benchmarks, debugging notes, code, and an explanation without notes.

Not every question applies equally to every topic. Choose depth based on the concept and its consequences.

## Question-driven development protocol

Use the question bank in [METHODOLOGY.md](METHODOLOGY.md). The recurring dimensions are:

- Problem and motivation
- Fundamentals and mental models
- Internals and execution flow
- State, boundaries, invariants, and guarantees
- Failure modes and recovery
- Alternatives and trade-offs
- Independent implementation and verification
- Production operation, security, and observability
- Engineering judgment and transfer to unfamiliar problems

**Interaction contract:**
- Ask one meaningful question at a time.
- Let the learner attempt an answer before revealing the solution.
- Probe assumptions and ask for concrete reasoning.
- Give hints when stuck; then explain precisely and correct misconceptions.
- Increase difficulty progressively.
- Do not turn every session into a lecture or dump the entire question bank.
- A video watched or note written is not proof of mastery.

## Three learning phases

1. **Story & Philosophy:** language-agnostic understanding of problems, primitives, protocols, components, boundaries, and design forces.
2. **Implementation:** turn principles into working code. Prioritize Java for direct career transfer; use Go, Python, or TypeScript selectively when the source or experiment makes the comparison valuable.
3. **Production:** integrate components into systems with reliability, security, observability, performance, testing, deployment, maintainability, and operational practices.

The written [27-chapter reference](https://backend-from-first-principle.vercel.app/) and the [video learning journey](https://www.youtube.com/watch?v=6Ss4dJD9Kzg&list=PLui3EUkuMTPgZcV0QhQrOcwMPcBCcd_Q1&index=3) are complementary, not identical. Ground lesson-specific claims in the actual source material.

## 90-day first execution block

This is a direction-setting plan, not a promise to finish every topic on schedule. Revisit prerequisites and adjust pace to demonstrated understanding.

| Period | Focus | Evidence to produce |
|---|---|---|
| Days 1–30 | Request lifecycle, client/server model, networking and HTTP, routing, APIs, Java fundamentals | A working HTTP server/API, tests, and a clear request-flow explanation |
| Days 31–60 | Persistence, SQL and transactions, caching, queues, concurrency | Focused backend components plus failure and correctness experiments |
| Days 61–90 | Reliability, observability, security, performance, distributed-systems foundations | An integrated backend project, design decisions, tests, and operational notes |

The 27-chapter curriculum remains the source map. This 90-day block prioritizes foundations and evidence rather than rushing through chapter counts.

## Daily practice

Target: **90 focused minutes** when feasible.

| Activity | Time |
|---|---:|
| Learn and investigate one coherent concept | 20 min |
| Question-driven grilling and recall | 15 min |
| Hands-on implementation | 35 min |
| Failure experiment or debugging | 10 min |
| Documentation and next action | 10 min |
| **Total** | **90 min** |

On difficult days, use a 20-minute minimum: understand one idea, answer one meaningful question, and make one small experiment or code change. Consistency matters more than perfect adherence to the time split.

### Daily learning log: non-negotiable record

Every learning day gets a dated entry based on [templates/DAILY-LEARNING-LOG.md](templates/DAILY-LEARNING-LOG.md). Keep it honest and concise; a short entry with real evidence is better than a polished page of claims.

Each log must capture:
- Date, topic, phase, and exact source/scope.
- What was learned, separating source claims from additional explanations.
- The learner's own explanation and the questions challenged.
- What was implemented, tested, inspected, or debugged; link evidence where possible.
- One principle that transfers beyond the current language/framework/topic.
- Remaining gaps, a truthful mastery assessment, and exactly one next action.

At session close, update [PROGRESS.md](PROGRESS.md) with the current topic, evidence, gaps, and next action. Use a commit message that states the intent and outcome, for example: `docs(backend): record request lifecycle learning and transfer principle`. Do not claim implementation or mastery without evidence.

## Weekly and monthly evidence

- **Weekly:** produce at least one meaningful artifact: implementation, test suite, experiment, debugging investigation, technical explanation, or design note.
- **Weekly:** connect a concept to a real work problem when appropriate, while respecting employer confidentiality.
- **Monthly:** assess capability, identify gaps, and select the next deliberate practice target.
- Keep no more than a few active implementation projects; finish focused experiments before starting broad projects.

## AI-native engineering principles

Use AI throughout the engineering lifecycle:

| Activity | Appropriate AI leverage | Engineer remains accountable for |
|---|---|---|
| Learning | Socratic tutoring, explanations, quizzes | Understanding and independent recall |
| Codebase exploration | Summaries, call graphs, execution-path hypotheses | Verifying against source and runtime behavior |
| Implementation | Scaffolding, alternatives, refactoring assistance | Correctness, maintainability, and code ownership |
| Testing | Edge-case ideas, test scaffolding | Test quality and proof of behavior |
| Debugging | Hypotheses, log/trace analysis assistance | Evidence-based root-cause diagnosis |
| Design | Alternatives, critique, trade-off analysis | Final decisions and consequences |
| Workflow | Repetitive task automation and agentic workflows | Review, permissions, security, and outcomes |

**Non-negotiable:** never outsource understanding. AI may accelerate work and broaden exploration; it does not transfer engineering accountability. Verify generated code, tests, assumptions, dependencies, security, and behavior.

## Mastery scale

| Level | Meaning |
|---|---|
| 0 | Unseen |
| 1 | Familiar |
| 2 | Explain without notes |
| 3 | Apply / implement |
| 4 | Diagnose failures |
| 5 | Design and defend trade-offs |
| 6 | Transfer understanding to unfamiliar problems |

Assign levels per concept based on demonstrated evidence. Watching a lesson does not increase mastery automatically.

## Career development: capability before title

- **SDE-2 readiness:** independently own components and features, make sound local design decisions, deliver reliably, handle ambiguity, and demonstrate measurable impact.
- **SDE-3 capability target:** drive complex and ambiguous technical problems, design across components or services, influence technical decisions, improve engineering standards, and deliver broader impact.
- Build these capabilities through real work ownership, feedback, communication, and collaboration—not study alone. Actual promotion criteria vary by organization.

## Current next action

Begin Backend from First Principles, Lesson 1: **Why does a backend exist?**

Starting question: **Why can't a mobile application connect directly to a database, fetch a user's account balance, and display it?**

Answer in your own words. Consider what the client would need to know, scale, access control, business rules, and what happens when the database changes. The mentor should review the reasoning and ask the next question only after this attempt.
