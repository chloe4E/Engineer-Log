Here is your day-by-day blueprint for **Weeks 5 to 8**.

This phase transitions you from localized databases and framework baselines into the meat of distributed architecture. You will be learning how to handle networks that fail, data that gets out of sync, and massive spatial/streaming traffic.

---

## 🌐 Phase 2: Distributed Systems & Scale (Weeks 5–8)

### 📅 WEEK 5: Replication & Partitioning

*Focus: How to split and duplicate data across multiple machines without breaking consistency.*

* **Day 21**
* **Coding (20m):** Codewars – Binary Trees. Practice implementing a simple Binary Search Tree (BST) insertion and lookup algorithm in Java.
* **Theory (40m):** Read **DDIA Chapter 5** (Leaders and Followers). Master the difference between synchronous vs. asynchronous replication, and what happens when a leader node crashes (failover).


* **Day 22**
* **Coding (20m):** Codewars – Tree Traversals. Practice a standard iterative Depth-First Search (DFS) using an explicit stack to avoid memory overhead.
* **Theory (40m):** Read **DDIA Chapter 5** (Problems with Replication Lag). Learn about distributed edge cases: *Read-Your-Own-Writes* consistency, *Monotonic Reads*, and *Consistent Prefix Reads*.


* **Day 23**
* **Coding (20m):** Codewars – Breadth-First Search (BFS). Implement a level-order tree traversal using a `Queue` (`LinkedList` or `ArrayDeque` in Java).
* **Theory (40m):** Read **DDIA Chapter 5** (Multi-Leader and Leaderless Replication). Understand how systems like Cassandra handle writes without a single coordinator. Learn the concept of Quorum writes/reads ($W + R > N$).


* **Day 24**
* **Coding (20m):** Codewars – Array/String problem focusing on hashing (e.g., finding duplicate patterns).
* **Theory (40m):** Read **DDIA Chapter 6** (Partitioning and Routing Traffic). Understand how large databases shard data. Focus deeply on **Consistent Hashing**—why it’s used, how it minimizes data movement when scaling up/down, and how virtual nodes prevent hot spots.


* **Day 25**
* **Coding (20m):** Codewars – Review the solutions you submitted this week. Focus on cleaning up variable scopes and ensuring no resource leaks exist.
* **Theory (40m):** Review session. Sketch out a high-level design of a system requiring high write availability across three global regions. Justify whether you’d use leaderless replication or multi-leader replication based on this week's readings.



---

### 📅 WEEK 6: Transactions & Distributed Truth

*Focus: Ensuring data integrity when multiple clients read and write simultaneously.*

* **Day 26**
* **Coding (20m):** Codewars – Heaps / Priority Queues. Solve a problem requiring tracking the "$K$ most frequent elements" using Java's `PriorityQueue`.
* **Theory (40m):** Read **DDIA Chapter 7** (The Meaning of ACID). Demystify the acronym. Focus heavily on what "Isolation" actually means in a database context vs. what developers assume it means.


* **Day 27**
* **Coding (20m):** Codewars – Use a Max-Heap to keep track of a running stream of data efficiently.
* **Theory (40m):** Read **DDIA Chapter 7** (Weak Isolation Levels). Study **Read Committed** and **Snapshot Isolation (MVCC)**. Understand how multi-version concurrency control allows readers to read without blocking writers.


* **Day 28**
* **Coding (20m):** Codewars – Two-pointer array problem involving sorting or partitioning arrays (e.g., *Dutch National Flag* problem).
* **Theory (40m):** Read **DDIA Chapter 7** (Preventing Lost Updates & Write Skew). This is a common senior interviewer trap. Understand what **Write Skew** is (the doctor-on-call duty example) and why standard row-locking doesn't always prevent it.


* **Day 29**
* **Coding (20m):** Codewars – Graph warm-up. Implement an adjacency list representation of a directed graph in Java using a `Map<Integer, List<Integer>>`.
* **Theory (40m):** Read **DDIA Chapter 7** (Serializability). Learn the three ways to achieve true serializability: actual sequential execution, Two-Phase Locking (2PL), and Serializable Snapshot Isolation (SSI).


* **Day 30**
* **Coding (20m):** Codewars – Write a Java program that safely updates shared state using atomic classes (e.g., `AtomicInteger`) to understand lock-free concurrency.
* **Theory (40m):** Consolidate your knowledge of Transactions. Write a 1-page summary contrasting the performance costs of *Snapshot Isolation* vs. *Two-Phase Locking (2PL)*. (Hint: 2PL introduces significant lock waiting overhead).



---

### 📅 WEEK 7: Heavy Traffic & Geospatial Architecture

*Focus: Moving to complex system designs handling massive location-based queries.*

* **Day 31**
* **Coding (20m):** Codewars – Greedy Algorithms. Solve a classical scheduling/interval matching challenge (e.g., *Meeting Rooms*).
* **Theory (40m):** Read **System Design Interview (SDI) Vol 2 - Chapter 2** (Nearby Places / Proximity Service). Review the functional vs. non-functional requirements. Pay attention to how small the read volume is compared to the write volume.


* **Day 32**
* **Coding (20m):** Codewars – Greedy / Array optimization. Solve a problem where local maximum choices yield an optimal global solution.
* **Theory (40m):** Read **SDI Vol 2 - Chapter 2** (Geospatial Indexing Deep Dive). Master **Geohashes** and **Quadtrees**. Understand how a 2D map of longitude/latitude is converted into a 1D string/tree format for efficient database index scanning.


* **Day 33**
* **Coding (20m):** Codewars – Dynamic Programming (DP) Warm-up. Solve a simple 1D array DP problem (e.g., *Climbing Stairs* or *Fibonacci* with memoization).
* **Theory (40m):** Read **SDI Vol 2 - Chapter 4** (Design Ride-Hailing Service / Uber style). Contrast this with the Proximity service. Why can't we use a static Quadtree when the drivers are constantly moving?


* **Day 34**
* **Coding (20m):** Codewars – Dynamic Programming. Move to a slightly harder string/array DP problem (e.g., *Coin Change* or *Unique Paths*).
* **Theory (40m):** Read **SDI Vol 2 - Chapter 4** (High-Level Design for Uber). Understand the Dispatch Service, Route Service, and how an in-memory data store like **Redis (using Geospatial indexes)** handles rapid-fire driver location updates.


* **Day 35**
* **Coding (20m):** Codewars – Solve a string optimization challenge using a matrix/2D array approach.
* **Theory (40m):** Practice drawing Alex Xu’s high-level components for a ride-hailing app. Focus on the flow of data: How does a passenger's app communicate with a driver's app in real-time? (WebSocket connections vs HTTP polling).



---

### 📅 WEEK 8: Streaming, Metrics & Scale

*Focus: Processing event streams in real-time and scaling analytical ingestion layers.*

* **Day 36**
* **Coding (20m):** Codewars – Graph Traversal. Implement a basic cycle detection algorithm in a directed graph using DFS.
* **Theory (40m):** Read **SDI Vol 2 - Chapter 5** (Distributed Message Queue). Focus on the core mechanics of a message broker. What is a producer, a consumer, and a topic?


* **Day 37**
* **Coding (20m):** Codewars – String pattern matching (e.g., implementing an elementary version of an index-of operation).
* **Theory (40m):** Read **SDI Vol 2 - Chapter 5** (Deep Dive on Storage Engine / Kafka style). Learn why appending to a disk sequentially is incredibly fast and how an  LSM-like log-segment format allows message queues to achieve extreme throughput.


* **Day 38**
* **Coding (20m):** Codewars – Java-Specific Stream API. Practice map, filter, reduce, and collection operations using Java Streams to clean up data pipelines.
* **Theory (40m):** Read **SDI Vol 2 - Chapter 7** (Ad Click Aggregation). Look at the scale: millions of clicks per second. Understand why writing every click instantly to a relational database is a recipe for system collapse.


* **Day 39**
* **Coding (20m):** Codewars – Sliding Window technique. Apply it to an array stream simulation (e.g., tracking the maximum value in a moving subarray window).
* **Theory (40m):** Read **SDI Vol 2 - Chapter 7** (Streaming Frameworks & Time Windows). Learn how stream aggregation engines (like Apache Flink or Spark Streaming) process data using **Tumbling Windows** vs. **Sliding Windows**. Know the difference between *Event Time* and *Processing Time*.


* **Day 40**
* **Coding (20m):** Codewars – Take an older algorithm you wrote and refactor it using clean object-oriented principles (Single Responsibility, clear interfaces).
* **Theory (40m):** Review Phase 2. Spend 40 minutes reviewing the trade-offs between a batch architecture (Hadoop/MapReduce style processing at midnight) vs. a streaming architecture (Kafka + Flink processing events as they occur).