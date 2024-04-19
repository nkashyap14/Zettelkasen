# Mutex

- A mutex is a program object that allows multiple program [[thread|threads]] to share the same resource but not simultaneously
- When a [[Computer Program|program]] is started it is considered a single [[process]] that runs in a [[thread|single thread]]
- Used to deal with [[race condition|race conditions]] a situation where more than one thread tries to perform operations on the same resource at one time
- Acts as a [[lock]] that any thread must obtain before accessing the shared resource
- Operations:
	- Locking: Thread must lock the mutex associated with a resource. If a mutex is locked by another thread the requesting thread is put to sleep until the mutex becomes available
	- Accessing the resource: Once mutex is locked that resource can safely access the shared resource knowing no other thread can operate on it
	- Unlocking/Releasing: Must release/unlock the mutex once done with shared resource to allow blocked threads to continue their execution path
---
Links :: [[Computer Science]] [[Concurrency]] [[Thread]] [[Linux]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-04 16:08
