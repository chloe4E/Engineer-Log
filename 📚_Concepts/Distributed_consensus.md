# Distributed Consensus

**Domain:** distributed consensus  <br>
**Tags:** #raft #paxos  <br>
**Last updated:** 2026-05-27 <br>


## What it is

Raft algo decomposes Paxos into more digestible flow with 3 sub issues:
- **leader election**
- **log replication**: leader accept a `write` and wait for a majority (quorum) of replicas to acknowledge the `write` before committing.
- **safety**

## Why it matters

One sentence.

## Key points


## gem 💡 Summary of Learnings
Consensus: The ultimate tool for fault tolerance. While Paxos is the theoretical foundation, Raft is the pragmatic, leader-driven protocol used in modern infrastructure (like etcd, which powers Kubernetes) to keep machines in perfect agreement.