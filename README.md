# Skip Graphs
The overarching repository for Skip Graph project features set. The ideal goal is for this repository to provide a feature parity among various 
implementations of the Skip Graph. 

## Definitions
A **skip graph**[1] is a distributed data structure that enables efficient **search**, **insert**, and **delete** operations in a **peer-to-peer 
system**. It's a **linked, layered structure**, similar to skip lists, but supports **range queries** and better **fault tolerance**.

**How** it works:
- Nodes are organized in multiple levels, each with linked lists.
- Higher levels have sparser links, allowing logarithmic search.
- Nodes share a *membership vector*; links are formed based on prefix matching.
- Searching starts from the topmost level and descends as needed.

It offers $O(\log n)$ complexity for operations and resilience to node failures. 

A skip graph also acts as a **Distributed Hash Table (DHT)** by 
organizing nodes to support **key-based lookup and storage** across a distributed system:
- Each node holds keys (or key-value pairs), forming a **distributed index**.
- Lookup uses **membership vectors** and **layered linked lists** to navigate efficiently—like routing in DHTs.
- Unlike ring-based DHTs (e.g., Chord), skip graphs support **range queries**, since keys are **ordered**.
- Keys are stored at nodes based on a **deterministic rule**, enabling decentralized **insert/search/delete**.

Thus, skip graphs provide DHT functionality with **ordered key support** and **logarithmic routing**.

## Implementations
- **Rust**: https://github.com/thep2p/skipgraph-rust (Work in Progress)
- **Go**: https://github.com/thep2p/skipgraph-go (Work in Progress)
- **Java**: https://github.com/thep2p/skipgraph-java (an older implementation, a minimalistic version)


## References
1. Aspnes, James, and Gauri Shah. "Skip graphs." Acm transactions on algorithms (talg) 3.4 (2007): 37-es.
