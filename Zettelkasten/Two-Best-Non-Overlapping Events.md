# Two-Best-Non-Overlapping Events

#### Problem statement

You are given a **0-indexed** 2D integer array of `events` where `events[i] = [startTimei, endTimei, valuei]`. The `ith` event starts at `startTimei` and ends at `endTimei`, and if you attend this event, you will receive a value of `valuei`. You can choose **at most** **two** **non-overlapping** events to attend such that the sum of their values is **maximized**.

Return _this **maximum** sum._

Note that the start time and end time is **inclusive**: that is, you cannot attend two events where one of them starts and the other ends at the same time. More specifically, if you attend an event with end time `t`, the next event must start at or after `t + 1`.
##### Example 1
```
**Input:** events = [[1,3,2],[4,5,2],[2,4,3]]
**Output:** 4
**Explanation:** Choose the green events, 0 and 1 for a sum of 2 + 2 = 4.
```
##### Example 2
```
**Input:** events = [[1,3,2],[4,5,2],[1,5,5]]
**Output:** 5
**Explanation:** Choose event 2 for a sum of 5.
```
#### Solution
```
class Solution(object):
    def maxTwoEvents(self, events):
        events.sort()
        bestVal, res = 0, 0
        #pushing end value and val onto the heap
        heap = []
  
        for start, end, val in events:
            #while end time is less than the current start so we know we can use the val
            while heap and heap[0][0] < start:
                bestVal = max(bestVal, heapq.heappop(heap)[1])
            res = max(res, val + bestVal)
            heapq.heappush(heap, (end, val))
  
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Heap]]
#### Important Subdetails

#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Leetcode Problem]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-08 18:52
