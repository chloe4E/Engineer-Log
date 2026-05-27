# Distributed Consensus

**Domain:** Databases & Messaging | distributed consensus  <br>
**Tags:** #raft #paxos #Databases & #Messaging <br>
**Last updated:** 2026-05-27 <br>


## What it is

Raft algo decomposes Paxos into more digestible flow with 3 sub issues:
- **leader election**
- **log replication**: leader accept a `write` and wait for a majority (quorum) of replicas to acknowledge the `write` before committing.
- **safety**

## Why it matters

One sentence.

## Key points
  - In Raft, a node can be in one of three states: Follower, Candidate, or Leader.
  - The leader is sending **pings** to followers
  - Follower have an **Election Timeout** timer (randomized) which resets on pings
  - if a Follower's timeout reaches **0** it assumes the Leader is off and transitions to **Candidate** state:
    - **increment** the cluster's **term** (logical clock)
    - **vote** for itself
    - request vote from other followers (send **`RequestVote` message**) 
  - A candidate becomes a leader once it reaches a quorum (majority) of votes from other nodes
  - randomized election timeout ensures not all nodes transition to candidate at the same time
  - randomized election timeout ensures not all nodes transition to candidate at the same time

## gem 💡 Summary of Learnings
Consensus: The ultimate tool for fault tolerance. While Paxos is the theoretical foundation, Raft is the pragmatic, leader-driven protocol used in modern infrastructure (like etcd, which powers Kubernetes) to keep machines in perfect agreement.