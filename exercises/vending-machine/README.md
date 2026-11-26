# Vending Machine — LLD Challenge 001

**Status:** Planned; starts 2026-11-25  
**Language:** Java  
**Learning cadence:** 30 minutes, 6 sessions per week  
**Parent programme:** [LLD Engineering Capability Programme](../../lld/LLD_CAPABILITY_PROGRAM.md)

## Purpose

This is the first end-to-end exercise in the LLD Engineering Capability Programme. The objective is to learn how to derive a design from an unfamiliar real-world problem, not to reproduce a memorised vending-machine class diagram.

The implementation is the proof of work. The deeper outcome is transferable skill in thinking, modelling, designing, implementing, judging and defending.

## Working agreement

- Derive requirements and assumptions before fixing the class design.
- Work through the problem using the first-principles framework in the parent programme.
- Learn each prerequisite when it becomes relevant; do not skip it or turn the first session into a theory-only prerequisite course.
- Use Java.
- Prefer the simplest design that satisfies the agreed requirements.
- Introduce patterns and abstractions only when a concrete design pressure justifies them.
- Record design alternatives and trade-offs.
- Keep the implementation runnable and testable.
- Do not claim a feature is complete without evidence.

## Initial questions to resolve

These are prompts for requirements discovery, not decisions already made:

- Which actors exist: customer, operator, maintenance technician or external payment provider?
- Which payment methods are in scope for the simulation?
- Is cash change required, and which denominations exist?
- Can a customer cancel after payment begins?
- What should happen if payment succeeds but dispensing fails?
- Can multiple customers or requests interact concurrently?
- Can an operator restock or change prices while purchases are active?
- Is persistence required, or is in-memory state sufficient for the first version?
- What hardware and external integrations are simulated rather than implemented?

## Planned submission artifacts

### Requirements and modelling
- [ ] Problem statement, scope and non-goals
- [ ] Functional and non-functional requirements
- [ ] Assumptions and constraints
- [ ] Actors and core use cases
- [ ] Business rules and invariants
- [ ] Edge-case and failure catalogue
- [ ] Domain model and responsibility matrix

### Visual design
- [ ] Use-case diagram, if useful
- [ ] UML class diagram
- [ ] Purchase sequence diagram
- [ ] Failure/refund sequence diagram
- [ ] Transaction state machine
- [ ] Component diagram
- [ ] Design decisions and trade-offs

### Java implementation
- [ ] Reproducible Java project and setup instructions
- [ ] Domain model and application logic
- [ ] Inventory and operator/restocking flow
- [ ] Product selection and purchase flow
- [ ] Payment abstraction and agreed payment simulations
- [ ] Dispensing abstraction
- [ ] Cancellation/refund/recovery behaviour
- [ ] Runnable CLI demonstration

### Verification
- [ ] Unit tests for domain rules
- [ ] Integration tests for complete purchase flows
- [ ] Failure-path tests
- [ ] Duplicate-operation/idempotency tests where relevant
- [ ] Concurrency tests for shared inventory where relevant
- [ ] Test report and known limitations

### Final shareable package
- [ ] GitHub repository and README
- [ ] Eraser architecture workspace
- [ ] Technical design document (Markdown or PDF)
- [ ] Working demo and test evidence
- [ ] Short demo recording
- [ ] Peer review with friend
- [ ] Retrospective and independent design defence

A central Notion/GitBook page is optional. Do not build a separate challenge portal before the design and implementation are complete.

## Delivery target

Aim to have a usable first submission within approximately 7–10 focused sessions, then improve its depth and quality through the rest of the programme. The full foundation cycle is estimated at 8–10 weeks. These are planning estimates, not reasons to skip understanding or testing.

## Progress

No user-authored design artifact or implementation has been completed yet. The Day 1 lesson was delivered on 2026-11-26; the user's attempt and first artifact are pending. No 2026-11-25 LLD session is backfilled. Update this section only when evidence exists.

- **Next session:** Day 1 — continue from the 2026-11-26 lesson; user attempt pending.
- **First action:** write problem-statement.md with the user outcome, first-scope assumptions, actors, use cases, open questions and candidate invariants.
