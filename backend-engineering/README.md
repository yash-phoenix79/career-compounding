# Backend Engineering from First Principles

A long-term, evidence-driven learning program to develop transferable backend engineering judgment—not just familiarity with frameworks.

## North star

Become an engineer who can explain, design, implement, debug, scale, and operate backend systems from first principles. Understand the machinery beneath abstractions, then prove that understanding through code, experiments, tests, and production-style decisions.

**Completion is not the metric. Demonstrated capability is.**

## Learning resources

1. **Core written reference:** [Backend, from First Principles](https://backend-from-first-principle.vercel.app/) — 27 self-contained chapters with diagrams and runnable Go/Python examples.
2. **Video journey:** [Backend Engineering from First Principles — YouTube playlist](https://www.youtube.com/watch?v=6Ss4dJD9Kzg&list=PLui3EUkuMTPgZcV0QhQrOcwMPcBCcd_Q1&index=3) — the instructor's broader progression through story/philosophy, language-specific implementation, and production projects.

These resources overlap but are not identical. The website is a 27-chapter reference; the video series describes a three-phase learning journey. Use the relevant source for each session and record which source actually supports a claim.

## Three phases

1. **Story & Philosophy:** language-agnostic mental models, problems, protocols, system components, and the reasons behind design choices.
2. **Implementation:** translate principles into working code. Use the language and ecosystem that best serve the concept; prioritize Java for direct career transfer, and use Go/Python/JavaScript when the source or experiment calls for them.
3. **Production:** integrate the pieces into complete systems. Design for reliability, security, observability, performance, maintainability, and operational reality.

Do not skip the conceptual foundation. Do not mistake reading implementation code for being able to implement it independently. Do not call a project production-grade merely because it runs locally.

## The daily learning loop

One video or one coherent concept per learning day:

1. Identify the source and exact scope.
2. Build the mental model and answer the foundational questions in [METHODOLOGY.md](METHODOLOGY.md).
3. Inspect the mechanism: diagrams, request/data flow, state transitions, relevant OS/network/database behavior.
4. Be grilled: explain it without notes, reason through counterexamples, and diagnose failure scenarios.
5. Implement or run a focused experiment.
6. Extend the concept into production: failure handling, observability, security, scale, and trade-offs.
7. Record evidence, unresolved questions, and the next step.

A session can span multiple days when the concept is substantial. One-video-per-day is a cadence, not a reason to rush.

## Repository map

- [CURRICULUM.md](CURRICULUM.md) — source map and topic progression.
- [METHODOLOGY.md](METHODOLOGY.md) — the question framework, grilling protocol, and mastery standard.
- [PROGRESS.md](PROGRESS.md) — current state and next action.
- [templates/CONCEPT-NOTE.md](templates/CONCEPT-NOTE.md) — durable concept notes.
- [templates/DAILY-LEARNING-LOG.md](templates/DAILY-LEARNING-LOG.md) — daily session record.
- [sessions/](sessions/) — dated session notes and learning evidence.
- [implementations/](implementations/) — small experiments and runnable implementations.
- [projects/](projects/) — integrated production-style projects.

## Working rules

- Source-ground claims when studying a specific lesson. Clearly label outside knowledge, inference, and corrections.
- Prefer first-principles explanations over framework recipes.
- Use diagrams only when they clarify a mechanism or boundary.
- Build the smallest experiment that tests the concept.
- Preserve failed experiments and debugging lessons; they are valuable evidence.
- Keep notes concise enough to revisit, but deep enough to reconstruct the reasoning.
- Never mark a topic mastered solely because a video was watched.
- Every session ends with one concrete next action.

## Current starting point

We have established the three-phase learning philosophy from the introductory video transcript. The first substantive lesson is not yet recorded as completed. See [PROGRESS.md](PROGRESS.md).
