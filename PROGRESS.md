# Progress Log

Update this file at the end of each session. Keep entries factual. Do not claim progress without evidence.

## Locked non-negotiables

- **Daily 1:** Backend from First Principles — https://backend-from-first-principle.vercel.app/
- **Structured LLD practice:** active exercise: Vending Machine LLD Challenge 001. The programme is 30 minutes per session, six sessions per week, in Java; one formal recovery day.
- **Daily 3:** AI knowledge — https://aiengineeringfromscratch.com/ or a relevant reference in `RESOURCE_LIBRARY.md`.
- **Every weekend:** Make a tangible contribution to one active project: feature, bug fix, tests, reliability, documentation/design decision, or meaningful open-source contribution.
- These are the fixed operating contract. Do not replace them with another roadmap or resource hunt.

## Current status

- **Phase:** LLD capability foundations + backend fundamentals + daily AI knowledge
- **LLD programme:** Locked; starts 2026-11-25; 30 minutes × 6 sessions/week; Java; guided first-principles teaching.
- **LLD estimate:** 8–10 weeks (24–30 focused hours), with a usable first Vending Machine submission targeted after approximately 7–10 sessions.
- **LLD current task:** Day 1 — derive the vending machine problem statement, initial scope and unknowns, actors/use cases and domain candidates; create the first project artifact.
- **LLD status:** Planned; not started. Do not record completion until evidence exists.
- **LLD programme source:** `lld/LLD_CAPABILITY_PROGRAM.md`
- **Active LLD challenge:** `exercises/vending-machine/README.md`
- **Backend next action:** Continue the next concept; capture the concept, an example/experiment, and one trade-off or failure mode.
- **AI next action:** Study one small concept and write a concise takeaway or connect it to a current project.
- **Weekend project next action:** Choose the smallest useful change in the active project, implement it, test it, and commit it.
- **Current BUILD routine:** 5:30–7:00 AM (90 minutes) per the user's latest approved schedule. Scale down for sleep debt, illness, recovery needs or urgent work; never create catch-up debt.
- **Evidence expected:** Design/code/tests, a concept note or experiment, or a reviewable project contribution.

## Scoreboard

| Metric | Current | Target |
|---|---:|---:|
| Daily backend sessions | 0 | 5 per week |
| Formal LLD sessions | 0 | 6 per week |
| Daily AI knowledge sessions | 0 | 5 per week |
| Weekend project contributions | 0 | 1 per week |
| Implemented and tested slices | 0 | 1 per week |
| Weekly reviews completed | 0 | 1 per week |
| Public technical posts | 0 | 1 useful post per week to start |

Update numbers honestly. Do not infer historical completion; update only when evidence exists.

## Daily session log

| Date | Backend evidence | LLD evidence | AI knowledge evidence | Next action |
|---|---|---|---|---|
| YYYY-MM-DD | — | — | — | Record the next executable action after the session |

## Weekend project contribution log

| Weekend of | Project | Contribution | Tests/demo evidence | Commit or link | Next action |
|---|---|---|---|---|---|
| YYYY-MM-DD | — | — | — | — | Select one small contribution |

## Weekly review

### Shipped
- 

### Backend concept understood
- 

### LLD improvement
- 

### AI concept understood
- 

### Project contribution completed
- 

### What remains unclear
- 

### One next implementation task
- 

## Rules

- No streak guilt. Resume with the next small task.
- No claiming progress from watching alone.
- Keep tasks small enough to finish in one or two sessions.
- If a task stalls for two sessions, reduce scope or ask for a focused review.
- Do not create another tracker; this repository is the evidence log.


## Daily proof-of-record template

Copy one entry per day when logging actual work. Keep it factual; omit proprietary Amazon details and confidential code.

### YYYY-MM-DD
- **Backend concept + evidence:**
- **Trade-off/failure mode:**
- **LLD artifact + decision:**
- **AI concept + takeaway/experiment:**
- **Applied output / proof link:** commit, test output, artifact, or `learning-only` if no implementation was shipped.
- **Work impact (optional):** non-confidential delivery, investigation, review, or communication improvement.
- **Next executable action:**

A day can count as a learning day without shipping a feature, but passive consumption alone is not strong evidence. Every week should leave at least one reviewable implementation, test, or design artifact from the active project.

## Planned BUILD lesson — 2026-11-19 (not yet attempted)

- **Lesson ID:** AI-TOOL-EXECUTION-BOUNDARY-2026-11-19
- **Date:** 2026-11-19
- **Subject/domain:** AI engineering + backend architecture
- **Topic/prerequisite:** Tool-calling control loop and the trusted application-side execution boundary. Prerequisite: understand that a model can return a structured tool-call request; the application owns execution. The existing backend-first-principles question about why a mobile banking client should not connect directly to the database remains unanswered and is a useful retrieval test.
- **Credible sources:** [OpenAI function-calling guide](https://developers.openai.com/api/docs/guides/function-calling); [MCP specification, 2026-07-28](https://github.com/modelcontextprotocol/modelcontextprotocol/blob/main/docs/specification/2026-07-28/index.mdx); [OpenAI Agents SDK repository](https://github.com/openai/openai-agents-python).
- **Concepts presented:** The model proposes a named tool and arguments; the host validates tool availability, schema, authorization and policy; application code executes the operation; the result is returned to the model using the matching call identifier; the model then continues or finishes. Schema validity does not establish business correctness or authorization. Read and write tools have different risk; consequential writes need stricter controls and, where appropriate, human approval.
- **Practical exercise planned:** In the existing active codebase, ask the primary coding agent to trace one complete tool-call path without editing files. Independently verify the dispatch/execution boundary and identify one missing test. Do not start a new project.
- **Business connection:** Judge an AI workflow by the measurable customer problem and reliability of the resulting process, not by the presence of an agent. A useful discovery question is: “Tell me about the last time this repetitive task failed or was delayed; what happened and what did it cost?”
- **Actual output/evidence:** No code, test, independent explanation, customer conversation, or implementation has been reported. Only the lesson and exercise were delivered as a plan in the morning reminder.
- **Knowledge gaps:** User retrieval is not yet assessed; no current project/tool-call path has been inspected; authorization and idempotency behavior remain to be tested in an implementation.
- **Next lesson:** Error handling, idempotency, bounded retries and approval gates in tool execution.
- **Status:** planned; not attempted, retrieved, applied or verified.
