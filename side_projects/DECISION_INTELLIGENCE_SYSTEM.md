# Decision Intelligence System: Research, Architecture & Build Plan

**Status:** Research complete enough to choose a first experiment; implementation not started  
**Portfolio status:** Research  
**Purpose:** Determine how to build a practical system that improves consequential decisions through evidence-based research, independent analysis, adversarial review, selective simulation, and learning from outcomes.

## Executive decision

Build a **Decision Intelligence Engine (DIE)** as a staged experiment, not an unrestricted swarm of agents.

**Recommended first move:** prototype a research-and-deliberation workflow with one strong research agent, three independent specialist analyses, a skeptic, a source-verification step, and a synthesizer. Store each decision and its evidence in a simple local database or versioned Markdown/JSON records. Compare it against a single-agent baseline before adding more components.

**MiroFish is a possible simulation component, not the decision engine itself.** Use it only for questions where interactions among actors and feedback loops materially affect the outcome. Do not make every decision go through an agent simulation.

**Do not build a full custom desktop app yet.** First prove that the workflow creates better decisions on real examples. Reuse existing open-source projects where possible, and add integration only after a component proves useful.

### The problem statement

Given a consequential question in career, engineering, finance, business, or personal planning, produce a defensible decision and execution plan by:

1. Clarifying the objective, constraints, deadline, and success criteria.
2. Gathering relevant, traceable evidence and identifying missing information.
3. Comparing plausible options instead of prematurely committing to one.
4. Having independent specialists analyze the problem.
5. Stress-testing assumptions and strongest recommendations.
6. Using scenario simulation only when actor interaction or feedback loops matter.
7. Synthesizing trade-offs, uncertainty, and next actions.
8. Recording predictions and outcomes to evaluate and improve future decisions.

The system should improve the quality of decisions, not maximize the number of agents, tokens, citations, or pages.

## First-principles analysis

### What makes a decision hard?

Most consequential decisions combine several sources of difficulty:

- **Unclear objectives:** the decision-maker has not specified what success means.
- **Incomplete evidence:** relevant information is missing, stale, biased, or hard to find.
- **Alternative blindness:** the initial options omit a better choice or a reversible experiment.
- **Reasoning errors:** assumptions are mistaken for facts, risks are missed, or trade-offs are hidden.
- **Uncertainty:** even correct reasoning cannot eliminate unknown future outcomes.
- **Execution gap:** a recommendation does not translate into a feasible plan.
- **No feedback loop:** the decision-maker never compares predictions with outcomes.

Multiple agents can help with some of these problems, but cannot automatically solve them. Agents can share the same blind spots, cite weak evidence, reinforce each other, or generate a confident consensus around a bad premise.

### Design principles

1. **Problem specification before agent orchestration.** Define goals, hard constraints, options, and decision deadline first.
2. **Evidence before confidence.** Important factual claims need traceable sources; the system must preserve contradictions and mark unverified claims.
3. **Independent before collaborative.** Capture initial analyses before exposing agents to one another's conclusions.
4. **Critique the argument, not the person or role.** Ask for counter-evidence, failure modes, and conditions that would reverse a recommendation.
5. **Consensus is optional.** Preserve unresolved disagreements; do not use vote counts as truth.
6. **Choose the simplest method that works.** A single agent, checklist, calculation, or small experiment may beat a multi-agent workflow.
7. **Simulation is conditional.** Simulated agent behavior is a scenario, not empirical proof or a calibrated forecast.
8. **Value of information governs research depth.** Continue research when new information could change the decision enough to justify its cost.
9. **Make uncertainty actionable.** Identify which unknowns matter and how to reduce them.
10. **Measure incremental value.** Every additional agent or stage must earn its latency and cost through better outcomes.
11. **Human owns the decision.** The system recommends and explains; the user decides, especially for high-stakes, financial, health, or career choices.
12. **Keep a decision audit trail.** Store the brief, evidence, assumptions, dissent, final choice, predictions, and outcomes.

## What research suggests

### 1. Multi-agent debate: promising, not universally superior

**Du et al., ICML 2024 — “Improving Factuality and Reasoning in Language Models through Multiagent Debate.”**  
Paper: https://proceedings.mlr.press/v235/du24e.html  
Project page: https://composable-models.github.io/llm_debate/

The method has several model instances propose answers, critique each other's reasoning, and debate over multiple rounds. The authors report gains on the tasks they evaluate, including reasoning and factual validity.

**Use:** independent proposals followed by bounded critique and revision.  
**Caveat:** results on selected benchmarks do not establish that a council improves open-ended life or career decisions. Debate can cost more and can still converge on incorrect claims.

### 2. Multi-agent failure modes: coordination is a real engineering problem

**Cemri et al., “Why Do Multi-Agent LLM Systems Fail?” (2025; NeurIPS 2025 Datasets and Benchmarks Track).**  
Paper: https://arxiv.org/abs/2503.13657  
Published proceedings: https://papers.nips.cc/paper_files/paper/2025/hash/b1041e52d3be19f0a9bc491657488e4a-Abstract-Datasets_and_Benchmarks_Track.html

The research analyzes failures across multi-agent frameworks and identifies recurring problems involving specification, inter-agent alignment, system design, verification, and termination. It argues against assuming that multi-agent orchestration automatically produces meaningful gains.

**Use:** explicit role contracts, bounded rounds, task-level checks, clear stopping conditions, and a single-agent baseline.

### 3. Debate strategy and cost need evaluation

**Smit et al., ICML 2024 — “Should we be going MAD? A Look at Multi-Agent Debate Strategies for LLMs.”**  
Paper: https://proceedings.mlr.press/v235/smit24a.html

The authors compare debate and prompting strategies and report that debate does not reliably outperform alternatives such as self-consistency and ensembling in their tested settings; tuned strategies can perform better.

**Use:** compare debate with cheaper baselines rather than assume debate is the best default.

### 4. Sparse communication can reduce overhead

**Li et al., Findings of EMNLP 2024 — “Improving Multi-Agent Debate with Sparse Communication Topology.”**  
Paper: https://aclanthology.org/2024.findings-emnlp.427/  
Google Research page: https://research.google/pubs/improving-multi-agent-debate-with-sparse-communication-topology/

The work studies how agents communicate and reports that more selective communication can match or outperform fully connected debate while reducing computational costs in its evaluated tasks.

**Use:** use an orchestrator to route relevant critiques instead of letting every agent reply to every other agent.

### 5. Explore alternatives explicitly

**Yao et al., NeurIPS 2023 — “Tree of Thoughts: Deliberate Problem Solving with Large Language Models.”**  
Paper: https://arxiv.org/abs/2305.10601  
Proceedings: https://papers.nips.cc/paper_files/paper/2023/hash/271db9922b8d1f4dd7aaef84ed5ac703-Abstract-Conference.html

Tree of Thoughts explores and evaluates multiple candidate reasoning paths rather than following a single path.

**Use:** generate options, assess constraints, compare consequences, and revisit branches when evidence changes. This is a reasoning pattern, not a requirement to implement a literal tree-search algorithm in v1.

### 6. Memory and feedback can make the workflow cumulative

**Shinn et al., NeurIPS 2023 — “Reflexion: Language Agents with Verbal Reinforcement Learning.”**  
Paper: https://arxiv.org/abs/2303.11366  
Proceedings: https://proceedings.neurips.cc/paper_files/paper/2023/hash/1b44b878bb782e6954cd888628510e90-Abstract-Conference.html

Reflexion uses feedback and textual reflections from prior attempts to inform future behavior without updating model weights.

**Use:** retain prior decisions and outcomes. Do not automatically promote an agent's explanation of failure into a universal rule; record evidence separately from interpretation.

### 7. Simulated agents can model interactions, but realism must be tested

**Park et al., “Generative Agents: Interactive Simulacra of Human Behavior” (2023).**  
Paper: https://arxiv.org/abs/2304.03442

This work explores agents with memory, reflection, and planning in a simulated social environment.

**Use:** informs the simulation layer when interactions among actors matter.  
**Caveat:** coherent simulated behavior is not proof that the simulation predicts real people or future events accurately.

### 8. Research quality needs its own evaluation

**DeepResearch Bench (2025).**  
Paper: https://arxiv.org/abs/2506.11763

This benchmark evaluates deep research agents using expert-authored tasks and report-quality dimensions, including retrieval and citation-related quality.

**Use:** evaluate coverage, source relevance, citation support, and the quality of the final report—not merely report length or number of sources.

## Core workflow

### Stage 0 — Decision brief
Capture:
- Decision question and context.
- Desired outcomes and success criteria.
- Hard constraints versus preferences.
- Deadline and reversibility.
- Current options and omitted alternatives.
- Known facts, assumptions, and missing information.

**Output:** validated decision brief.

### Stage 1 — Research plan and evidence ledger
Decompose the question into researchable subquestions. Prefer primary and authoritative sources where appropriate. Track for each important claim:
- Claim and scope.
- Source URL, title, date, and relevant passage.
- Whether the source supports, contradicts, or contextualizes the claim.
- Source quality, freshness, and limitations.
- Verification status and unresolved disagreement.

Do not allow the researcher to mark its own claim as verified merely because it found a page with similar wording. For important claims, retrieve and inspect the cited passage. Label inference and opinion separately from fact.

**Output:** evidence ledger, findings, gaps, contradictions, and research stopping recommendation.

### Stage 2 — Independent analysis
Start with three task-dependent perspectives, selected from:
- Domain specialist.
- Strategist / objective optimizer.
- Risk analyst.
- Skeptic / red team.
- Decision analyst.

Each analyst receives the brief and shared verified evidence, but not other analysts' conclusions. Require:
- Recommended option and alternatives.
- Main reasons and evidence.
- Assumptions.
- Failure modes and downside.
- What information could change the recommendation.

### Stage 3 — Adversarial review
Have the skeptic challenge the leading options. Ask other agents to respond only to substantive challenges. Require a counterargument, supporting evidence, and conditions under which each side would change its view.

Stop after a bounded number of rounds or when no material new evidence or argument appears. Preserve remaining disagreement.

### Stage 4 — Optional scenario simulation
Invoke MiroFish or another simulation tool only when feedback loops, social dynamics, or interactions among actors are important. Define:
- Reality seed and evidence.
- Assumptions and agent personas.
- Scenarios and variables.
- What would count as an informative result.
- How simulation outputs will be distinguished from observed facts.

Never present a generated simulation as a verified prediction without independent validation.

### Stage 5 — Decision analysis and synthesis
Compare viable options against explicit criteria. Use a decision matrix for transparency, and expected utility only where probabilities and utilities can be meaningfully estimated. Avoid fabricated precision.

The final report should include:
1. Recommendation and confidence/uncertainty.
2. Best alternative and why it lost.
3. Evidence for the decision.
4. Main assumptions and unresolved questions.
5. Risks, trade-offs, and reversibility.
6. What evidence would change the recommendation.
7. Immediate next action, milestones, and review date.
8. Research and compute cost.

The synthesizer must assess evidence quality and arguments, not count agent votes.

### Stage 6 — Execution and outcome review
Turn the decision into a small plan with actions, owners (usually the user), deadlines, and measurable signals. Record predicted outcomes and review dates. Later compare actual outcomes with predictions, while accounting for luck and external factors.

## Proposed implementation architecture

Keep v1 small and replaceable.

| Layer | V1 choice | Why |
|---|---|---|
| User interface | Existing CLI or a minimal local web UI only if needed | Avoid premature desktop-app development |
| Orchestration | A simple explicit workflow/state machine | Easier to inspect, test, and debug than a free-running swarm |
| Research | Web search/fetch tools plus source ledger | Traceability is a core requirement |
| Agents | Small number of roles, possibly the same model at first | Measure role value before paying for model diversity |
| Verification | Separate citation/claim-checking pass | Research agent should not be sole verifier |
| Decision analysis | Explicit criteria and trade-off table | Makes values and assumptions visible |
| Simulation | MiroFish as optional, isolated component | Avoid coupling all decisions to simulation |
| Storage | SQLite plus exported Markdown/JSON | Local, portable, easy to inspect and back up |
| Evaluation | Fixed test decisions and scorecards | Detect whether each component helps |
| Models | Provider adapters; local models only if quality and hardware suffice | Avoid locking architecture to one provider |

A framework is not the architecture. Prefer plain, inspectable orchestration until complexity requires a framework. Keep simulation and research tools behind interfaces so they can be replaced.

## Open-source candidates to inspect

These are candidates, not endorsements. Check the current repository, license, maintenance, dependencies, model-provider requirements, security, and installation instructions before adoption.

### MiroFish — optional scenario simulation
- Repository: https://github.com/razor-ai/mirofish
- Official project site: https://mirofish.ai/
- Documented workflow: source material / knowledge graph, agent persona and environment setup, simulation, report generation, and follow-up interaction.
- Documented setup uses Node.js, Python, an OpenAI-compatible model endpoint/API key, and a Zep Cloud API key. The README describes a free monthly Zep quota for simple use, not a guarantee that the entire workflow is free.
- Fit: useful when interactions and feedback loops matter; not a replacement for evidence research or decision analysis.
- Decision: do not make it a prerequisite for v1.

### Socratic Council — deliberation candidate
- Repository: https://github.com/richer-richard/socratic-council
- Intended workflow discussed during initial discovery: independent analysis, cross-examination, evidence gathering, and structured decision records.
- Before adoption, verify the current repository's actual capabilities, license, release/install path, provider costs, and maintenance. Do not assume that its name or README proves quality.

### Research implementation from the multi-agent debate paper
- Repository: https://github.com/composable-models/llm_multiagent_debate
- Useful as a research reference and experimental implementation, not necessarily a production-ready general-purpose decision product.

### Important constraint
Open-source code is not the same as free inference. Hosted model APIs can incur charges. Local inference avoids per-request API charges but consumes hardware and may reduce quality or speed. Keep usage budgets and human approval for any external side effects.

## Evaluation plan: prove each component earns its cost

### Baseline comparison
Select 5–10 varied decisions with known context and, where possible, assessable answers or outcomes. Compare:
A. One strong model with a clear prompt and research tools.
B. Independent analyses + skeptic + synthesizer.
C. B plus a separate citation-verification stage.
D. C plus simulation for only the cases where simulation is plausibly relevant.

Use the same decision brief and comparable evidence access. Blind human review where practical.

### Scorecard
Score each output on a fixed rubric, e.g. 1–5:
- Factual correctness.
- Citation support and traceability.
- Coverage of important alternatives.
- Important risk and assumption coverage.
- Calibration and honest uncertainty.
- Actionability and fit to constraints.
- Decision-maker usefulness.
- Latency and monetary cost.

Track hard failures separately, such as fabricated citations, missed hard constraints, or unsafe recommendations. Don't treat agreement between agents as correctness. Don't judge decision quality solely by outcome; record reasoning and predictions before the outcome is known.

### Component ablation
Remove one component at a time (debate, verification, simulation, memory) and compare. Keep a component only if it improves quality enough to justify its cost, latency, and maintenance.

### Initial success criteria
Set thresholds before running the experiment. A reasonable first bar:
- No unverified citations presented as verified.
- No hard constraints violated in the final plan.
- At least one measurable quality improvement over the single-agent baseline on the evaluation set.
- Added cost and latency are documented and acceptable.
- A human can audit how the recommendation was reached.

If multi-agent debate does not beat the baseline, simplify the system rather than rationalizing the result.

## Risks and guardrails

- **Shared blind spots:** use different task perspectives, independent first passes, and external evidence.
- **Citation laundering:** verify the cited passage; multiple agents repeating a claim is not corroboration.
- **Groupthink:** hide initial analyses from other agents and preserve dissent.
- **Simulation overconfidence:** label simulated outcomes and test against historical or external data where possible.
- **False precision:** don't invent probabilities or scores unsupported by evidence.
- **Unbounded cost:** limit agents, rounds, search budget, and tokens; stop when marginal value is low.
- **Prompt injection / unsafe tool use:** treat retrieved pages as untrusted input; limit tools and permissions; never let research agents deploy, spend money, or send messages without explicit approval.
- **Privacy:** do not upload sensitive personal, work, or financial information to third-party services without understanding their data handling.
- **Overengineering:** avoid a full desktop app, vector database, elaborate graph store, or dozens of agents before a useful workflow is proven.
- **Decision outsourcing:** the system supports judgment; it does not own the user's decision.

## Build plan

### Experiment 1 — Decision Council MVP
**Scope:** one local workflow, no MiroFish integration yet.

1. Accept a structured decision brief.
2. Collect a bounded set of sources and write an evidence ledger.
3. Run three independent analyses.
4. Run one adversarial review.
5. Verify important citations.
6. Synthesize a recommendation and action plan.
7. Save the complete run as Markdown/JSON and SQLite records.
8. Compare against a single-agent baseline on several decisions.

**Non-goals:** autonomous execution, always-on agents, large simulation populations, custom model training, polished desktop UX, and automatic changes to life plans.

### Experiment 2 — Selective simulation
Choose one decision where interacting actors materially affect outcomes. Run the council with and without MiroFish. Keep the integration only if it surfaces actionable information that improves the decision.

### Experiment 3 — Decision memory
Add outcome review and prediction tracking. Evaluate whether history improves subsequent recommendations without propagating unsupported conclusions.

## Final recommendation

**Do this now: build Experiment 1, the Decision Council MVP.** Keep it local and auditable. Begin with a simple workflow and evidence ledger, use three independent perspectives plus a skeptic and synthesizer, and test against a single-agent baseline.

**Do not start by building around MiroFish.** It addresses the simulation problem, which is only one optional part of decision intelligence. Integrate it after the basic council works and a real use case demonstrates that simulation adds value.

The first proof should be a useful decision report produced with traceable evidence, explicit uncertainty, and concrete next actions. The system earns additional complexity only when measured results justify it.

## Source list

- Du et al., 2024, multi-agent debate: https://proceedings.mlr.press/v235/du24e.html
- Cemri et al., 2025, multi-agent failures: https://arxiv.org/abs/2503.13657
- Smit et al., 2024, debate strategy trade-offs: https://proceedings.mlr.press/v235/smit24a.html
- Li et al., 2024, sparse communication: https://aclanthology.org/2024.findings-emnlp.427/
- Yao et al., 2023, Tree of Thoughts: https://arxiv.org/abs/2305.10601
- Shinn et al., 2023, Reflexion: https://arxiv.org/abs/2303.11366
- Park et al., 2023, Generative Agents: https://arxiv.org/abs/2304.03442
- DeepResearch Bench, 2025: https://arxiv.org/abs/2506.11763
- MiroFish repository: https://github.com/razor-ai/mirofish
- MiroFish project site: https://mirofish.ai/
- Multi-agent debate reference implementation: https://github.com/composable-models/llm_multiagent_debate
