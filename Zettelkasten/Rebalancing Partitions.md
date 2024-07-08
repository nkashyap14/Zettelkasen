# Rebalancing Partitions

## Summary

- Database requirements are constantly evolving:
	- Ie if query throughput increases leads to needing mroe [[Vertical scaling]] with additions of more CPU's
	- If dataset size increases need to add more disks and ram
	- A machine fails and other machines need to take over failed machine's responsibilities
		- [[Horizontal Scaling]]
- All of above can lead to needing [[rebalancing]]
## Subtopics

- [[Hash Mod N]]
	- Don't do it this way
	- Not good for [[Range Based Partitioning]]
- [[Dynamic Partitioning]]
	- Good for [[Range Based Partitioning]]
## Details

## Conclusion


Type :: #topic
Links :: [[Computer Science]] [[System Design]] [[Partitioning]]
Creator ::
Date ::  2024-06-07 13:05