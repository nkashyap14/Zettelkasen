# Cassandra - A Decentralized Structured Storage System


## General Details

- [[Cassandra]] is a [[distributed storage]] system used to manage large amounts of structured data spread across many commodity servers
	- [[Column Database]]
	- [[NoSQL]]
- [[Highly available]]
- No single point of failure
- Hundreds of nodes
	- At this scale small and large components can fail continuously
- Doesn't support a full [[relational database|relational model]]
- In order to meet the [[reliability]] and [[Scalability]] needs of facebook messenger Cassandra was developed
	- Needed high [[write throughput]]
		- Billions of writes per day
	- [[Replication|Need for replication across data centers]]
- Data Model:
	- Table is a distributed multi dimensional [[hashmap|map]] [[Index|indexed]] by a key
	- Value is a highly structured object
	- Row key in a table is a string with no size restrictions
		- Typically 16-36 bytes long
	- Every operation on a row key is atomic per replica regardless of columns
	- Columns are grouped into sets called column families
- Column families
	- 2 types:
		- Simple
		- Super
			- Column family within a column family
	- Applications can specify the sort order of columns within column families
- API:
	- insert(table, key, rowMutation)
	- get(table, key, columnName)
	- delete(table, key, columnName)
- [[Partitioning]]
	- Uses [[Consistent Hashing]] to partition data across cluster
		- Guarantees that departure or arrival of a node only affects nodes next to it on the ring relating to data movement
		- To ensure efficient data and load distribution despite the random position assignment via a hash function cassandra analyzes load information on the ring and has lightly loaded nodes move on the ring to alleviate load of heavily loaded nodes
- [[Replication]]
	- Used to achieve [[Availability|high availability]] and [[Durability]]
	- each data item replicated at N hosts where N is replication factor
	- Each key k is assigned to a coordinator node which is in charge of replication of the data items that fall within the range
		- Replicates to N-1 nodes ont he ring
	- There are options for replication policies
		- Rack Unaware
		- Rack aware (Within a data center replicate across racks)
		- Datacenter Aware
- Cluster Membership
	- Uses [[Scuttlebutt]]
	- This is an efficient anti-entropy gossip based mechanism that has efficient CPU utilization and efficient utilization of the gossip channel
	- Uses  modified version of [[Accrual Failure Detector]]
		- Idea is failure detection module doesn't emit a boolean indicating whether a node is up or down instead emits a value which represents a suspicion level (as seen below)
		- The value dynamically adjusts to reflect network and load conditions at the monitoring node
$$
\phi = 1 = 10\%
$$
$$
\phi = 2 = 1\%
$$
$$
\phi = 3 = .1\%
$$

- Spinning up node:
	- When a node starts it chooses a random token for its position on the ring then its mapping is persisted to disk locally and also in Zookeeper (initial design) and then its token gets gossiped around the cluster
	- Allows for nodes to know about all nodes and their respective positions which allows a node to route request for a key to a correct node in the cluster

- Local Persistence:
	- Relies on local file system for data persistence
	- Data represented on disk using a data format that lends itself to efficient data retrieval
	- [[SSTable]]
	- Writes into in memory data structure only after a successful write into commit log for durability
	- Also uses bloom filters. Pretty much uses SStables
- Implementation:
	- [[process]] has following modules:
		- Partitioning module
		- Cluster membership + failure detection module
		- Storage engine module
	- Each of the modules depend on an [[event driven substrate]] 
		- Message processing pipeline and task pipeline are split into multiple stages along the line of [[SEDA Architecture]]
	- Implemented using [[Java]]
	- System control messages rely on [[UDP]] while application related messages for replication and request routing rely on [[TCP]]
- Mechanism needed to purge commit log entries
	- Cassandra has a rolling commit log where older one reaches certain configurable size so new one gets rolled out. Facebook uses 128 MB size in production
## References


Author:: [[Avinash Lakshman]] [[Prashant Malik]]
Type:: #source #paper
Org:: [[Facebook]]
Link:: https://www.cs.cornell.edu/projects/ladis2009/papers/lakshman-ladis2009.pdf
Topics::
Date:: 2025-01-02 22:07
