# Kafka

**Domain:**  Distributed Systems / Kafka / event-driven-architecture
**Tags:** #kafka #event
**Last updated:** 2026-05-20

## What it is

In distributed systems, you want to have a **resilient** set-up. Event-driven Architecture is one way to achieve this.
In an event-driven architecture: `producers send messages to a message broker and consumers listen to the message broker`.

Kafka is one system enabling this.

## Why it matters

One sentence.

## Key points

Kafka is:
- using an **append-only** distributed text file (**logs**) 
- messages are appended until a **retention** period expires (this retention period enable **replayability**)
- it applies a **pub/sub** principle: producers publish to a **topic**, consumers subscribe to a topic to read data.
- it uses partition to scale: topics are split into multiple partitions across servers.
- one partition can only have one consumer (within a consumers group) => this is a bottleneck: if one topic has only one partition then it can only have one consumer
- producers distribute their messages across partitions using a kafka mechanism called the **partitioner**
- a kafka message is composed of a `key` (optional) and a `value` (the data)
- partitioning in kafka can be done `3 ways`:
  1. if we have a **key**, we can use a **hash** function and assign to a partition
  2. if we have **no key**, the producer will act as a **load balancer** and try ot evenly distribute across partitions
  3. we can have a **custom partitioner**
- **replication factor**: the data can be duplicated according to a replication factor. There is always one leader which accept reads and writes and one or several followers who act as back-ups.
- data safety: kafka has an acknowledgement mechanism from the partitions to the producers it can be set to  `0,1,[...],all` depending on how many replications (writes) you want to ensure.
