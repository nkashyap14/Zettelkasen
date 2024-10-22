# Thread Lifecycle

- A thread has 4 states:
	- New State: 
		- No CPU resources taken, not running yet
		- Some [[Zettelkasten/Programming Language|programming languages]] require us to explicitly start a [[thread]] after creation
	- Runnable state: 
		- In a state ready for the os to schedule for execution. Through context switches can be scheduled on a [[processor]]
	- Blocked:
		- Waiting on some sort of bottleneck. Context switch can occur while thread is blocked to allow processor to be utilized by a different thread on a different path of execution
		- [[join()]]
	- Terminated:
		- When a thread completes its execution or is abnormally aborted
---
Links :: [[Computer Science]] [[Concurrency]] [[Python]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-02 22:59
