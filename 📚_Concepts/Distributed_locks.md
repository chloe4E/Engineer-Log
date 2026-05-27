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
They require safety mechanisms like fencing tokens to be bulletproof.<br>
The Golden Rule: A distributed lock is completely unsafe unless the target storage system actively validates fencing tokens on every single write operation. <br>
Fencing Tokens: Provide a server-side line of defense. By requiring a strictly increasing token check at the database level, you safely reject old writes from clients that don't realize they've lost their locks.