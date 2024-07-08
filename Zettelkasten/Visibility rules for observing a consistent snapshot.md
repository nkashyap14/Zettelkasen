# Visibility rules for observing a consistent snapshot

- When a [[Transaction]] reads from a database transaction id's are used to decide which objects a transaction can see and which are invisible
- An object is visible to a transaction if following conditions are met 
	- At the time when the reader's transaction started the transaction which created the object had already been committed and 
	- The object is not marked for deletion or if it is the transaction which requested deletion had not yet committed at the time when the readers transaction started
# Flow

1. List created of all other transactions in progress (not committed or aborted)
	1. Writes made by those transactions are ignored even if it subsequently commits
2. Any writes made by aborted transactions are ignored
3. Any writes made by transactions with a later transaction ID are ignored regardless of whether that transaction has committed
4. All other writes are visible to the application queries

---
Links :: [[Computer Science]] [[Snapshot Isolation]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-07-04 08:52
