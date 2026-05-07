# Cache Stampede

**Domain:** Distributed Systems
**Tags:** #caching
**Last updated:** 2026-05-04

## What it is

Cache stampede is when the requested data is not available in your cache anymore, as a consequence your database is receiving a large amount of requests for this very piece of data.


## Why it matters

Your DB could crash because of this unexpected amount of request, your user may experience a longer than usual waiting time.
This may eventually breach your services SLOs.

## Key points

mitigation strategies to prevent / handle a cache stampede:
- Locking (lock the db on the request of the first user for the data, trade-off: first user will pay the price)
- Probabilistic early recomputation - PER (trade-off: relies also on luck)
- External recomputation (ex: cronjob but trade-off: may waste resources)

The optimal solution depend on the structure of the data.
If the data is long-tail: it is advisable to pick a "lazy loading" approach to fetch data when required, but we also use locking or PER to avoid crashing the db.

