# Curriculum and Source Map

## Primary sources

### A. Video series — three-phase journey

[YouTube playlist entry](https://www.youtube.com/watch?v=6Ss4dJD9Kzg&list=PLui3EUkuMTPgZcV0QhQrOcwMPcBCcd_Q1&index=3)

The instructor's framing:
1. Story & Philosophy — language-agnostic understanding and common patterns.
2. Implementation — concept-by-concept deep dives in a chosen language and ecosystem; the instructor mentioned Node.js and Go.
3. Production — end-to-end production-grade projects combining the principles and implementations.

The introductory transcript shared in this project supports this three-phase structure. We will capture each lesson from its actual transcript/video rather than infer unseen content from the playlist title.

### B. Written reference — 27 chapters

[Backend, from First Principles](https://backend-from-first-principle.vercel.app/)

The site describes itself as a 27-chapter engineering reference with diagrams and runnable Go/Python examples. Its curriculum is organized into these groups:

| Group | Chapters | Coverage |
|---|---:|---|
| The Request Path | 01–07 | HTTP & CORS; routing; serialization/deserialization; authentication & authorization; validations & transformations; controllers, services & middleware; REST API design |
| State & Machinery | 08–14 | Databases; caching; task queues & background jobs; full-text search; error handling & fault tolerance; gRPC & inter-service communication; configuration management |
| Running in Production | 15–20 | Logging & observability; graceful shutdown; backend security; scaling & performance I; scaling & performance II; concurrency & parallelism |
| Distribution & Scale | 21–24 | Docker, Kubernetes & CI/CD; automated testing; message brokers & Kafka; WebSockets & real-time systems |
| OpenAPI & AI Agents | 25–26 | OpenAPI & documentation; AI agents & loop engineering |
| System Design | 27 | URL shortener system design |

The written reference and video series are complementary, not assumed to be identical. Verify exact chapter contents when studying them.

## Recommended progression

Use the video series' three phases as the learning architecture. Use the 27-chapter site as a topic reference and implementation aid.

### Phase 1 — Story & Philosophy
Build language-independent understanding:
- Request/response and client-server architecture.
- Network and HTTP fundamentals.
- Routing and serialization.
- Identity, permissions, validation, and request lifecycle.
- API design and application boundaries.
- Persistence, transactions, caching, and asynchronous work.
- Reliability, observability, security, concurrency, and scale.

### Phase 2 — Implementation
For each concept, implement a small slice and understand the language/runtime ecosystem. Choose language based on learning value:
- **Java:** priority for direct transfer to the user's backend career and production work.
- **Go:** useful for concurrency, networking, services, and comparison with explicit systems concepts.
- **Python / JavaScript / TypeScript:** use when the reference material or a specific experiment benefits from them.

Do not learn multiple languages in parallel just for breadth. Understand the concept once, then compare implementations selectively.

### Phase 3 — Production
Integrate concepts into end-to-end systems:
- Define requirements, boundaries, data model, and contracts.
- Implement core flows and persistence.
- Add auth, validation, failure handling, and tests.
- Add observability, deployment, graceful shutdown, and security.
- Exercise load, concurrency, partial failures, and recovery.
- Document design decisions and operational runbooks.

## Topic dependency guidance

This is a suggested dependency map, not a rigid schedule:

1. **Machine and network foundations:** bytes, processes, sockets, TCP, DNS, TLS, HTTP.
2. **Request processing:** routing, serialization, middleware, context, validation.
3. **Application design:** handlers/controllers, services, domain logic, API contracts.
4. **Persistence:** relational modeling, SQL, indexes, transactions, isolation, migrations, connection pools.
5. **Performance and async:** caching, queues, search, streaming, concurrency.
6. **Reliability and security:** timeouts, retries, idempotency, fault tolerance, auth, authorization, threat modeling.
7. **Production operation:** observability, configuration, graceful shutdown, containers, CI/CD, testing, deployment.
8. **Distributed system design:** partitioning, replication, consistency, event streaming, real-time systems, scaling trade-offs.

Return to prerequisites when a later topic exposes a gap. The sequence should serve understanding, not become a checklist to rush through.
