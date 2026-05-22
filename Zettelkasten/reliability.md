# reliability

- Refers to the ability of a system to perform its intended functions consistently and predictably without failure over a specified period
- In layman's terms a system continuing to work correctly even when things go wrong
	- fault happens which probability of happening is never going to be zero
- Probability that the service will perform its functions for a specified time
- Reliability measures how the service performs under varying operating conditions
- Metrics used:
$$
Mean Time Between Failures = \frac{Total Elapsed Time - Sum of Downtime}{Total Number of Failures}
$$

$$
Mean Time To Repair = \frac{Total Maintenance Time}{Total Number of Repairs}
$$

- Better reliability has a higher mean time between failures and a lower mean time to repair
	- So we want to minimize the denominator for mtbf which is number of failures
		- also maximize numerator so decrease percentage of total time that downtime makes up
	- To lower meantime to repair must lower total maintenance time or increase total number of repairs
---
Links :: [[Computer Science]] [[System Design]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-07-19 08:09
