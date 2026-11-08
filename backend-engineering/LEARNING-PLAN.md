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

