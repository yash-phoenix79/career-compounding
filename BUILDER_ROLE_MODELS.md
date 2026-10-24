# Builder Role Models & Reverse-Engineering Field Guide

**Purpose:** Learn from people who repeatedly build, release, maintain, or improve real software. Extract practices that can be tested in our own work—not personalities, hype, follower counts, extreme hours, or founder mythology.

**Operating rule:** This is a reference shelf, not a daily research task. Study one person only when it answers a question raised by the current project. Every study must produce either (a) one practice to test, (b) a code/design artifact, or (c) a written engineering lesson. No endless biography consumption.

## The 10 builders

### 1. Tanay Kothari — product intuition, iteration, customer contact
**Inspect:** Wispr Flow; interviews about its shift from silent-speech hardware toward software dictation; product quality metrics.
**Public evidence:** [Personal site](https://tanaykothari.com/), [AIX Ventures fireside chat](https://www.aixventures.com/fireside-chat-with-tanay-kothari-at-wispr-flow), [public profile](https://councils.forbes.com/profile/Tanay-Kothari-CEO-Co-founder-Wispr-Flow/c260f8bc-0910-429c-9332-cf2198489d6c).
**Adopt:** Find a sharp user problem; observe real users; define a quality metric tied to user outcomes (e.g. whether dictated text needs editing, not just transcription accuracy); change direction when usage disproves an assumption.
**For us:** Before a feature, write who has the problem, the current workaround, and the observable outcome that proves improvement.
**Caution:** Don't copy startup growth tactics, team scale, or founder workload. Not every anecdote about early output is independently verified.

### 2. Lauren Tan — deep technical work, compiler engineering, AI-agent workflows
**Inspect:** React Compiler's progression from experiments to beta, release candidate, and stable release; public agent tooling such as pstack/skills where available.
**Public evidence:** [React Compiler 1.0](https://react.dev/blog/2025/10/07/react-compiler-1), [React Compiler beta](https://react.dev/blog/2024/10/21/react-compiler-beta-release), [Lauren Tan's site](https://about.me/lauren.tan).
**Adopt:** Work through complex systems in stages; use prototypes to learn; expose work to adopters early; incorporate bug reports and contributions; make adoption incremental rather than requiring a risky all-at-once rewrite.
**For us:** For a difficult feature, create a tiny experiment first, record what it proved, then implement behind tests or a safe rollout where appropriate.
**Caution:** React Compiler is team work; don't attribute the entire project or all team practices to one person.

### 3. Mitchell Hashimoto — engineering craft and minimal viable scope
**Inspect:** Ghostty, Terraform, and his writing about building large technical projects.
**Public evidence:** [How I approach large technical projects](https://mitchellh.com/writing/building-large-technical-projects), [The Building Block Economy](https://mitchellh.com/writing/building-block-economy).
**Adopt:** Build for a real need; get a minimal version into daily use; implement the narrow path that makes it useful; defer features until real use reveals their value; treat foundational tools as leverage.
**For us:** Define one end-to-end workflow and make it reliable before adding secondary features.

### 4. Simon Willison — small tools, visible evidence, AI-assisted engineering
**Inspect:** Datasette, small HTML tools, detailed build logs, and writing about LLM-assisted programming.
**Public evidence:** [LLM workflow series](https://simonwillison.net/series/using-llms/), [open-source process notes](https://simonwillison.net/series/), [Datasette](https://datasette.io/).
**Adopt:** Make small useful tools; keep experiments concrete; show steps and results; use AI to accelerate exploration and implementation while inspecting output; test, document, and publish learnings.
**For us:** A session should leave a runnable experiment, test, diff, or note—not a pile of prompts or tabs.
**Caution:** Tiny one-file tools fit some jobs, not every production system.

### 5. Evan You — prototype, release, community feedback, maintainability
**Inspect:** Vue, Vite, release history, RFCs, issue discussions, and contribution guidance.
**Public evidence:** [Vue creator story](https://github.com/readme/stories/evan-you), [Vue FAQ](https://vuejs.org/about/faq.html), [Evan You interview](https://www.monterail.com/blog/evan-you-interview-features).
**Adopt:** Start by solving your own concrete problem; share a useful version; learn from users; make changes incrementally; treat maintenance, documentation, compatibility, and community as part of the product.
**For us:** Once anyone else uses a project, add setup instructions, release notes, issue triage, and compatibility expectations.

### 6. Guillermo Rauch — developer experience, deployment, end-to-end ownership
**Inspect:** Socket.IO, Mongoose, Next.js, Vercel, and talks about shipping incrementally.
**Public evidence:** [Vercel](https://vercel.com/about), [Accel interview on incremental delivery](https://www.accel.com/podcast-episodes/vercels-guillermo-rauch-on-bold-visions-for-the-future-delivered-incrementally), [GitHub](https://github.com/rauchg).
**Adopt:** Reduce friction between idea and deployed result; set a quality bar before coding; deliver in small increments; listen to feedback; own the full journey, including deployment.
**For us:** A feature isn't done when it compiles; it is done when a user can access it and important failure modes are understood.
**Caution:** A platform company's scale and infrastructure are not the default for a solo project.

### 7. Armin Ronacher — pragmatic libraries, operational learning, skeptical AI engineering
**Inspect:** Flask, Jinja, Click, Sentry, MiniJinja, and engineering essays.
**Public evidence:** [Projects and open-source work](https://lucumr.pocoo.org/projects/), [engineering writing](https://lucumr.pocoo.org/).
**Adopt:** Build small components with clear responsibilities; reuse tools only when they reduce real complexity; investigate runtime behavior and costs; publish experiments and limitations; stay skeptical of attractive abstractions.
**For us:** Before adding a framework, queue, vector database, or agent layer, write down the concrete problem it solves and the simplest alternative.

### 8. Pieter Levels — fast MVPs and demand validation
**Inspect:** Small products, launch pages, and writing about MVPs.
**Public evidence:** [How I build MVPs](https://levels.io/how-i-build-my-minimum-viable-products/), [long-form interview](https://lexfridman.com/pieter-levels-transcript/).
**Adopt:** Choose a narrow audience; launch a small useful version quickly; avoid building features before demand evidence; plan how users will discover the product; learn from failed attempts.
**For us:** Target a credible demo or first-user release in days/weeks, not months of speculative architecture.
**Caution:** Don't copy his business model, stack, revenue, or risk tolerance. MVP never excuses insecure data handling or untested critical behavior.

### 9. Andrej Karpathy — first-principles understanding and hands-on AI experiments
**Inspect:** Zero to Hero, micrograd, the from-scratch Bitcoin walkthrough, and his talk on software changing with LLMs.
**Public evidence:** [Personal site and learning material](https://karpathy.ai/), [technical blog](https://karpathy.github.io/), [Software Is Changing (Again)](https://www.youtube.com/watch?v=LCEmiRjPEtQ).
**Adopt:** Build simplified versions of important mechanisms; understand the underlying model rather than only calling a library; test intuitions with small experiments; treat AI as a new programming interface while recognizing its fallibility.
**For us:** Pair AI-assisted delivery with a weekly from-first-principles exercise: implement a tiny version, inspect behavior, explain limitations.
**Caution:** Research-scale AI projects aren't the fastest route to every backend goal; match depth to the current problem.

### 10. Ryan Dahl — runtime design, security defaults, learning from limitations
**Inspect:** Node.js history, Deno design decisions, permissions, built-in TypeScript/testing, and compatibility trade-offs.
**Public evidence:** [Why the creator of Node.js built Deno](https://stackoverflow.blog/2024/03/19/why-the-creator-of-node-js-r-created-a-new-javascript-runtime/), [Deno engineering and product blog](https://deno.com/blog).
**Adopt:** Identify limitations in developer experience; turn them into explicit design goals; make safe behavior easier by default; reduce unnecessary choices when an integrated solution is better.
**For us:** Document one or two non-functional requirements—security, portability, latency, operability—before selecting the stack.
**Caution:** Rebuilding a runtime is not a project template. Copy the disciplined problem framing, not the scope.

## Shared patterns worth copying
1. Start from a concrete pain. Prefer a problem you or an identifiable user repeatedly experiences.
2. Narrow scope aggressively: one audience, one main workflow, one measurable result.
3. Prototype to answer questions and reduce uncertainty before committing to a large design.
4. Ship a vertical slice: a complete thin path beats a broad collection of unfinished components.
5. Use feedback as evidence: observe usage, errors, edits, retention, or task completion—not compliments alone.
6. Keep engineering fundamentals: read diffs, test critical behavior, protect secrets/data, inspect logs, understand failure modes.
7. Use AI as leverage, not an excuse to abdicate judgment. Delegate bounded work, give context, inspect changes, run checks, own the result.
8. Maintain what you release: setup docs, release notes, issue handling, reliable upgrades.
9. Publish proof: working demo, commit history, tests, design notes, benchmark, or postmortem.
10. Finish before expanding. Do not collect role models, frameworks, or projects instead of shipping.

## Reverse-engineering protocol (45 minutes maximum per study)
1. **5 min — identify the artifact:** Find the repo, product, release, or technical article.
2. **10 min — inspect evidence:** Read README/docs, design notes, release history, tests, issues, and a few commits if public.
3. **10 min — reconstruct workflow:** Problem → smallest version → validation → release → maintenance. Mark unknowns as unknown; don't invent private practices.
4. **10 min — extract one practice:** State the principle, evidence, trade-off, and when it wouldn't apply.
5. **10 min — apply it:** Use the principle in our active project, create a tiny experiment, or write a decision note.
6. Stop. No biography rabbit holes.

## How we will use this list
- Keep all 10 as a stable role-model list; revisit only when a concrete question makes one relevant.
- Study at most one builder in a week, and only after completing the day's locked learning commitments.
- Never add a project because a role model launched one.
- Role-model research is not project progress unless it produces an artifact or applied decision.
- Weekly output remains one implemented/tested project slice and honest evidence in PROGRESS.md.

## Source-quality rule
Prefer primary evidence: the person's own technical writing, official project documentation, public repositories, release notes, and direct interviews. Treat media summaries and claims about private company workflows as lower confidence. Distinguish individual work from team work. These are transferable interpretations of public evidence, not claims that we know private day-to-day routines.
