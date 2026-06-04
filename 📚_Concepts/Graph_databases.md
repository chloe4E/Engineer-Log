# Graph Databases

**Domain:** Databases Graph    <br>
**Tags:** #graph   #databases
**Last updated:** 20260604 <br>

## What it is

A graph database is a database which **treats the relationship between the datapoints as equally as the datapoints** themselves.

## Why it matters

Infrastructure problems, like IAM permissions, are **dependency problems** and a graph database is giving a better solution than RDMS.
**Infrastructure is a web**.

## Key points

- A graph database is **built of connections**.
- It is composed of **3 components**:
  - **nodes**: the data itself | ex: `user_123`.
  - **edges**: the relationship between the nodes | ex: `has_access_to`
  - **properties**: specific details about a node or edge | ex for a node: `status:active` | ex for a edge: `protocol:https`
- when one queries a graph db we ask to **traverse** based on a starting node (traverse vs. search)
- examples of graph db providers: Neo4j or Amazon Neptune

