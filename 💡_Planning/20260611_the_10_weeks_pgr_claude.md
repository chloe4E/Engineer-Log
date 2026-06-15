Here's a structured 2.5-month program — roughly 10 weeks, 5 days a week, ~1 hour per session. The philosophy is: weeks 1–4 reinforce fundamentals and Java fluency, weeks 5–8 go deep on distributed systems with your books, and weeks 9–10 simulate real interviews.Every card above is clickable — it will send the relevant prompt directly into our chat so you can dive into any session on the day.

Here's how the overall structure works:

**Phase 1 (weeks 1–4)** is about making Java feel effortless and shoring up CS fundamentals — the kind of stuff that trips people up in coding screens even when they know it. You'll touch collections, concurrency, algorithms, OOP patterns, and databases, with Codewars practice woven in from day one.

**Phase 2 (weeks 5–8)** is the intellectual core. DDIA is one of the best books ever written for senior engineers, and you'll read it systematically — not as a speed-run but with dedicated days for interview Q&A after each section. Alex Xu Vol.2 then gives you structured practice applying the theory to concrete design problems. Each chapter maps to a realistic interview question.

**Phase 3 (weeks 9–10)** flips the mode entirely. You stop studying and start performing — full timed mocks, gap-closing, and behavioural prep.

**On your one hour a day:** reading days are about depth, not speed — read slowly and take notes. Coding days should be done on Codewars before looking at any solution. Mock days work best if you actually talk through your answer out loud, since interviewers care a lot about your reasoning process.

**For podcasts**, I'd recommend Waveform / The Changelog for general tech awareness, and the Software Engineering Daily back catalogue for deep dives on specific systems (Kafka, Cassandra, distributed tracing etc.) — these map well to what you'll be reading in DDIA.

# Senior Back-End Engineer Interview Prep — 10-Week Program

**Language:** Java  
**Duration:** 10 weeks · 5 days/week · ~1 hour/day  
**Resources:** DDIA (Martin Kleppmann) · System Design Interview Vol.2 (Alex Xu) · Codewars  
**Goal:** Reinforce engineering fundamentals and be fully ready for a senior back-end interview

---

## How to use this program

- **Reading days** — go slowly, take notes in your own words. Understanding > coverage.
- **Coding days** — attempt the problem on Codewars *before* looking at solutions or asking for hints. Struggle is the point.
- **Design days** — talk through your answer out loud, as if in a real interview. Structure: clarify requirements → estimate scale → propose high-level design → drill into components → discuss trade-offs.
- **Mock days** — treat them as real interviews. No notes, no looking things up mid-session.
- **Review/quiz days** — write down what you got wrong. Keep a running "weak spots" list.

---

## Podcast recommendations

Listen during commutes, walks, or chores.

| Podcast | Best for |
|---|---|
| Software Engineering Daily | Deep dives on Kafka, Cassandra, distributed tracing — maps directly to DDIA topics |
| The Changelog | General tech awareness, engineering culture |
| Waveform / TLDR Tech | Staying current on the industry |
| Corecursive | In-depth engineer stories, useful for behavioural prep inspiration |

---

## Phase 1 — Weeks 1–4: Foundations

> Goal: Java fluency, CS fundamentals, and database basics. These underpin everything in phases 2 and 3.

---

### Week 1 — Java & Data Structures

**Theme:** Get comfortable with idiomatic Java before touching any system design.

#### Monday — Java generics & collections

**Topics:**
- Generics: type bounds (`<T extends Comparable<T>>`), wildcards (`? extends`, `? super`)
- Collections hierarchy: `List`, `Set`, `Map`, `Queue`, `Deque`
- When to use `ArrayList` vs `LinkedList` vs `ArrayDeque`
- `HashMap` internals: hash function, buckets, load factor, resizing
- `TreeMap` vs `HashMap` vs `LinkedHashMap`

**Practice:**
- Write a generic `Pair<A, B>` class with a static factory method
- Implement a frequency counter using `HashMap` (e.g. count word occurrences in a string)

**Key interview questions to be able to answer:**
- What is the time complexity of `HashMap.get()` in the worst case?
- Why would you choose `LinkedHashMap` over `HashMap`?

---

#### Tuesday — Streams & lambdas

**Topics:**
- Functional interfaces: `Function`, `Predicate`, `Supplier`, `Consumer`
- Stream pipeline: `filter`, `map`, `flatMap`, `reduce`, `collect`
- `Collectors`: `toList`, `groupingBy`, `partitioningBy`, `joining`
- Optional: avoiding null, chaining with `map` and `orElse`
- Method references: `ClassName::method`
- Parallel streams: when they help and when they hurt

**Practice:**
- Given a list of orders, group them by customer and compute the total value per customer — using only streams
- Rewrite the same logic imperatively and compare readability

**Key interview questions:**
- What is a terminal vs intermediate operation?
- When would parallel streams reduce performance?

---

#### Wednesday — Arrays & hashmaps (Codewars)

**Focus:** Two-pointer, sliding window, and hashmap-based patterns.

**Codewars targets (7–6 kyu):**
- Two sum (find two numbers that add to a target)
- Longest substring without repeating characters
- Group anagrams together

**Technique notes:**
- Two-pointer works on sorted arrays — always ask "can I sort this first?"
- Sliding window keeps O(n) what would otherwise be O(n²)
- HashMap trades space for time — learn to spot when this swap is worth it

---

#### Thursday — Concurrency basics

**Topics:**
- `Thread`, `Runnable`, `Callable`, `Future`
- `ExecutorService` and thread pools: `newFixedThreadPool`, `newCachedThreadPool`
- `synchronized` keyword: method-level and block-level
- `volatile`: visibility guarantee, not atomicity
- `AtomicInteger`, `AtomicReference` from `java.util.concurrent.atomic`
- `ReentrantLock` vs `synchronized`
- Common pitfalls: race conditions, deadlock, livelock

**Practice:**
- Implement a thread-safe counter using three approaches: `synchronized`, `AtomicInteger`, and `ReentrantLock`
- Identify the bug in a given double-checked locking snippet

**Key interview questions:**
- What is the difference between `volatile` and `synchronized`?
- How does a thread pool prevent thread creation overhead?

---

#### Friday — Week review & quiz

**Self-quiz (write answers before checking):**
1. What is the time complexity of `TreeMap.get()`?
2. What does `flatMap` do that `map` cannot?
3. What happens if two threads simultaneously call `hashMap.put()` without synchronisation?
4. When should you use `ConcurrentHashMap` instead of `HashMap`?
5. What is the difference between `Callable` and `Runnable`?

**Action:** Add any questions you struggled with to your "weak spots" list.

---

### Week 2 — Algorithms & Complexity

**Theme:** The vocabulary of coding interviews. Not about memorising solutions — about recognising patterns.

#### Monday — Big O deep dive

**Topics:**
- Time complexity: O(1), O(log n), O(n), O(n log n), O(n²), O(2ⁿ)
- Space complexity: in-place vs auxiliary space
- Amortised analysis: why `ArrayList.add()` is O(1) amortised
- How to derive complexity by counting loop iterations
- Common traps: hidden O(n) inside a loop that looks O(1)

**Practice:**
- Annotate 5 code snippets with their time and space complexity (write these yourself first)
- Find the complexity of: binary search, BFS, merge sort, quicksort worst case

---

#### Tuesday — Sorting algorithms

**Topics:**
- Merge sort: divide and conquer, stable, O(n log n) always, O(n) space
- Quick sort: pivot selection, O(n log n) average, O(n²) worst, in-place
- Heap sort: O(n log n) always, in-place, not stable
- Counting sort / Radix sort: O(n + k), when the range of values is bounded
- Java's `Arrays.sort()`: uses TimSort for objects, dual-pivot quicksort for primitives

**Practice:**
- Implement merge sort in Java from memory
- Given an array of objects, sort by multiple fields using `Comparator.comparing().thenComparing()`

**Key interview questions:**
- Why does Java use TimSort for object arrays?
- In what scenario would you reach for counting sort over merge sort?

---

#### Wednesday — Trees & binary search (Codewars)

**Codewars targets (6 kyu):**
- Validate a binary search tree
- Find the lowest common ancestor of two nodes
- Binary search on a sorted array — implement without a library

**Technique notes:**
- BST invariant: left < root < right at *every* node, not just adjacent ones
- Recursive tree traversals: pre-order (root, left, right), in-order (left, root, right), post-order (left, right, root)
- In-order traversal of a BST produces sorted output

---

#### Thursday — Graphs: BFS & DFS

**Topics:**
- Representations: adjacency list (preferred) vs adjacency matrix
- BFS: queue-based, shortest path in unweighted graphs, level-order traversal
- DFS: stack-based (or recursive), cycle detection, topological sort
- Topological sort: Kahn's algorithm (BFS-based) and DFS-based
- Connected components, strongly connected components

**Where these appear in backend systems:**
- Dependency resolution (build systems, package managers) — topological sort
- Crawlers and link analysis — BFS
- Fraud detection and social graphs — connected components

**Practice:**
- Implement BFS and DFS for a graph represented as `Map<Integer, List<Integer>>`
- Detect a cycle in a directed graph

---

#### Friday — Mixed challenge

**Challenge:** Given a list of tasks with dependencies (e.g. `[[1,0],[2,1],[3,2]]`), determine a valid execution order. If a cycle exists, return an empty list.

This is a real interview problem (LeetCode 207/210 style). It combines graph representation, topological sort, and cycle detection — all from this week.

**Review:** Write out your time and space complexity analysis before checking.

---

### Week 3 — OOP, Design Patterns & Spring

**Theme:** What separates a senior engineer from a mid-level one is knowing *why* code is structured the way it is.

#### Monday — SOLID principles

**For each principle, learn: the rule, a violation example, and the fix.**

| Principle | One-line rule | Classic Java violation |
|---|---|---|
| Single Responsibility | A class has one reason to change | A `UserService` that also sends emails |
| Open/Closed | Open for extension, closed for modification | A `switch` on type that grows with every new type |
| Liskov Substitution | Subtypes must be substitutable for base types | A `Square extends Rectangle` that breaks area logic |
| Interface Segregation | Don't force clients to depend on methods they don't use | A fat `Animal` interface with `fly()` and `swim()` |
| Dependency Inversion | Depend on abstractions, not concretions | `new MySQLRepository()` hardcoded inside a service |

**Practice:** Refactor a `UserService` class that violates at least three of these principles.

---

#### Tuesday — Design patterns

**Must-know for senior interviews:**

**Creational:**
- Factory Method — decouple object creation from usage. Example: `PaymentProcessorFactory.create("stripe")`
- Builder — construct complex objects step by step. Example: `HttpRequest.Builder`
- Singleton — single instance, thread-safe with double-checked locking or `enum`

**Structural:**
- Decorator — add behaviour without subclassing. Example: Java I/O streams
- Proxy — control access to an object. Example: Spring AOP, lazy loading

**Behavioural:**
- Strategy — swap algorithms at runtime. Example: different sorting or pricing strategies
- Observer — notify subscribers of state changes. Example: event listeners, reactive streams
- Command — encapsulate requests as objects. Example: undo/redo, job queues

**Practice:** Implement a `Strategy` pattern for a payment system that supports `CreditCard`, `PayPal`, and `Crypto` — without `if/else` or `switch`.

---

#### Wednesday — Spring Boot & IoC

**Topics:**
- Inversion of Control (IoC): the framework creates and wires objects, not your code
- Dependency Injection: constructor injection (preferred) vs field injection vs setter injection
- `@Component`, `@Service`, `@Repository`, `@Controller` — stereotype annotations
- `@Bean` and `@Configuration` — programmatic bean definition
- `@Transactional`: propagation levels, rollback rules, proxy pitfalls (calling a `@Transactional` method from within the same class bypasses the proxy)
- Spring's request lifecycle for a REST endpoint

**Key interview questions:**
- Why is constructor injection preferred over field injection?
- What happens if you call a `@Transactional` method from another method in the same class?
- What is a Spring Bean scope? What is the difference between `singleton` and `prototype`?

---

#### Thursday — OOP design challenge (Codewars)

**Design challenge:** Model a parking lot system in Java.

Requirements: multiple levels, multiple spot sizes (compact, regular, large), vehicles of different sizes (motorcycle, car, bus). Implement `park(Vehicle v)` and `leave(Vehicle v)`.

Focus on: which classes you create, which interfaces you define, how you avoid `instanceof` checks, and how you'd extend this for a new vehicle type without modifying existing code.

---

#### Friday — Review & quiz

**Self-quiz:**
1. What design pattern does `java.util.Collections.sort()` use when accepting a `Comparator`?
2. Name two Spring proxy limitations and how to work around them.
3. How would you implement a thread-safe Singleton without `synchronized`?
4. Which SOLID principle does the Open/Closed principle most directly enable?

---

### Week 4 — Databases & Caching

**Theme:** Every senior back-end interview will probe your understanding of databases. This week makes that a strength.

#### Monday — SQL indexes deep dive

**Topics:**
- B-tree indexes: structure, how range queries work, why order matters in composite indexes
- Hash indexes: O(1) point lookup, no range queries
- Composite indexes: column order is critical — leftmost prefix rule
- Covering indexes: the query is satisfied entirely from the index, no table access
- Index selectivity: why `status = 'active'` on a boolean column is often useless
- When indexes hurt: high-write tables, low-selectivity columns, over-indexing

**Practice:**
- Given a slow query, identify which index to add and explain why
- Explain what `EXPLAIN ANALYZE` output tells you

**Key interview questions:**
- A query on `(first_name, last_name)` has a composite index. Will a query filtering only on `last_name` use it?
- What is an index scan vs a sequential scan?

---

#### Tuesday — Transactions & ACID

**Topics:**
- Atomicity: all-or-nothing. Implemented via undo logs.
- Consistency: data moves from one valid state to another. Enforced by constraints.
- Isolation: concurrent transactions don't interfere. Implemented via locking or MVCC.
- Durability: committed data survives crashes. Implemented via WAL (write-ahead log).

**Isolation levels (know all four and what anomaly each prevents):**

| Level | Dirty read | Non-repeatable read | Phantom read |
|---|---|---|---|
| Read uncommitted | ✅ possible | ✅ possible | ✅ possible |
| Read committed | ❌ prevented | ✅ possible | ✅ possible |
| Repeatable read | ❌ prevented | ❌ prevented | ✅ possible |
| Serializable | ❌ prevented | ❌ prevented | ❌ prevented |

**Practice:**
- Write a Java/Spring example where choosing the wrong isolation level causes a bug
- Explain MVCC (Multi-Version Concurrency Control) and why it reduces lock contention

---

#### Wednesday — Caching strategies

**Topics:**
- Cache-aside (lazy loading): app checks cache → miss → load from DB → write to cache. Most common pattern.
- Read-through: cache sits in front of DB, fetches on miss automatically.
- Write-through: every write goes to cache and DB simultaneously. Strong consistency, higher write latency.
- Write-behind (write-back): writes go to cache first, DB asynchronously. High throughput, risk of loss.
- Cache eviction policies: LRU, LFU, TTL-based
- Cache stampede / thundering herd: many simultaneous cache misses on the same key. Solution: mutex lock or probabilistic early expiration.
- Redis vs Memcached: Redis supports richer data structures, persistence, replication.

**Practice:**
- Implement an LRU cache in Java using `LinkedHashMap` with `accessOrder=true`
- Design caching for a product catalogue that gets 10,000 reads/second and updates once an hour

---

#### Thursday — SQL challenge

**Challenge 1:** Window functions  
Given an orders table, rank customers by total spend within each country using `RANK() OVER (PARTITION BY country ORDER BY total_spend DESC)`.

**Challenge 2:** CTE optimisation  
Rewrite a nested subquery as a CTE. Explain when a CTE is optimised away vs materialised by the planner.

**Challenge 3:** ORM context  
Describe the N+1 query problem. Show it occurring with JPA/Hibernate, and fix it with `JOIN FETCH` or `@EntityGraph`.

---

#### Friday — Phase 1 milestone review

**Full review quiz (30 minutes):**
1. What is the time complexity of inserting into a `TreeSet`?
2. What does `volatile` guarantee that `synchronized` does not — and vice versa?
3. Explain the Liskov Substitution Principle with a Java example.
4. What does the leftmost prefix rule mean for composite indexes?
5. What anomaly does "repeatable read" isolation prevent?
6. In cache-aside, who is responsible for populating the cache?
7. What is write skew and which isolation level prevents it?

**Action:** Update your weak spots list. These gaps are what Phase 2 will stress.

---

## Phase 2 — Weeks 5–8: Distributed Systems & System Design

> Goal: Deep understanding of how large-scale systems work, drawn from DDIA and Alex Xu Vol.2. These are the concepts that define a senior engineer.

---

### Week 5 — DDIA Part 1: Data Models & Storage

#### Monday — DDIA Chapters 1–2: Foundations & data models

**Chapter 1 key concepts:**
- Reliability: tolerating hardware faults, software errors, human mistakes
- Scalability: describing load (e.g. Twitter's fan-out problem), latency percentiles (p50, p99, p999)
- Maintainability: operability, simplicity, evolvability

**Chapter 2 key concepts:**
- Relational vs document model: schema-on-write vs schema-on-read
- When document databases fit: self-contained documents, locality, flexible schema
- When relational fits: many-to-many relationships, joins
- Graph databases: property graphs, triple-stores, SPARQL
- Impedance mismatch between object models and relational tables

**Interview takeaway:** Be able to argue when you'd choose relational vs document vs graph for a given problem, with trade-offs.

---

#### Tuesday — DDIA Chapter 3: Storage engines

**Key concepts:**
- Log-structured storage: append-only segments, compaction, Bitcask
- SSTable + LSM-tree: sorted segments, merging, Bloom filters, used by Cassandra, LevelDB, RocksDB
- B-tree: ubiquitous in relational DBs, updates in-place, write-ahead log for crash recovery
- LSM vs B-tree trade-offs: LSM has higher write throughput, B-tree has more predictable read latency
- Column-oriented storage: store each column separately, compression, vectorised processing (OLAP)
- Materialised views and data cubes

**Interview takeaway:** When asked "how does Postgres store data vs Cassandra?", you should be able to explain B-tree vs LSM at a conceptual level.

---

#### Wednesday — Interview Q&A from Chapters 1–3

Work through these questions out loud, as if in an interview:

1. You're building a write-heavy analytics platform. Would you choose a B-tree or LSM-tree based storage engine? Why?
2. Twitter has ~100M users. Each user follows on average 200 accounts. When a user posts a tweet, how would you fan out to followers? What's the trade-off between push (fan-out on write) and pull (fan-out on read)?
3. You have a read-heavy service where 90% of queries access only 3 of 50 columns in a table. What storage optimisation would you recommend?
4. What is the difference between schema-on-read and schema-on-write? When is each preferable?
5. What is a Bloom filter and how does an LSM-tree use it?

---

#### Thursday — DDIA Chapter 4: Encoding & schema evolution

**Key concepts:**
- Formats: JSON/XML (human-readable, no schema enforcement), binary (Thrift, Protocol Buffers, Avro)
- Protocol Buffers: field tags for backward/forward compatibility, required vs optional fields
- Avro: schema must be available at read time, schema resolution between writer/reader schema
- Backward compatibility: new code can read data written by old code
- Forward compatibility: old code can read data written by new code
- Dataflow: databases, service calls (REST/RPC), message-passing

**Interview takeaway:** Rolling deployments require backward *and* forward compatibility. Know how Protobuf field tags make this work.

---

#### Friday — Coding + DDIA link

**Coding challenge:** Implement a simple binary serialiser in Java that encodes a `User` object (id: int, name: string, email: string) using a hand-rolled binary format. Then add a new optional `age` field and ensure old decoders don't break.

This directly exercises Chapter 4's concepts on schema evolution and backward compatibility.

---

### Week 6 — DDIA Part 2: Replication & Partitioning

#### Monday — DDIA Chapter 5: Replication

**Key concepts:**
- Single-leader replication: all writes go to leader, replicated to followers. Failover risks.
- Synchronous vs asynchronous replication: consistency vs availability trade-off
- Replication lag problems:
    - Read-your-own-writes: after writing, you might read a stale replica
    - Monotonic reads: you might see data "going back in time" across different replicas
    - Consistent prefix reads: causally related events appear out of order
- Multi-leader replication: useful for multi-datacenter setups, conflict resolution required
- Leaderless replication (Dynamo-style): quorum reads/writes (r + w > n), sloppy quorum, hinted handoff
- Conflict resolution: last-write-wins (LWW), version vectors, CRDTs

**Interview takeaway:** Know the replication lag anomalies by name and how to mitigate them. Know when to use quorum reads vs strong consistency.

---

#### Tuesday — DDIA Chapter 6: Partitioning (sharding)

**Key concepts:**
- Partitioning by key range: easy range queries, hotspot risk (e.g. timestamp-based keys)
- Partitioning by hash: uniform distribution, no range queries
- Consistent hashing: virtual nodes, minimise rebalancing when nodes join/leave
- Hotspot problem: a celebrity with millions of followers causes uneven writes. Solution: add a random suffix to the hot key.
- Secondary indexes on partitioned data:
    - Local (scatter-gather): each partition indexes its own data, queries must fan out
    - Global (term-partitioned): index is partitioned separately from data, writes touch multiple partitions
- Rebalancing strategies: fixed number of partitions, dynamic partitioning

---

#### Wednesday — Design: globally distributed key-value store

**System design practice.** Work through this in 45 minutes:

**Requirements:**
- 10M writes/day, 100M reads/day
- Sub-10ms p99 read latency
- Multi-region (US, EU, Asia)
- Eventual consistency is acceptable for reads

**Work through:**
1. Choosing a partitioning strategy (hash-based, consistent hashing)
2. Replication topology (leaderless with quorum, or single-leader per region)
3. Handling replication lag and conflict resolution
4. Data model and encoding format
5. How you'd handle a region outage

---

#### Thursday — DDIA Chapter 7: Transactions

**Key concepts:**
- Read committed: default in Postgres and Oracle. Prevents dirty reads and dirty writes.
- Snapshot isolation / Repeatable read: each transaction sees a consistent snapshot. Implemented via MVCC.
- Serializable isolation: three approaches: actual serial execution (VoltDB), two-phase locking (2PL), serializable snapshot isolation (SSI)
- Two-phase locking: readers block writers, writers block readers. Deadlock risk.
- Write skew: two transactions read the same data, both decide to write based on what they read, and the combined effect violates a constraint. Classic example: on-call scheduling.
- Phantoms: a write in one transaction affects a query in another. Predicate locks vs index-range locks.

**Interview takeaway:** Most engineers know ACID but not write skew or how SSI works. Knowing these is a differentiator.

---

#### Friday — Interview Q&A: Chapters 5–7

1. A user submits a payment. Your payment service reads the account balance, then updates it. Two simultaneous requests read the same balance. What anomaly is this and how do you prevent it?
2. Your e-commerce site has product inventory stored in a replicated database. After a user buys an item, another user still sees it as available for 200ms. What replication concept describes this, and how would you fix it if needed?
3. What is the difference between optimistic and pessimistic concurrency control?
4. How does MVCC allow readers and writers to not block each other?
5. You're designing a global leaderboard. Users in different regions write scores. How do you handle conflicting updates?

---

### Week 7 — DDIA Part 3 + Alex Xu Vol.2 Begins

#### Monday — DDIA Chapters 8–9: Faults & consensus

**Chapter 8 key concepts:**
- Partial failures: in distributed systems, some parts can fail while others work — unlike a single computer
- Unreliable networks: packet loss, variable latency, no upper bound on delivery time
- Unreliable clocks: time-of-day clocks vs monotonic clocks; clock skew; why you can't use timestamps to order events across machines
- Process pauses: GC pauses, VM suspension — a node may be "alive" but paused for seconds
- Truth is defined by the majority: a node cannot know its own state with certainty

**Chapter 9 key concepts:**
- Linearizability: behaves as if there's only one copy of the data. Strong guarantee. Expensive.
- Causality and happens-before: a weaker ordering that can be tracked with logical clocks (Lamport timestamps, version vectors)
- Consensus: getting nodes to agree on a value. Impossible to solve in a fully asynchronous system with one faulty node (FLP impossibility).
- Raft and Paxos: consensus algorithms used in etcd, ZooKeeper, CockroachDB
- ZooKeeper: consensus-as-a-service. Coordination, leader election, distributed locks.

**Interview takeaway:** Know why you can't use wall-clock time to order events. Know what linearizability costs (it requires coordination — you can't have it and partition tolerance simultaneously without sacrificing availability).

---

#### Tuesday — DDIA Chapters 10–11: Batch & stream processing

**Chapter 10 key concepts:**
- MapReduce: map phase (emit key-value pairs), shuffle (group by key), reduce phase. Handles failures by recomputing.
- Why MapReduce is falling out of favour: materialises intermediate state to disk. Dataflow engines (Spark, Flink) keep it in memory.
- Join strategies in batch: sort-merge join, broadcast hash join, partitioned hash join

**Chapter 11 key concepts:**
- Message brokers vs databases: brokers are transient by default; Kafka is durable and replayable
- Kafka architecture: topics, partitions, consumer groups, offset management
- Exactly-once semantics: hard to achieve end-to-end; idempotent producers + transactional consumers
- Event sourcing: store events not state. Derive current state by replaying. Append-only log.
- CQRS: Command Query Responsibility Segregation — separate write model from read model
- Stream-stream joins, stream-table joins, table-table joins

---

#### Wednesday — Alex Xu Vol.2 Chapter 1: Proximity service

**Core problem:** Find all businesses within a given radius of the user.

**Work through:**
- Geospatial indexing: geohash, quadtrees, Google S2
- Why a naive SQL `WHERE ST_Distance(...) < radius` doesn't scale
- Two-step approach: fetch candidates by geohash, then filter precisely
- Read-heavy vs write patterns for a business directory
- Caching strategy for popular areas
- What the interviewer is looking for: ability to scope the problem, reason about scale, pick an appropriate data structure

---

#### Thursday — Alex Xu Vol.2 Chapter 2: Nearby friends

**Core problem:** Show which friends are within X km of the user, updated in near-real-time.

**Work through:**
- How location updates flow: mobile → load balancer → WebSocket server → Redis pub/sub → other WebSocket connections
- Why WebSockets over polling for this use case
- Location storage: Redis sorted set with geospatial commands (`GEOADD`, `GEORADIUS`)
- Scaling WebSocket servers: horizontal scaling, consistent hashing to pin users to servers
- Handling location history: write to a time-series store (e.g. InfluxDB, or Cassandra with time-bucketed keys)

---

#### Friday — Hard coding challenge: concurrency

**Challenge:** Implement a bounded blocking queue in Java (`BoundedBlockingQueue`) with the following constraints:
- Fixed capacity passed in the constructor
- `enqueue(int element)` blocks if the queue is full
- `dequeue()` blocks if the queue is empty
- Thread-safe, no `java.util.concurrent` blocking queue classes allowed

Use `ReentrantLock` and `Condition` variables. This is a classic senior-level Java concurrency problem.

**Extension:** After solving it, explain how this relates to the producer-consumer problem and where you'd see this pattern in real systems (e.g. Kafka's internal fetch buffer, HTTP connection pools).

---

### Week 8 — Alex Xu Vol.2 Core Designs

#### Monday — Alex Xu Chapter 3: Google Maps

**Core problems:**
- Map rendering: tiling, zoom levels, vector vs raster tiles
- Navigation: graph representation of roads, Dijkstra vs A*, bidirectional search
- ETA prediction: historical speed data, real-time traffic as edge weights
- Scale: petabytes of map data, millions of navigation requests/second

**Key design decisions:**
- Pre-computing tiles at different zoom levels vs on-demand generation
- Storing the road graph: adjacency list in a graph DB or custom format
- Partition the graph geographically for parallel routing computation

---

#### Tuesday — Alex Xu Chapter 4: Distributed message queue

**Core problems:**
- Persistence: messages must survive broker restarts (WAL / commit log on disk)
- At-least-once vs exactly-once delivery
- Consumer groups and offset management
- Throughput: sequential disk writes (fast) vs random writes (slow)
- Message ordering: guaranteed within a partition, not across partitions
- How Kafka's architecture differs from traditional message brokers (RabbitMQ, ActiveMQ)

**Key interview question:** "What guarantee does a Kafka producer get after `send()` returns without waiting for acknowledgement? What about `acks=all`?"

---

#### Wednesday — Alex Xu Chapter 5: Metrics monitoring & alerting

**Core problems:**
- Data ingestion: high write throughput (millions of time-series points/second)
- Storage: time-series databases (InfluxDB, Prometheus, Cortex) — optimised for time-range queries and downsampling
- Query: aggregation over time windows, label-based filtering
- Alerting: threshold-based vs anomaly detection, alert fatigue, deduplication
- Visualisation: Grafana on top of Prometheus/Cortex

**Key design decisions:**
- Pull (Prometheus scrapes targets) vs push (agents push to collector)
- Data retention and downsampling: raw data kept for 15 days, 1-minute aggregates for 1 year
- Handling high cardinality: label explosion kills Prometheus performance

---

#### Thursday — Alex Xu Chapter 6: Ad click event aggregation

**Core problems:**
- High write throughput: billions of click events per day
- Aggregation: count clicks per ad, per minute/hour/day
- Accuracy: exactly-once counting — deduplication at scale
- Late-arriving events: an event from 5 minutes ago arrives now; do you recount?
- Lambda architecture vs Kappa architecture

**Key design decisions:**
- Kafka for ingestion (durable, replayable)
- Flink/Spark Streaming for windowed aggregation
- Idempotency keys to deduplicate retried events
- Storing aggregates in Cassandra (write-optimised, time-series friendly)

---

#### Friday — Phase 2 milestone review

**Identify your gaps.** Rate your confidence 1–5 on each:

- DDIA: replication lag anomalies (read-your-own-writes, monotonic reads)
- DDIA: difference between snapshot isolation and serializable isolation
- DDIA: LSM vs B-tree write/read trade-offs
- DDIA: Kafka exactly-once semantics
- Design: geospatial indexing (geohash vs quadtree)
- Design: how to scale WebSocket connections
- Design: time-series storage trade-offs

**Any topic rated 1–2 goes on your revision list for week 9 Monday.**

---

## Phase 3 — Weeks 9–10: Interview Simulation

> Goal: Stop studying. Start performing. The material is now inside you — these two weeks are about translating it into interview-room behaviour.

---

### Week 9 — More Designs + First Full Mocks

#### Monday — Alex Xu Chapters 7–8

**Chapter 7: Hotel reservation system**

Key problems:
- Inventory management: rooms available per date range. Overlapping bookings must be prevented.
- Concurrency: two users book the last room simultaneously. Optimistic locking vs database transaction with `SELECT FOR UPDATE`.
- Idempotency: if a booking request is retried, don't double-charge.
- Read vs write patterns: read-heavy (browsing) vs write-critical (reservation)

**Chapter 8: Distributed email service**

Key problems:
- Sending at scale: SMTP, delivery queues, retry with exponential backoff
- Receiving and storing: IMAP, message deduplication
- Search: inverted index on email body (Elasticsearch)
- Spam filtering: ML pipeline, reputation systems

---

#### Tuesday — Alex Xu Chapters 9–10

**Chapter 9: S3-style object storage**

Key problems:
- Object metadata vs object data stored separately
- Large file uploads: multipart upload, chunk hashing for integrity
- Erasure coding vs replication for durability
- Consistency model: strong for metadata, eventual for object propagation

**Chapter 10: Real-time gaming leaderboard**

Key problems:
- Data structure: Redis sorted set (`ZADD`, `ZREVRANK`, `ZREVRANGE`) — O(log n) updates and range queries
- Scale: millions of players, top-10 must be real-time
- Historical snapshots: archive daily winners to a separate store
- Anti-cheat: rate-limit score submissions, anomaly detection

---

#### Wednesday — Full mock: system design

**Instructions:** Set a 45-minute timer. Attempt this without notes.

**Prompt:** Design a URL shortener (e.g. bit.ly).

**What the interviewer expects from a senior candidate:**
- Clarify scale: 100M URLs created/day, 10B redirects/day
- Estimate storage: 100M × 100 bytes ≈ 10GB/day
- Hash function choice: MD5 then take first 7 chars vs base62 encoding of a counter
- Collision handling strategy
- Database choice for the mapping (key-value, high read throughput)
- Caching layer (80% of redirects come from 20% of URLs — hot cache)
- Analytics: how to count clicks without blocking the redirect
- Custom aliases, expiration

**After:** review your answer against these criteria and note gaps.

---

#### Thursday — Mock: coding screen

**Instructions:** 45-minute timer. No looking things up.

**Problem:** Given a string containing just the characters `(`, `)`, `{`, `}`, `[`, `]`, determine if the input string is valid. A string is valid if open brackets are closed in the correct order.

Then, extend the solution: given a list of log files where each log entry is either an "open" or "close" event with a timestamp and a session ID, find all sessions that were never properly closed.

**Focus:** Talk through your approach before coding. Consider edge cases explicitly. Analyse time and space complexity before submitting.

---

#### Friday — Behavioural & technical deep dives

**Behavioural questions — prepare a 2-minute answer for each (STAR format):**

1. Tell me about a time you had to make a significant technical decision under uncertainty. How did you approach it?
2. Describe a system you designed that didn't scale as expected. What did you learn?
3. Tell me about a time you disagreed with a technical direction. What did you do?
4. Describe the most complex bug you've debugged. What was your process?
5. Tell me about a time you had to balance technical debt with delivering features.

**Technical deep-dive questions — answer in 3–5 minutes each:**

1. Walk me through what happens from the moment a user hits Enter in their browser to seeing a webpage.
2. Explain the CAP theorem. Is it actually a theorem? What are its practical limitations?
3. How does a Java garbage collector work? What is GC pause and how do you tune it?
4. What is a distributed transaction? How does two-phase commit work and what are its failure modes?
5. How would you debug a Java service that is responding slowly but CPU and memory look normal?

---

### Week 10 — Final Simulations & Gap Closing

#### Monday — Targeted gap review

Look at your weak spots list and your Phase 2 confidence ratings. Spend today going deep on the 2–3 topics where you rated yourself lowest.

**Common areas to revisit:**
- Write skew and serializable isolation
- Kafka offset management and exactly-once semantics
- Consistent hashing and virtual nodes
- The difference between linearizability and serializability
- JVM memory model: heap regions, G1GC, how to read a GC log

---

#### Tuesday — Hard coding challenges: DP + graphs

**Challenge 1 — Dynamic programming:**  
Given a list of coin denominations and a target amount, find the minimum number of coins needed to make the amount. If it's not possible, return -1.

This is the classic unbounded knapsack / coin change problem. After solving it, explain: what is the recurrence relation? What is the time complexity? How does bottom-up DP differ from memoised recursion in space usage?

**Challenge 2 — Graphs:**  
Given a directed graph of `n` nodes and a list of edges, find all nodes from which every other node is reachable. Return them sorted.

This requires understanding of strongly connected components (Kosaraju's or Tarjan's algorithm) or a two-pass DFS. After solving, explain why this problem matters in real systems (e.g. identifying isolated services in a dependency graph).

---

#### Wednesday — Final mock: system design (harder)

**Instructions:** 45-minute timer. Interviewer will interrupt with follow-up questions.

**Prompt:** Design a distributed rate limiter that can be used as a shared service across multiple back-end APIs.

**What a senior answer covers:**
- Requirements: per-user vs per-endpoint vs global limits. Hard vs soft limits.
- Algorithms: token bucket, leaky bucket, sliding window log, sliding window counter — trade-offs
- Distributed challenge: a single Redis counter with Lua script for atomic increment. Or a local + centralised hybrid.
- Consistency trade-off: is it OK to occasionally allow a few extra requests?
- Failure mode: if the rate limiter service is down, fail open or fail closed?
- Header conventions: `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `Retry-After`
- Where to implement: API gateway, middleware, client library

---

#### Thursday — Final mock: coding (hard)

**Instructions:** 45-minute timer.

**Problem:** Implement an LFU (Least Frequently Used) cache with O(1) time complexity for both `get(key)` and `put(key, value)`.

This is a genuinely hard problem (LeetCode 460 hard). It requires a combination of a `HashMap` for key lookup, a `HashMap` of doubly linked lists organised by frequency, and careful pointer management.

If you solve it with O(log n), that's still a strong answer — explain the trade-off. What matters is: can you break it down, think through data structures systematically, and communicate your reasoning clearly?

---

#### Friday — Readiness assessment

**Final self-assessment — honest ratings 1–5:**

| Area | Topics | Your rating |
|---|---|---|
| Java depth | Concurrency, JVM, GC, generics, streams | |
| Algorithms | Big O, sorting, trees, graphs, DP | |
| Databases | Indexes, ACID, isolation levels, MVCC | |
| Distributed systems | Replication, partitioning, consensus, CAP | |
| System design | Caching, queues, storage, scale estimation | |
| Coding interview | Problem decomposition, edge cases, complexity analysis | |
| Communication | Structuring answers, thinking out loud, handling ambiguity | |

**Last-minute review list — skim these the day before your interview:**
- CAP theorem and what it actually means in practice
- The four isolation levels and which anomaly each prevents
- LSM tree vs B-tree one-paragraph summary
- Consistent hashing mental model
- Three rate limiting algorithms (token bucket, leaky bucket, sliding window)
- Java `volatile` vs `synchronized` vs `AtomicInteger`
- `@Transactional` proxy pitfall in Spring

---

## Quick-reference cheatsheet

### Java interview hot topics

| Topic | What interviewers ask |
|---|---|
| `HashMap` | Internals, collision handling, when to use `ConcurrentHashMap` |
| `volatile` | What it does and does NOT guarantee |
| Thread pools | `ExecutorService`, work-stealing pool, when to tune pool size |
| GC | Heap regions (eden, survivor, old gen), G1GC, how to reduce pause times |
| `Optional` | Why it exists, when NOT to use it (not as a field type) |
| Spring `@Transactional` | Proxy limitation, propagation levels, rollback rules |
| `CompletableFuture` | Composing async calls, error handling, thread pool choice |

### System design framework (45 minutes)

```
1. Clarify requirements          (5 min)
   - Functional: what must it do?
   - Non-functional: scale, latency, consistency, availability

2. Estimate scale                (3 min)
   - Reads/writes per second
   - Storage over 5 years
   - Bandwidth

3. High-level design             (10 min)
   - Core components on a whiteboard
   - Main data flow

4. Deep dive into 2–3 components (20 min)
   - The interviewer will guide this
   - Show trade-offs, not just answers

5. Wrap up                       (7 min)
   - Failure modes
   - Monitoring and alerting
   - What you'd do differently with more time
```

### DDIA one-paragraph summaries

**Replication:** Single-leader is simple but has failover risk. Multi-leader enables multi-region writes but introduces conflicts. Leaderless (Dynamo-style) uses quorums (r + w > n) for tunable consistency. All three suffer from replication lag — read-your-own-writes, monotonic reads, and consistent prefix reads are the main anomalies.

**Partitioning:** Hash partitioning distributes evenly but kills range queries. Key-range partitioning supports range queries but creates hotspots. Consistent hashing with virtual nodes minimises rebalancing. Secondary indexes on partitioned data force a choice: scatter-gather (local indexes) or coordinated writes (global indexes).

**Transactions:** Read committed prevents dirty reads. Snapshot isolation (MVCC) prevents non-repeatable reads without blocking. Serializable isolation is needed for write skew and phantoms — achieved via 2PL (pessimistic) or SSI (optimistic).

**Consensus:** You can't rely on clocks across machines. Linearizability is expensive — it requires a round trip to a quorum. Raft and Paxos give you consensus at the cost of availability under partition. ZooKeeper is consensus-as-a-service.

---

*Good luck. The program is designed to compound — each week builds on the last. Trust the process, stay consistent, and focus on understanding over memorisation.*