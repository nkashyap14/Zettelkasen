# Service Discovery

## Summary

- Client makes request to a db needs to hit certain [[partitions|partition]] who does the routing
	- [[Dynamic Partitioning]] or even [[Hash Mod N]] can lead to assignment of partition to nodes changes
- Not limited to just db's
	- How does a software accessible over a network get requests routed t oit
	- Many companies write their own in house service discovery tools

## Subtopics

- Approaches:
	- Allow client to contact any node
		- [[Round-Robin Load Balancer]]
		- If node owns the partition for the request it answers otherwise it forwards request to appropriate node
	- Send requests from clients to a routing tier first which determines the node that should handle the request and forwards it accordingly
		- Doesn't handle requests but only acts as a [[partition aware load balancer]]
	- Require that clients be aware of the partitioning and assignment of partitions
		- Client connects to right node
	- [[Gossip Protocol]]
		- can use this amongst the nodes to disseminate and agree on changes in cluster state
		- Adds more complexity to the database nodes but removes requirement of third party service

## Details

- Many [[Distributed Systems]] utilize a separate coordination service such as [[ZooKeeper]] which maintains the mapping of partitions to nodes

## Conclusion


Type :: #topic
Links :: [[Computer Science]]
Creator ::
Date ::  2024-06-17 09:41