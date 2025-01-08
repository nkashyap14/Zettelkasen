# Non-Overlapping Intervals

#### Problem statement

Given an array of intervals `intervals` where `intervals[i] = [start_i, end_i]`, return the minimum number of intervals you need to remove to make the rest of the intervals non-overlapping.

Note: Intervals are _non-overlapping_ even if they have a common point. For example, `[1, 3]` and `[2, 4]` are overlapping, but `[1, 2]` and `[2, 3]` are non-overlapping.
##### Example 1
```
Input: intervals = [[1,2],[2,4],[1,4]]

Output: 1
```
##### Example 2
```
Input: intervals = [[1,2],[2,4]]

Output: 0
```
#### Solution
```
class Solution:
    def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
        stack, res = [], 0
        intervals.sort(key = lambda x: x[0])
        
        for start, end in intervals:
            if stack and stack[-1] > start:
                res += 1
                #in the case that this current interval ends after the previous one this is the one to remove
                if end > stack[-1]:
                    continue
            stack.append(end)

        return res
```

###### Programming Language Utilized:
 - [[Python]]
###### Data structure utilized:

- [[Intervals]]
- [[Greedy]]
#### Important Subdetails

- As with overlapping intervals we are checking if the start of the next interval is < the end of another to indicate overlapping
- We also sort which is an n log n operation
- The key here is that we have to be choosy in which interval we should keep on the stack as the one to track
	- In our case we pick the interval that ends earlier as that minimizes the chances of overlapping with later intervals
	- this is done by adding the interval's end to the stack as the last value only if it ends before the previous interval
		- in our case this means we have removed the other interval
		- when we don't add we have removed this interval

#### Runtime of Optimal Solution

- O(n) space complexity for hte stack
- O(n log n) runtime due to the sorting
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-04 16:51
