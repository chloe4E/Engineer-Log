# Distributed Locks

**Domain:** Databases & Messaging | distributed systems | locks | databases <br>
**Tags:** #locks #Databases & #Messaging <br>
**Last updated:** 2026-05-27 <br>

## What it is



## Why it matters

Goal: ensure that only **one worker** can modify one specific resource **at any time**.

## Key points

- Can use an external system to act as a single source of truth for who holds the lock (Redlock algo for Redis, Zookeeper or Consul)
- **Fencing tokens**: increasing number on lock holder change. Database checks the token to doublecheck if it shall accept the write or not


## gem 💡 Summary of Learnings
Distributed Locks: Essential for protecting shared resources across clusters, but vulnerable to timing issues (like network/GC pauses).<br>
They require safety mechanisms like fencing tokens to be bulletproof.
