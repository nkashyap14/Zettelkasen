# Minimum Interval to Include Each Query

#### Problem statement

You are given a 2D integer array `intervals`, where `intervals[i] = [left_i, right_i]` represents the `ith` interval starting at `left_i` and ending at `right_i` **(inclusive)**.

You are also given an integer array of query points `queries`. The result of `query[j]` is the **length of the shortest interval** `i` such that `left_i <= queries[j] <= right_i`. If no such interval exists, the result of this query is `-1`.

Return an array `output` where `output[j]` is the result of `query[j]`.

Note: The length of an interval is calculated as `right_i - left_i + 1`.
##### Example 1
```
Input: intervals = [[1,3],[2,3],[3,7],[6,6]], queries = [2,3,1,7,6,8]

Output: [2,2,3,5,1,-1]

```
#### Solution
```
class Solution:
    def minInterval(self, intervals: List[List[int]], queries: List[int]) -> List[int]:
        intervals.sort()

        minHeap = [] #min heap which will contain tupels of (length of interval, end of interval)
        res = {} #maps query to shortest length interval
        i = 0

        for q in sorted(queries):
            #as long as the query is in the intervals then include it in the heap
            while i < len(intervals) and intervals[i][0] <= q:
                heapq.heappush(minHeap, (intervals[i][1] - intervals[i][0] + 1, intervals[i][1]))
                i += 1

            #pop all intervals from the top of hte minheap whose end is before q so its not
            #part of that internval
            while minHeap and minHeap[0][1] < q:
                heapq.heappop(minHeap)

            res[q] = minHeap[0][0] if minHeap else -1

        return [res[query] for query in queries]
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

 - [[Minheap]]
#### Important Subdetails

#### Runtime of Optimal Solution

- Runtime is O(n log n + q log q) where n is number of intervals and q is number of queries
- Happens because python sort funciton is n log n
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-02-09 16:47
