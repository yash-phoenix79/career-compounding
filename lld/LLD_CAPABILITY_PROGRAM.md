# LLD Engineering Capability Programme

**Status:** Locked  
**Start date:** 2026-11-25  
**Cadence:** 30 minutes per session, 6 sessions per week  
**Weekly recovery:** 1 day without a formal LLD session  
**Implementation language:** Java  
**Teaching mode:** Guided, Socratic, first-principles, hands-on  
**First design exercise:** Vending Machine  
**Estimated foundation cycle:** 8–10 weeks (24–30 focused hours)

## 1. Purpose and north star

This is not a course for memorising standard interview solutions. The objective is to develop transferable software-design capability: independently understand unfamiliar problems, reason about requirements and constraints, model a domain, derive responsibilities and interactions, implement a correct design, evaluate alternatives, and defend engineering decisions.

The vending machine is the first practice laboratory, not the limit of the curriculum. The capability must transfer to unfamiliar and non-standard problems.

The six capabilities we are deliberately training:

1. **Think:** decompose unfamiliar problems, ask precise questions, expose ambiguity, identify constraints and reason from first principles.
2. **Model:** identify actors, use cases, entities, value objects, behaviours, relationships, states and invariants.
3. **Design:** assign responsibilities, choose abstractions, manage dependencies and apply OOP, SOLID and patterns when justified.
4. **Implement:** translate the model into clean Java code, handle errors and build maintainable, testable software.
5. **Judge:** compare alternatives, detect over-engineering and under-engineering, assess trade-offs and critique designs.
6. **Defend:** explain decisions, respond to criticism and adapt a design when requirements or constraints change.

## 2. Locked operating agreement

- Complete one focused **30-minute LLD session on six days each week**.
- Keep one day free of a formal LLD session for recovery; do not create catch-up debt.
- Use Java for implementation.
- Teaching is guided and Socratic: reason first, receive hints when stuck, attempt the work, then review the solution and alternatives.
- Every session must produce evidence: a written answer, requirement, diagram, design decision, code change, test, review, or independent explanation.
- Do not count passive reading or watching as mastery.
- Do not skip prerequisites. Compress only by testing demonstrated knowledge and moving on when the required capability is proven.
- Do not force design patterns, interfaces, inheritance, concurrency or infrastructure into a design without a problem-driven reason.
- Do not treat AI-generated code as understood until it can be explained, modified and tested independently.
- Preserve the wider Career OS priorities and protect sleep and work delivery. The LLD programme is a focused part of the existing engineering-learning routine, not permission to create an unbounded workload.

## 3. The first-principles reasoning framework

Use this sequence for every design problem:

1. **Understand the real-world problem:** who has the problem, who uses the system, and what outcome is needed?
2. **Discover actors and use cases:** what does each actor need to accomplish?
3. **Clarify requirements and constraints:** functional scope, quality attributes, assumptions, boundaries and non-goals.
4. **Derive business rules and invariants:** what must always be true? What must never happen?
5. **Model the domain:** identify concepts, identity, state, behaviour, entities and value objects.
6. **Assign responsibilities:** which object owns each piece of data and behaviour, and why?
7. **Define relationships and contracts:** how do objects collaborate? What should depend on abstractions?
8. **Model behaviour:** workflows, state transitions, events, failure paths and concurrency boundaries where relevant.
9. **Implement and verify:** build the smallest coherent solution and test its important rules.
10. **Critique and defend:** compare alternatives, identify weaknesses, explain trade-offs and adapt to changed requirements.

This is a reasoning aid, not a rigid ceremony. Use only the steps that help the problem, but never skip the underlying questions.

## 4. Prerequisite and mastery map

Prerequisites are part of the programme, not administrative work to rush through. Each topic is learned from the problem it solves and tested in the vending machine or a small isolated exercise.

### A. Programming and Java foundations

- Types, variables, expressions, control flow and methods.
- Primitive values versus object references; identity versus equality.
- Mutability, immutability, aliasing and side effects.
- Classes, constructors, fields, methods and access modifiers.
- Interfaces and abstract classes.
- Collections: List, Set, Map, queues; choosing structures from required operations.
- Generics and type safety.
- Enums and modelling finite sets of states.
- Exceptions and error propagation.
- Lambdas and basic functional interfaces where useful.
- Packages, visibility and project structure.
- Basic debugging and JUnit-based testing.

**Mastery evidence:** explain references, equality, mutability and collection choices; write and test small Java examples without copying a template.

### B. Object-oriented thinking and domain modelling

- What objects represent; state, behaviour and identity.
- Encapsulation and invariants.
- Abstraction and contracts.
- Polymorphism and dynamic dispatch.
- Inheritance versus composition.
- Association, aggregation and composition.
- Entities versus value objects.
- Responsibility assignment and object collaboration.
- Constructors and object validity.
- Cohesion and coupling.

**Mastery evidence:** derive a small object model from a written scenario, explain each responsibility, and identify an inappropriate abstraction.

### C. Software design principles

- Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation and Dependency Inversion.
- Separation of concerns.
- Program to an interface when it creates a useful boundary.
- Dependency injection and object construction.
- Composition over inheritance as a heuristic, not an absolute rule.
- DRY, KISS and YAGNI, including the trade-offs and common misuses.
- Testability, changeability and the cost of abstraction.

**Mastery evidence:** diagnose a deliberately poor design, refactor it for a concrete reason, and explain the cost of the refactor.

### D. Behaviour and UML modelling

- Use-case and activity modelling.
- UML class diagrams: attributes, operations, visibility, relationships, multiplicity and dependencies.
- Sequence diagrams: messages, object lifelines and interaction order.
- State machines: states, events, guards, transitions and invalid transitions.
- Component diagrams and boundaries.
- Translating diagrams into code and keeping diagrams consistent with implementation.

**Mastery evidence:** create and explain the smallest useful diagrams for a workflow; identify what a diagram does not communicate.

### E. Design patterns

- Why patterns emerge and what recurring design pressure they address.
- Creational: Factory, Builder and Singleton (including Singleton's costs).
- Structural: Adapter, Decorator, Facade and Composite.
- Behavioural: Strategy, State, Observer, Command and Template Method.
- Pattern intent, participants, collaboration, consequences and alternatives.
- Recognizing when a simple conditional or direct composition is better.
- Avoiding pattern names as a substitute for reasoning.

**Mastery evidence:** derive the need for a pattern from a changing requirement, implement it, and explain why simpler alternatives were rejected.

### F. Correctness and engineering quality

- Input validation and domain errors.
- Unit, integration and behavioural tests.
- Test doubles and dependency boundaries.
- State transition correctness and invariant testing.
- Transaction boundaries and partial failure.
- Shared mutable state, race conditions and critical sections.
- Synchronization and locking at an appropriate level.
- Idempotency and duplicate requests/events.
- Retry safety, compensation and refund/recovery flows.
- Observability and useful diagnostic information where relevant.

**Mastery evidence:** reproduce a failure, write a test that exposes it, implement a justified fix, and explain residual limitations.

## 5. Daily 30-minute session protocol

A normal session uses this timebox:

- **3 min — Retrieval:** explain the previous concept without notes.
- **7 min — First-principles lesson:** derive today's concept, its purpose and mental model.
- **12 min — Guided reasoning:** answer questions and apply the concept to the current design.
- **6 min — Build evidence:** create or modify a diagram, code, test, requirement or decision record.
- **2 min — Recall and next action:** summarize what is understood, what remains unclear and the next executable step.

Some sessions may use most of the time for implementation or a design review. The timebox is a default, not a reason to interrupt deep work at an artificial point. Carry unfinished work forward explicitly.

For every important concept, use this learning loop:

1. Learn why the concept exists.
2. Explain its mental model in your own words.
3. Compare alternatives and trade-offs.
4. Apply it to the current problem.
5. Implement or model it yourself.
6. Test it or challenge it with a counterexample.
7. Recall it without notes.
8. Transfer it to a different problem.

## 6. Eight-to-ten-week plan

The estimate is 8–10 weeks at six 30-minute sessions per week: 24–30 hours of focused practice. It is an estimate, not a deadline. Advance based on evidence, not calendar completion.

| Period | Focus | Expected evidence |
|---|---|---|
| Week 1 | Java prerequisite diagnostic and targeted foundations | Java exercises; clear understanding of references, classes, interfaces, collections, enums and exceptions |
| Week 2 | OOP and domain modelling | Domain model; responsibility explanations; composition/inheritance exercises |
| Week 3 | SOLID and software design principles | Poor-design critique; refactoring; dependency and coupling analysis |
| Week 4 | Requirements, UML and behavioural modelling | Use cases, class/sequence/state/component diagrams |
| Week 5 | Design patterns and design alternatives | Small pattern implementations; pattern/no-pattern comparisons |
| Weeks 6–7 | Vending machine design and Java implementation | Defended design, runnable application, core purchase and operator flows |
| Week 8 | Testing, failures, concurrency and reliability | Unit/integration/failure tests; concurrency analysis; test report |
| Week 9 | Documentation, peer review and interview defence | Complete submission package; peer review; recorded design defence |
| Week 10 (buffer if needed) | Remediate gaps and independent transfer assessment | Rework weak areas; solve an unfamiliar variation independently |

### First-session start

**2026-11-25 — Day 1.** Start the real vending-machine problem immediately while checking prerequisites in context.

Day 1 is expected to produce:
- A concise problem statement.
- Initial functional scope and explicit unknowns.
- Initial actors and use cases.
- A first list of domain concepts (not a final class design).
- A small project skeleton or repository setup decision.
- A first evidence commit or documented artifact.

Do not spend the first day only discussing what LLD is. Teach the minimum required context and start deriving the solution.

## 7. Vending machine challenge scope and deliverables

The vending machine is the first end-to-end exercise. Derive the detailed requirements together; do not assume the design in advance.

### Design and analysis
- Problem statement, scope, non-goals and assumptions.
- Functional and non-functional requirements.
- Actors, use cases and user journeys.
- Business rules, invariants and edge cases.
- Domain model and responsibility matrix.
- UML use-case, class, sequence, state and component diagrams where each adds value.
- Design decisions, alternatives and trade-offs.

### Implementation
- Java domain model and application services.
- Inventory and restocking.
- Product selection and purchase workflow.
- Payment boundary with cash/card/UPI simulation as agreed in scope.
- Dispensing boundary and change handling if cash/change is in scope.
- Transaction lifecycle and cancellation/refund/recovery paths.
- Runnable CLI demonstration.
- Keep hardware, external payment gateways and persistence behind replaceable boundaries or explicitly out of scope for the first version.

### Verification and engineering quality
- Unit and integration tests.
- Out-of-stock, invalid selection, insufficient payment and payment failure.
- Dispensing failure after successful payment and recovery/refund semantics.
- Duplicate payment callback or repeated request.
- Concurrent attempts to buy the last item.
- Restocking and price-change behaviour during an active transaction.
- Test report and known limitations.
- SOLID and pattern justification based on actual design needs.

### Final shareable package
1. GitHub repository as source of truth.
2. Eraser architecture workspace with diagrams.
3. Technical design document (PDF or Markdown).
4. Runnable CLI demo and test evidence.
5. Short demo recording.
6. Peer review and engineering retrospective.
7. One central Notion/GitBook page is optional; do not build a portal before the solution is complete.

## 8. Transfer beyond standard interview problems

After the vending machine, practise varied problem families rather than memorising a fixed catalogue:

- Resource management: Parking Lot, Library Management.
- Scheduling and coordination: Elevator, Meeting Room Booking.
- Financial workflows: Splitwise, Payment System.
- Booking and inventory: Movie Ticket Booking, Seat/Inventory Reservation.
- Games and simulations: Chess, Snake and Ladder.
- Infrastructure components: Rate Limiter, Cache, Logger.
- Workflow and event systems: Notification Framework, Approval Workflow, Pub/Sub.
- Unfamiliar prompts with changing, incomplete or conflicting requirements.

For every new problem, begin with a blank page and the first-principles reasoning framework. Do not reuse a class diagram without re-deriving the domain.

## 9. Mastery gates and evaluation

Use three levels for each important topic:

- **Understand:** explain the purpose, mechanism and limitations without relying on memorised wording.
- **Apply:** use it correctly in code or a design and test the result.
- **Judge:** identify misuse, compare alternatives, explain trade-offs and adapt when requirements change.

Evaluate each complete challenge out of 100:

| Capability | Weight |
|---|---:|
| Requirement analysis and ambiguity handling | 10 |
| Domain modelling | 15 |
| Responsibilities and abstractions | 15 |
| OOP and SOLID reasoning | 15 |
| UML and interaction modelling | 10 |
| Pattern selection and restraint | 10 |
| Correctness, failure handling and concurrency | 10 |
| Testing and code quality | 10 |
| Communication and trade-offs | 5 |
| **Total** | **100** |

The final transfer assessment is not a score alone. The user must independently:
- Derive a design for an unfamiliar problem without a template.
- Explain why important objects and abstractions exist.
- Implement a coherent core flow in Java.
- Identify and test important failure paths.
- Adapt the design when a requirement changes.
- Defend decisions and acknowledge limitations.

Interview target: work toward a defensible 45–60 minute design discussion for appropriately scoped problems. Do not claim universal mastery from one project or one assessment.

## 10. Session records and evidence

At the end of each session, record:
- Date and session number.
- Concept and first-principles explanation.
- Questions answered and reasoning.
- Artifact produced (file, diagram, code, test or commit).
- Mistakes or misconceptions corrected.
- What can now be explained independently.
- Remaining knowledge gap.
- Next executable action.

Update the canonical Career OS progress log with factual evidence. Do not backfill sessions that did not happen. The programme document is the plan; the progress log is the evidence.

## 11. Resource shelf

Use resources selectively to answer the current learning question. Do not turn this into resource collection.

- [Dev.java Learn](https://dev.java/learn/) — Java language and platform foundations.
- [Refactoring.Guru](https://refactoring.guru/) — design principles, patterns and refactoring explanations.
- [Java Design Patterns](https://github.com/iluwatar/java-design-patterns) — inspect concrete Java implementations after deriving the need.
- [Awesome Low Level Design](https://github.com/ashishps1/awesome-low-level-design) — supplementary practice prompts and references.
- [PlantUML](https://plantuml.com/) — text-based UML diagrams.
- [Mermaid](https://mermaid.js.org/) — diagrams in Markdown and GitHub.
- [Eraser](https://www.eraser.io/) — collaborative architecture diagrams and technical documentation.
- [A Philosophy of Software Design](https://web.stanford.edu/~ouster/cgi-bin/book.php) — abstraction, complexity and design judgment.
- [Effective Java](https://www.oreilly.com/library/view/effective-java/9780134686097/) — Java-specific design and implementation guidance.

## 12. Completion definition

The first cycle is complete when the user has:
- Demonstrated the prerequisite and OOP foundations through explanation and exercises.
- Produced and defended a complete vending-machine design.
- Implemented and tested the agreed core scope in Java.
- Analysed important failures and concurrency boundaries.
- Published the final submission package and completed peer review.
- Passed an independent design-transfer exercise.

**North star:** Do not train to reproduce LLD answers. Train to derive good designs from unfamiliar problems.
