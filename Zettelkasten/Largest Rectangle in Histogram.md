# Largest Rectangle in Histogram

#### Problem statement

You are given an array of integers `heights` where `heights[i]` represents the height of a bar. The width of each bar is `1`.

Return the area of the largest rectangle that can be formed among the bars.

Note: This chart is known as a [histogram](https://en.wikipedia.org/wiki/Histogram).
##### Example 1
```
Input: heights = [7,1,7,2,2,4]

Output: 8

```
##### Example 2
```
Input: heights = [7,1,7,2,2,4]

Output: 8
```
#### Solution
```
class Solution:
    def largestRectangleArea(self, heights: List[int]) -> int:
        maxArea = 0
        stack = []

        for i, h in enumerate(heights):
            start = i
            while stack and stack[-1][1] > h:
                index, height = stack.pop()
                maxArea = max(maxArea, height * (i - index))
                start = index
            stack.append((start, h))

        for i, h in stack:
            maxArea = max(maxArea, h * (len(heights) - i))

        return maxArea
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Stack]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(n) runtime and O(n) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-26 16:27
