# Task Scheduling

#### Problem statement

You are given an array of CPU tasks `tasks`, where `tasks[i]` is an uppercase english character from `A` to `Z`. You are also given an integer `n`.

Each CPU cycle allows the completion of a single task, and tasks may be completed in any order.

The only constraint is that **identical** tasks must be separated by at least `n` CPU cycles, to cooldown the CPU.

Return the _minimum number_ of CPU cycles required to complete all tasks.
##### Example 1
```
Input: tasks = ["X","X","Y","Y"], n = 2

Output: 5
```
##### Example 2
```
Input: tasks = ["A","A","A","B","C"], n = 3

Output: 9
```
#### Solution
```
class Solution:
    def leastInterval(self, tasks: List[str], n: int) -> int:
        count = Counter(tasks)

        maxHeap = [ -cnt for cnt in count.values()]
        heapq.heapify(maxHeap)
        
        time = 0
        q = deque()

        while q or maxHeap:
            time += 1
            #if there are still tasks to be scheduled
            if maxHeap:
	            #process the most frequent character at time t_i
                cnt = 1 + heapq.heappop(maxHeap)
                #if the cnt of the variable isn't 0 then put it onto the queue for cooldown
                if cnt:
                    q.append([cnt, time + n])
            #if the queue has values and the first value's cooldown time has passed then put it back onto the heap for processing
            if q and q[0][1] == time:
                heapq.heappush(maxHeap, q.popleft()[0])

        return time
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Queue]]
- [[Heap]]
- [[MaxHeap]]
#### Important Subdetails
- Use the built in counter to generate frequencies
- Negate the keys and heapify it
	- Reason we negate the keys is by default python only has a minheap. So we need to negate the keys to have the heap function as a max heap
- use a queue to manage when to put the values back onto the heap
- always want to use most frequent value
#### Runtime of Optimal Solution

- Runtime O(n * m)
	- M is number of tasks
	- n is the cooldown
- Space complexity is O(m)
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-10 16:44
