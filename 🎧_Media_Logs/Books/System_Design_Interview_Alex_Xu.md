## 1. Chapter 5: Design Consistent Hashing

- traditional hashing can cause data distribution issues and reshuffling issue if the node count changes (leading to cache stampede)
- Using a logical ring (consistent hashing), adding or removing a (virtual) node just causes a 1/n (n=number of nodes) reshuffling
- Using virtual nodes (server_a_1, server_b_1, server_a_2 etc...) supports uniform distribution and prevents hotspots

How would you handle data replication on this hash ring to ensure that if a node goes down, its data isn't permanently lost?
- Clockwise Replication: Data is replicated to the coordinator node plus the next $N-1$ (N is the replication factor) nodes going clockwise on the hash ring.
- Distinct Physical Node: When replicating, one must filter on duplicate hardware (to avoid duplication on the same hardware). We call it the "preference list"
- Handling Failure? 
  - hinted handoff: a node stores temporarily the data for the offline node and hand-off the data when the node is back online

Other points:
- The Quorum Rule ($R + W > N$): Ensuring your read quorum plus your write quorum is strictly greater than your replication factor mathematically guarantees that your read and write operations overlap on at least one node.