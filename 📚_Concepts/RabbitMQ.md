# <Concept Name>

**Domain:** Distributed Systems / event driven architecture
**Tags:** #rabbitMQ #event
**Last updated:** 2026-05-20

## What it is

One sentence.

## Why it matters

One sentence.

## Key points

In RabbitMQ:
- Producers sends message to **Exchanges**
- Exchanges use rules, called **routing keys**, to decide to which queue(s) the message go to.
- **Queues** use **binding keys**, it connects Exchanges to Queues.
- once a consumer reads and acknowledges the message, it gets deleted. **No replayability**.
- there are 4 ways for Exchanges to distribute a message:
  1. **Direct** exchange: `1:1 routing`. Exchange looks for an exact match between the message routing key and the queue binding key.
  2. **Fanout** exchange: `send to all`. ignore routing key and copy & send message to all queues (ex: config changes)
  3. **Topic** exchange: `selective routing`. pattern matching using dot separated routing keys. (ex: sensor.temperature.city1)
  4. Header exchange: ignore routing key and rely on message's header attributes.
- Failed messages fo to **DLX** (dead letter Exchange) and DLX route the message to a Dead Letter Queue for re-triggering or later inspection (by admins).
- A message can **fail** because it is **rejected**, the time to live **expired** or the queue **overflowed**.
- message deletion: a message can be deleted upon delivery with or without acknowledgement (automatic ack, manual ack, reject or nack)
