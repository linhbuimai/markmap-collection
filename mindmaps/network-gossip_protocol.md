---
title: Network - Gossip Protocol
markmap:
    maxWidth: 300
    colorFreezeLevel: 2
    embedAssets: true
    activeNode:
        placement: center
---

# Distributed System

## definition

- is a collection of entities (processes), with attributes:
	- **autonomous** (standalone, not dependent)
	- **prorammable** (can write code)
	- **asynchronous**: each process runs according to its own clock
		- not sync clock
		- is different from parallel system where processes have synced clocks
	- **failure prone**: may crash arbitrarily at any point in time
- entities communicate through an **unreliable communication medium**: messages may be dropped or delayed or lost

## focus questions

1. why are **gossip** and **epidemic protocols** fast and reliable?
2. what is the most efficient way for cloud computing system to detect failures of servers?
3. how is grid computing related to cloud computing?

## building blocks

### failure detectors

### membership protocols

### gossip and epidemic protocols

- multicast
	- what
		- is a communication strategy: one sender transmits data to multiple recipients simultaneously
	- why
		- efficient data distribution
		- lower bandwidth consumption
		- realtime communication
	- challenges
		- group management
			- which nodes belong to the group
			- how nodes can join and leave the group dynamically
		- scalability
            - large amount of nodes and multicast messages
		- reliability (because multicast uses UDP)
			- packets can be lost
			- no built-in transmission mechanism
			- no order guarantee
		- fault-tolerance
			- what if a recipient fails
			- detect and retry missing messages
		- required overlay networks (multicast trees, peer-to-peer solutions)
	- types
		- IP multicast
		- application-level multicast
		- reliable multicast
    - how
        - tree-based multicast
            - organizes recipients into a hierarchical structure (spanning tree)
                - root node (source node): starts messages transmission
                - intermediate nodes (relay nodes): forward message to their child nodes
                - leaf nodes (end receivers): receive message but do not forward it
            - receivers send acknowledgements
                - positive ack
                - negative ack
                - ==problems==: ACKs/NACKs storm
            - how
                1. tree formation
                2. message transmission
                3. handling node failures: whatn an intermediate node fails
                    - parent reselection: child nodes reattach to a different parent
                    - backup links: child nodes activate predefined secondary paths
                4. tree maintenance: tree is updated dynamically as node joins, leaves the tree
            - type:
                - **source-based trees**: one sender <=> one tree
                - **shared trees**: single tree for all senders
                - **overlay multicast trees**: built at the application layer
                    + e.g., BitTorrent, Peer-to-Peer multicast protocols

## grid computing