# Global Interpreter Lock

- Exists as a global lock on the [[Interpreter]] which prevents any [[thread]] from overwriting execution to the same pocket of data in python
	- This effectively means python is blocked from [[Concurrency]]
- Allows only one thread to hold control of the python interpreter. In other words only one thread can be in a state of execution at any given point in time
- Was adopted as a convention because it allowed the integration of C libraries that were not safe into python
- GIL limits [[CPU Bound Applications|CPU Bound Programs]] as they become single threaded even if written to be multi threaded due to the GIL bottle neck
---
Links :: [[Computer Science]] [[Python]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-02 22:05
