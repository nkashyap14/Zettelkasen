# Read Committed Concurrency Bugs

- Example 1:
	- Alice has 2 bank accounts, same bank, 500 in each
	- Transfer 100 from a to account b
	- If she queries balances at the right timing while outgoing transfer has been made but incoming payment hasn't arrived then she will see her total balances as 900 for that instant
	- Called a [[non-repeatable read]] or a [[read skew]]
		- Considered acceptable under [[Read Committed Isolation|Read Committed]]
- Some situations/applications can't tolerate temporary inconsistencies
	- Backups:
		- Large db backups may take hours
		- Writes may be continuing to be made to the [[master-slave|primary]]
		- some parts of backup may end up having older data
			- As such backups can't tolerate temporary inconsistencies
	- Solution?
		- [[Snapshot Isolation]]
---
Links :: [[Computer Science]] [[Read Committed]] [[Concurrency]] [[Concurrency Bugs]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-07-04 08:42
