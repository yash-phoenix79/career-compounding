# Engineering Resource Library

**North star:** Become an exceptional engineer who can understand systems from first principles, design and implement them, debug failures, operate them reliably, and build useful AI-powered products. **SDE-2 is the near-term milestone, not the ceiling.**

This is a reference library, not a consumption checklist. The locked operating contract is **daily Backend from First Principles + daily LLD practice + daily AI knowledge, plus a tangible project contribution every weekend**. Keep increments small and evidence-based.

## 1. Locked daily and weekend anchors

### Every day
1. **Backend from First Principles:** https://backend-from-first-principle.vercel.app/ — study the next concept and connect it to a small implementation, experiment, or written explanation.
2. **LLD practice:** continue the current exercise. Start with library-management requirements, then model responsibilities, implement in Java, test, and document trade-offs.
3. **AI knowledge:** https://aiengineeringfromscratch.com/ — study one small concept and capture a practical takeaway. Use the other AI references below when directly relevant.

### Every weekend
4. **Project contribution:** make one tangible contribution to one active project: implement a feature slice, fix a bug, add tests, improve reliability, document an architecture decision, or make a meaningful open-source contribution. Prefer the existing active project; do not start a new project just to satisfy this.

### Execution constraints
- Aim for 60 minutes total on normal days; maximum planned learning is 90 minutes. Keep the three daily increments focused and small.
- On a difficult day, do 5–15 minutes per area or record a concrete takeaway and next action if energy is very low. Resume the next day.
- A project contribution should leave reviewable evidence: a commit, tested change, demo, or documented decision.
- Update `PROGRESS.md`. Passive reading/watching alone is not completion.
- Protect sleep and job delivery. Do not compensate for missed work with all-nighters.

## 2. DSA and interview problem-solving

- LeetCode: https://leetcode.com/
- NeetCode: https://neetcode.io/
- NeetCode 150: https://neetcode.io/practice
- AlgoMaster: https://algomaster.io/
- Striver's A2Z DSA Course: https://takeuforward.org/strivers-a2z-dsa-course/
- LeetCode Discuss / interview discussions: https://leetcode.com/discuss/

**Topics:** complexity analysis; arrays and strings; hashing; two pointers; sliding windows; binary search; linked lists; stacks and queues; trees; heaps; recursion and backtracking; graphs; greedy algorithms; dynamic programming; tries; union-find; intervals; monotonic stacks.

**Practice rule:** Use C++ for DSA. Prioritise understanding, correctness, complexity, explaining the approach, and revisiting failed problems over chasing a problem count. DSA remains a supporting SDE-2 workstream.

## 3. LLD, OOP, design patterns, and machine coding

- Refactoring.Guru: https://refactoring.guru/
- Awesome Low Level Design: https://github.com/ashishps1/awesome-low-level-design
- Java Design Patterns: https://github.com/iluwatar/java-design-patterns
- Design Patterns roadmap: https://roadmap.sh/design-patterns
- Java learning: https://dev.java/learn/

**Topics:** requirements and use cases; object responsibilities; encapsulation; abstraction; inheritance versus composition; interfaces; SOLID; dependency inversion; design patterns and their costs; validation; error handling; testability; refactoring; concurrency where relevant.

**Practice systems:** library management; parking lot; Splitwise-style expense manager; movie ticket booking; elevator; notification service; rate limiter; task scheduler; cache; logging framework.

**Exercise loop:** requirements → object model → interfaces → implementation → tests → critique → refactor. Implement in Java. Do not memorise class diagrams without writing working code.

## 4. Backend, Java, APIs, and developer tools

- Backend from First Principles: https://backend-from-first-principle.vercel.app/
- Dev.java: https://dev.java/learn/
- Java Tutorials: https://docs.oracle.com/javase/tutorial/
- Java API documentation: https://docs.oracle.com/en/java/javase/
- Spring Guides: https://spring.io/guides
- Spring Boot documentation: https://docs.spring.io/spring-boot/index.html
- Baeldung: https://www.baeldung.com/
- Git documentation: https://git-scm.com/doc
- Linux Journey: https://linuxjourney.com/
- Docker documentation: https://docs.docker.com/
- GitHub Actions: https://docs.github.com/en/actions

**Topics:** HTTP; REST; DNS and networking; API contracts; Java collections and generics; exceptions and resource management; streams and lambdas; concurrency; JVM and garbage collection; dependency injection; persistence; transactions; authentication and authorisation; testing; configuration; deployments; Git; Linux; containers; CI/CD.

## 5. Computer science foundations

- Teach Yourself Computer Science: https://teachyourselfcs.com/
- OSSU Computer Science: https://github.com/ossu/computer-science
- Harvard CS50: https://cs50.harvard.edu/x/
- Operating Systems: Three Easy Pieces: https://pages.cs.wisc.edu/~remzi/OSTEP/
- MIT Operating System Engineering: https://pdos.csail.mit.edu/6.1810/
- Computer Networking: A Top-Down Approach resources: https://gaia.cs.umass.edu/kurose_ross/index.php
- Beej's Guide to Network Programming: https://beej.us/guide/bgnet/
- MDN HTTP overview: https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview
- CMU Database Systems: https://15445.courses.cs.cmu.edu/
- PostgreSQL documentation: https://www.postgresql.org/docs/
- Use The Index, Luke!: https://use-the-index-luke.com/

**Topics:** processes and threads; scheduling; virtual memory; synchronisation; TCP/IP; DNS; TLS; HTTP; sockets; database indexes; transactions; isolation; locks; query plans; storage; replication.

Use these as a gap-driven reference. Do not enrol in every curriculum simultaneously.

## 6. HLD and system design

- System Design Primer: https://github.com/donnemartin/system-design-primer
- ByteByteGo: https://bytebytego.com/
- Gaurav Sen: https://www.youtube.com/@gkcs
- Hello Interview: https://www.hellointerview.com/

**Topics:** requirements; capacity estimates; APIs; data modelling; SQL versus NoSQL; caching; load balancing; scaling; replication; partitioning; queues; consistency; idempotency; retries; rate limiting; security; observability; fault tolerance; cost, latency, and throughput trade-offs.

**Practice systems:** URL shortener; news feed; chat; notification platform; file storage; search autocomplete; ride-hailing; video streaming; e-commerce order processing; distributed task scheduler.

Start from requirements and constraints. Derive the architecture instead of reciting a memorised answer.

## 7. Distributed systems, data infrastructure, and reliability

- Designing Data-Intensive Applications: https://dataintensive.net/
- Martin Kleppmann's site: https://martin.kleppmann.com/
- MIT Distributed Systems: https://pdos.csail.mit.edu/6.824/
- Gossip Glomers: https://fly.io/dist-sys/
- Jepsen / Maelstrom: https://github.com/jepsen-io/maelstrom
- Apache Kafka: https://kafka.apache.org/documentation/
- Redis: https://redis.io/docs/
- Kubernetes: https://kubernetes.io/docs/home/
- gRPC: https://grpc.io/docs/
- Google SRE books: https://sre.google/books/
- Google Engineering Practices: https://google.github.io/eng-practices/
- The Twelve-Factor App: https://12factor.net/
- OpenTelemetry: https://opentelemetry.io/docs/

**Topics:** replication; partitioning; consensus; distributed transactions; delivery semantics; event ordering; consistency; leader election; timeouts; retries; backpressure; queues; stream processing; distributed locks; logs, metrics, traces; SLOs/SLIs; incident response; rollbacks; disaster recovery.

Learn a technology when you understand the problem it solves. Avoid collecting infrastructure tools as badges.

## 8. Build real systems from scratch and read architectures

- CodeCrafters: https://codecrafters.io/
- Build Your Own X: https://github.com/codecrafters-io/build-your-own-x
- Architecture of Open Source Applications: https://aosabook.org/en/
- GitHub Explore: https://github.com/explore

**Project ideas:** URL shortener; rate limiter; Redis-like cache; task queue; notification service; search service; file storage service; event-driven order system; observability service; AI research assistant.

For each project, produce a problem statement, requirements/non-goals, architecture, API and data models, implementation, automated tests, logging/error handling, README, trade-off notes, and (where appropriate) a deployed demo. Keep one main project active at a time.

## 9. AI engineering and agentic systems

- AI Engineering from Scratch: https://aiengineeringfromscratch.com/
- OpenAI Cookbook: https://cookbook.openai.com/
- OpenAI API docs: https://platform.openai.com/docs/
- Anthropic documentation: https://docs.anthropic.com/
- Anthropic Cookbook: https://github.com/anthropics/anthropic-cookbook
- Hugging Face Learn: https://huggingface.co/learn
- LlamaIndex: https://docs.llamaindex.ai/
- LangGraph: https://docs.langchain.com/oss/python/langgraph/overview
- Full Stack Deep Learning: https://fullstackdeeplearning.com/
- Practical guide to building AI agents: https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/

**Topics:** model APIs; prompting and context; structured outputs; tool calling; embeddings; vector search; RAG; workflows and orchestration; state and memory; evaluation; hallucination and failure handling; prompt injection; permissions; latency/cost; caching; tracing; model selection; human approval.

**Project ideas:** document research assistant; codebase Q&A; debugging assistant; multi-source research pipeline; bounded agent workflow with approval; model/prompt evaluation harness; personal knowledge retrieval; financial research assistant.

Prefer deterministic workflows when they are simpler. Any agent should have limited tools, explicit state and step bounds, tests/evaluations, failure handling, and approval for consequential actions.

## 10. Existing AI/finance repositories to study

These are exploratory examples, not part of the immediate daily syllabus. Check their current maintenance, dependencies, and licence before adopting them.

- AI Hedge Fund: https://github.com/virattt/ai-hedge-fund
- TradingAgents: https://github.com/TauricResearch/TradingAgents
- Microsoft Qlib: https://github.com/microsoft/qlib
- Fincept Terminal: https://github.com/Fincept-Corporation/FinceptTerminal
- ValueCell: https://github.com/ValueCell-ai/valuecell

Study one end-to-end workflow: entry point, data flow, business logic, model invocation, persistence, tests, and error handling. Do not merely read the README.

## 11. Engineering blogs and technical judgment

- Netflix TechBlog: https://netflixtechblog.com/
- Uber Engineering: https://www.uber.com/blog/engineering/
- Cloudflare Blog: https://blog.cloudflare.com/
- AWS Architecture Blog: https://aws.amazon.com/blogs/architecture/
- GitHub Engineering: https://github.blog/engineering/
- Martin Fowler: https://martinfowler.com/

Read in response to a concept or problem you are working on. Capture the problem, constraints, solution, alternatives, and trade-offs. Avoid endless browsing.

## 12. Books and references

- *A Philosophy of Software Design* — John Ousterhout: https://web.stanford.edu/~ouster/cgi-bin/book.php
- *Effective Java* — Joshua Bloch.
- *Refactoring* — Martin Fowler: https://martinfowler.com/books/refactoring.html
- *Designing Data-Intensive Applications* — Martin Kleppmann: https://dataintensive.net/
- *Fundamentals of Software Architecture* — Mark Richards and Neal Ford.
- *Release It!* — Michael T. Nygard.
- *System Design Interview* — Alex Xu.
- *Database Internals* — Alex Petrov.
- *The Pragmatic Programmer* — Andrew Hunt and David Thomas.
- *Site Reliability Engineering* — Google: https://sre.google/books/

Suggested progression: *A Philosophy of Software Design* → *Effective Java* → *Refactoring* → *Designing Data-Intensive Applications* → *Release It!*. Read interview-oriented books when actively preparing; use deeper internals books when relevant.

## 13. SDE-2 interview preparation

- LeetCode: https://leetcode.com/
- NeetCode: https://neetcode.io/
- Hello Interview: https://www.hellointerview.com/
- Pramp: https://www.pramp.com/
- GeeksforGeeks interview experiences: https://www.geeksforgeeks.org/interview-experiences/

Prepare coding, LLD, HLD, project deep dives, behavioural stories, and clear communication. Start mock interviews before you feel completely ready. Build evidence of ownership, technical judgement, reliable execution, and handling ambiguity in your current role.

## 14. Public presence and learning in public

- X: https://x.com/
- GitHub: https://github.com/
- Hacker News: https://news.ycombinator.com/
- DEV Community: https://dev.to/

Share actual work: a design trade-off, a debugging investigation, a measured performance improvement, a project, or a lesson from a codebase. Let engineering work generate posts; do not let content creation become a competing project.

## 15. Separate finance learning track

- Zerodha Varsity: https://zerodha.com/varsity/

Finance and AI/finance repositories are secondary to the current engineering loop. Keep them in their own track until the core daily routine is stable.

## 16. Canonical progress files

- Roadmap: [ROADMAP.md](ROADMAP.md)
- Progress log: [PROGRESS.md](PROGRESS.md)
- Resource library: [RESOURCE_LIBRARY.md](RESOURCE_LIBRARY.md)
- Repository: https://github.com/yash-phoenix79/career-compounding
