# Software Factory & Tool Notes

A working notebook for useful tools and an experiment to turn inspiration into shipped demos.

## Tools to investigate

### Context.dev
Website: https://www.context.dev/

An API for agents to search the web, scrape pages into Markdown/HTML/structured data, crawl sites, research questions with sources, run batches, and monitor page changes. It aims to package rendering, extraction, retries, and crawling infrastructure.

**Experiment:** Use it for one small workflow that needs current web information. Evaluate source quality, failure handling, latency, and credits consumed. Review data handling, limits, and current pricing before adopting it. Candidate only; not yet adopted.

### The Open Frontier
Website: https://www.theopenfrontier.com/?uc=strategy
Methodology: https://www.theopenfrontier.com/methodology
Cost calculator: https://www.theopenfrontier.com/calculator

Compares open and closed models by use case, public benchmark scores, and estimated cost. The Strategy view is one of its use-case boards: select a workload category, inspect candidate models and their benchmark breakdowns, and compare quality against estimated task cost. The site also provides broader leaderboards, intelligence-per-dollar views, and a workload cost calculator.

Its methodology says the benchmark scores come from Artificial Analysis and the cost figures use published provider rates; the site refreshes its data regularly. The rankings are useful for shortlisting, not proof that a model will perform best on our own tasks. Model versions, prices, benchmark coverage, and provider performance change.

**Experiment:** Pick one real strategy/research or coding-agent task and create a small fixed evaluation set with expected outcomes. Compare two candidate models on task success, factuality, latency, and actual cost. Use the Strategy board to shortlist, then verify against our own workload. Do not choose solely on a single composite score or estimated cost.

**Decision rule:** Choose the cheapest model that reliably clears the quality bar for the task, not the cheapest model overall. Route harder or higher-risk tasks to a stronger model only when the evaluation shows the improvement is worth the extra cost.

### Hallmark
Website: https://www.usehallmark.com/
Source: https://github.com/nutlope/hallmark

An open-source design skill for coding agents including Claude Code, Codex, and OpenCode. It guides an agent to gather real content, choose a visual direction, lay out a page, and check the result with browser-based linting.

**Experiment:** Try it on a disposable branch or small POC. Compare against a page built without the skill; review visual hierarchy, responsiveness, accessibility, content accuracy, and lint findings. Review the skill and permissions before installing it globally. Automated lint does not prove a page is accessible or good.

## How to operate: the weekend software factory

This workflow is inspired by a builder's process. Treat it as an experiment to adapt, not a law.

1. **Collect during the week.** Save ideas, products, screenshots, problems, and repositories. Add one sentence about the problem and who it helps.
2. **Rank on the weekend.** Ask an agent to score user value, urgency, differentiation, feasibility, demo potential, and estimated effort. Require reasons and evidence.
3. **Select a small batch.** Brief each idea with target user, problem, core workflow, success criterion, timebox, and non-goals.
4. **Build in parallel.** The original process uses about 5–10 agents. For the first trial, start with 2–3 isolated POCs and scale only if coordination and review are manageable. Use separate branches/worktrees and clear boundaries.
5. **Kill quickly.** Stop ideas that fail the user-value test, require too much scaffolding, or cannot produce a credible demo in the timebox. Killing ~60% is a reminder to be selective, not a quota.
6. **Iterate on winners.** Keep the best one or two, test the core flow, and fix the largest usability issues.
7. **Polish and share.** Add a README, screenshots or a short recording, setup instructions, and known limitations. Share only what is safe and ready.
8. **Repeat.** Record what worked, what failed, time and money spent, and what to change next weekend.

### Guardrails

- One weekend experiment, not ten new commitments.
- Do not sacrifice sleep, work delivery, or the current primary career project.
- POCs are disposable; promote a winner only after review.
- Define pass/fail criteria for every POC.
- Inspect agent changes and run checks; “done” is not evidence.
- Track model/API costs and time.
- Record why each killed POC was stopped.
- Require human review before deployment or public posting.

### First weekend experiment

1. Collect 8–12 ideas, each with a one-line user problem.
2. Ask an agent to rank them transparently and choose two or three.
3. Give each POC a separate branch/worktree and strict scope.
4. Build only the core workflow.
5. Score attempts on usefulness, working functionality, clarity, effort, and next-step potential.
6. Keep at most one winner for another iteration; archive or delete the rest.
7. Write a retrospective.

**Success:** two or three honest attempts, a working demo worth showing or a clear reason none qualified, and a written retrospective. Do not force a winner.

## How to evaluate any new link

For every entry, record:
- What it does.
- The concrete idea worth borrowing.
- A small experiment that can be tested in a few hours.
- Outcome: keep, adapt, or discard, with a reason.

The goal is to turn a few discoveries into shipped work, not to grow an endless bookmark list.
