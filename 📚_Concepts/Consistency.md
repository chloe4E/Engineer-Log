# Consistency

**Domain:** Consistency <br> 
**Tags:** #consistency  <br>
**Last updated:** 2026-05-27 <br>

## What it is

One sentence.

## Why it matters

One of the tree pillars of CAP

## Key points

Strong consistency:[linearizability]: 
- once a `write` is successful all replicas are **locked** and must confirm the write.
- high **latency**
- if network partition the system rejects the update
- C+P in CAP: consistency + partition tolerance

Eventual:
- replicas converge eventually to the same value
- users can read different data (**stale** data)
- **fast** and **available**
- A+P in CAP: availability and partition tolerance


## gem 💡 Summary of Learnings
Consistency Trade-off: 
Strong consistency gives you absolute accuracy at the cost of speed and availability. 
Eventual consistency gives you blistering speed and uptime, but you must tolerate stale data temporarily.