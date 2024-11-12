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
            if maxHeap:
                cnt = 1 + heapq.heappop(maxHeap)
                if cnt:
                    q.append([cnt, time + n])
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
- Reverse the keys heapify it
- use a queue to manage when to put the values back onto the heap
- always want to use most frequent value
#### Runtime of Optimal Solution

- Runtime O(n * m)
	- M is number of tasks
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
