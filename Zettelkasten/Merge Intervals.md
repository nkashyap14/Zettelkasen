# Merge Intervals

#### Problem statement

Given an array of `intervals` where `intervals[i] = [start_i, end_i]`, merge all overlapping intervals, and return an array of the non-overlapping intervals that cover all the intervals in the input.

You may return the answer in **any order**.

Note: Intervals are _non-overlapping_ if they have no common point. For example, `[1, 2]` and `[3, 4]` are non-overlapping, but `[1, 2]` and `[2, 3]` are overlapping.
##### Example 1
```
Input: intervals = [[1,3],[1,5],[6,7]]

Output: [[1,5],[6,7]]
```
##### Example 2
```
Input: intervals = [[1,2],[2,3]]

Output: [[1,3]]
```
#### Solution
```
class Solution:
    def merge(self, intervals: List[List[int]]) -> List[List[int]]:
        intervals.sort(key= lambda i: i[0])
        output = [intervals[0]]
        for start, end in intervals[1:]:
            lastEnd = output[-1][1]
            if start <= lastEnd:
                output[-1][1] = max(lastEnd, end)
            else:
                output.append([start, end])

        return output
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
#### Important Subdetails

- Need to sort by start time
- need to take the max of the ending times as we areenlarging the interals
#### Runtime of Optimal Solution
- O(n log n) runtime because of the sorting
- O(n) space complexity because of the output creation
---
Links :: [[#Example Code]] [[Computer Science]] [[Amazon Leetcode Problem]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-03 04:17
