# Project Engineering Workflow

> A shared engineering operating method for every active project. The workflow is the standard; tools are optional accelerators. Keep the repository as the source of truth.

## Purpose

We work across multiple projects, so each session must start from the real current state and leave behind evidence another session can trust. The goal is to reduce repeated discovery, architecture churn, undocumented decisions, and claims that something works when it has not been tested.

This is a separate operating section of Career OS—not another project, tool collection, or reason to keep planning instead of building.

## The standard loop

**Understand → Design → Document → Implement → Validate → Handoff**

1. **Understand**
   - Read the README, agent instructions, current-status/handoff notes, relevant architecture decisions, and the code/tests that actually exist.
   - Establish what is implemented, what is proposed, what is broken, and what remains unknown.
   - For unfamiliar repositories, use code search and repository exploration. Treat generated summaries as navigation aids, not proof.
2. **Design**
   - State the user problem, smallest useful change, boundaries, data flow, failure cases, and acceptance criteria.
   - Use a diagram only when it clarifies a real decision. Record alternatives and trade-offs for consequential choices.
   - Prefer the simplest design that meets verified requirements; do not reopen settled architecture without new evidence.
3. **Document**
   - Put durable decisions and current truth in the repository, close to the code or in its canonical docs.
   - Keep requirements/vision, architecture/decisions, current status, execution plan, validation evidence, and next-session handoff findable. These are logical responsibilities, not a requirement to create six separate files in every repo.
   - Label proposed, historical, unverified, and verified claims honestly.
4. **Implement**
   - Make the smallest coherent, reviewable change.
   - Prefer a working vertical slice over a large scaffold. Keep mock mode and deterministic tests where external services would otherwise block progress.
   - Do not add a dependency or tool unless it solves a concrete problem worth its setup and maintenance cost.
5. **Validate**
   - Run the relevant tests, lint/type checks, and manual flows; test important edge cases and failure paths.
   - Check behavior against acceptance criteria. For security-sensitive or multi-user flows, test isolation and authorization explicitly.
   - Record exactly what ran and what remains unverified. Never claim production readiness from documentation alone.
6. **Handoff**
   - Update current status, decisions, evidence, blockers, and the single next action.
   - Leave the project in a state that can be resumed after weeks without reconstructing the conversation.

## Free and open-source tool policy

Use tools only when they improve the work. Prefer free and open-source options, inspect license and hosting requirements, and consider local hardware, privacy, setup effort, and ongoing maintenance. “Open source” does not necessarily mean every hosted feature or AI/API usage is free.

| Need | Default | Use when |
|---|---|---|
| Repository understanding | README, source search, tests, GitHub; optionally evaluate [Repowise](https://github.com/repowise-dev/repowise) | A repository is unfamiliar or hard to navigate. Verify current license, maintenance, and local requirements before adoption. |
| Architecture sketches | [Mermaid](https://github.com/mermaid-js/mermaid) in Markdown; [Excalidraw](https://github.com/excalidraw/excalidraw) for free-form diagrams | A diagram clarifies a boundary, flow, or trade-off. Keep source editable and near the project docs. |
| Architecture drafting | A short written design plus Mermaid/Excalidraw; optionally test [OpenDiagram](https://github.com/Itz-Agasta/OpenDiagram) | Only if it is genuinely faster than writing the design yourself. Verify license and whether any AI provider/API has separate costs. |
| Durable documentation | Markdown in GitHub | Default for internal project truth, decisions, and handoffs. |
| Published documentation | [Docusaurus](https://github.com/facebook/docusaurus) | Only when a project actually needs a browsable documentation site; do not add it merely to document a small repo. |
| Final verification | Existing test runner, linters, type checks, CI, and targeted manual checks | Every implementation change. |

Tool names above are candidates, not blanket endorsements. Recheck the canonical repository, license, activity, security, and installation requirements before adopting one. Do not pay for a hosted product when a lightweight repo-native workflow is enough. Do not spend a learning session installing tools when you could make progress with Markdown, code search, and tests.

## Shared project artifacts

Keep these responsibilities covered, using existing files where possible:

- **Intent:** Who the project helps, the problem, non-goals, and success criteria.
- **Current truth:** What works now, what is partial, what is proposed, and what is unverified.
- **Design and decisions:** Architecture, key boundaries, alternatives, trade-offs, and decision rationale.
- **Execution:** Milestones, prioritized tasks, blockers, and the next smallest useful change.
- **Evidence:** Commands/tests run, outcomes, known gaps, and reproducibility notes.
- **Handoff:** What changed this session and the exact next action.

Avoid duplicate sources of truth. Link to canonical docs instead of copying the same plan into multiple files.

## Application to our projects

### Thrills — move from architecture to a verified vertical slice

**Starting point:** Architecture and implementation contracts are documented; that is not proof of a working runtime.

1. Inspect the actual repository, environment, tests, and existing implementation before changing anything.
2. Confirm the M0 scope and identify the smallest runnable slice.
3. Build a reproducible Python project skeleton, Typer CLI, configuration, mock mode, and test/CI baseline only where still missing.
4. Implement one end-to-end vertical slice with deterministic tests.
5. Record real command output and unresolved integration gaps. Do not expand live source access until permissions and evaluation gates are ready.

**Avoid:** More architecture research unless code, tests, or new evidence reveals a real unresolved decision.

### Infinity — operationalize one finance-learning workflow

**Starting point:** The curriculum and tool inventory are planning assets, not a completed finance product.

1. Choose one high-value learning workflow.
2. Define its input, trustworthy sources, output, validation method, and measurable usefulness.
3. Run it manually or with the smallest implementation first.
4. Check factual accuracy, source freshness, decision usefulness, and effort required.
5. Document what was learned and decide whether to improve, automate, or discard it.

**Avoid:** Building the full catalogue or a large AI system before one workflow demonstrably helps.

### Forma / Negotiation OS — verify the real application and close a gap

1. Read the current status, architecture, open issues/PRs, code, and tests; verify what has actually shipped.
2. Select the highest-priority gap supported by evidence.
3. Implement the smallest coherent fix within the existing modular-monolith boundaries.
4. Test domain behavior and relevant API flows. For auth and session history, explicitly test authorization and cross-user isolation.
5. Update deployment and operational status only after checking real infrastructure; distinguish local tests from deployed verification.

**Avoid:** Claiming deployment, recovery, security, or production readiness based only on a runbook or design document.

### Vector — build the next capability that creates felt value

1. Read `AGENTS.md`, `docs/CURRENT.md`, and the canonical architecture/decision docs.
2. Check the existing runtime and tests before proposing a new component.
3. Pick one concrete user capability that fits the local-first architecture.
4. Implement and validate it end-to-end, keeping sensitive runtime data and secrets out of Git.
5. Update current status and the next-session handoff.

**Avoid:** Expanding architecture, adding agents, or reorganizing knowledge unless it unlocks a real capability.

### Career OS — learn backend fundamentals through evidence and practice

Use the same loop on learning tasks: understand one backend concept → design a small application or exercise → document trade-offs in your own words → implement → test and explain the result. Current learning priority is **backend engineering from first principles and low-level design (LLD)**. Keep AI model-training/reasoning-model resources saved for later; do not let them displace this focus.

A learning capture should eventually answer: What did I learn? What is still unclear? What did I build or test? What evidence shows I understand it? What is the next exercise?

## Default session checklist

Before work:
- [ ] Read the project instructions and current-status/handoff docs.
- [ ] Inspect relevant code and tests; do not assume the docs match reality.
- [ ] State the goal and acceptance criteria for this session.

During work:
- [ ] Make one small, coherent change.
- [ ] Use tools only when they save more time than they cost.
- [ ] Record important decisions and trade-offs.

Before stopping:
- [ ] Run the relevant checks and record actual results.
- [ ] Update canonical docs/status if reality changed.
- [ ] Record known gaps and one explicit next action.

## Prioritization rule

When several projects compete for attention, choose the next task based on user value, risk reduction, learning value, and readiness—not novelty or the number of tools available. Finish and validate a small slice before opening another major workstream.

**Operating principle:** Understand the real state. Design only what is needed. Document decisions. Implement a small slice. Validate with evidence. Leave a clear handoff.
