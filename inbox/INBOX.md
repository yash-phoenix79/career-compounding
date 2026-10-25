# Inbox

Dump things here quickly. No formatting required.

---

## 2026-10-25 — Learning capture: Backend (high level)
- **What I learned:** Studied backend engineering at a high level.
- **Topic area:** Engineering mastery → Backend engineering / system design.
- **Details to fill in:** Specific concepts covered, key takeaways, open questions, and one practical application or experiment.
- **Next step:** Expand this capture with the actual concepts learned, then move durable notes into the relevant knowledge/roadmap section.

## 2026-10-25 — Learning capture: AI engineering layers and reasoning models
- **Resource:** [Building Reasoning Models — Sebastian Raschka](https://magazine.sebastianraschka.com/p/building-reasoning-models)
- **Core takeaway:** AI engineering has several layers:
  1. **AI application engineering:** Build products using existing model APIs, structured outputs, embeddings, and RAG.
  2. **AI systems engineering:** Build reliable AI workflows and agents, including tool use, evaluations, observability, and production reliability.
  3. **AI model engineering:** Study model internals, fine-tuning, training, reinforcement learning, reasoning, and optimization.
- **What the article is about:** Hands-on techniques for developing and evaluating reasoning models, including generating multiple candidate answers, reinforcement learning, answer critique/refinement, and distilling knowledge from larger models into smaller ones.
- **Important distinction:** An LLM is the model; a reasoning model is trained to solve harder problems more effectively; an AI agent is a larger system that combines a model with tools and other software.
- **Career implication:** Building useful AI applications does not require training a model from scratch. Model-training knowledge is a deeper specialization to explore later.
- **Current priority — do not get distracted:** Focus on **backend engineering from first principles and low-level design (LLD)**. Build fundamentals before pursuing AI engineering/model training.
- **Next step:** Continue studying backend fundamentals and LLD; keep this AI engineering resource in the inbox for later, not as a current learning task.

## 2026-10-25 — Resource capture: bbtree and high-performance data structures
- **X post:** [Xiangpeng Hao (@MOVNTDQ) — post shared for review](https://x.com/MOVNTDQ/status/2114045515876995111)
  - The post itself could not be reliably retrieved, so keep the original link for later inspection rather than guessing its exact claims.
- **Article:** [bbtree: fastest ordered map — Xiangpeng Hao](https://bbtree.xiangpeng.systems/post/)
  - **Topic:** Building a high-performance B-tree / ordered map, relevant to backend, databases, storage engines, and systems programming.
  - **Key ideas to study:** B-trees and ordered maps; cache locality and CPU cache lines; SIMD-based search; concurrency and cache-coherence costs; version-lock/optimistic reads; memory reclamation; memory-mapped data structures.
  - **Database applications discussed:** Replacing skiplists in LSM-tree memtables, in-memory database indexes, and memory-mapping an index to avoid rebuilding it after restart.
  - **Correctness lesson:** Performance alone is not enough. The project describes combining human design accountability with fuzzing, formal verification, deterministic simulation testing, and broad testing.
  - **Critical reading note:** Treat performance figures as the author's reported benchmarks; results depend on hardware, workload, baselines, and integration. Reproduce or inspect benchmark methodology before generalizing.
- **Why it matters for my backend fundamentals:** This is a concrete systems case study connecting data structures, CPU/memory behavior, concurrency, storage engines, and correctness.
- **Current priority:** Save this as a future study resource. Continue focusing on **backend engineering from first principles and LLD**; do not let a new systems rabbit hole displace the current plan.
- **Possible later exercise:** Explain how a B-tree differs from a hash map and skiplist, then implement or benchmark a small ordered index and document the trade-offs.
