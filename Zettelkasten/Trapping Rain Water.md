# Trapping Rain Water

#### Problem statement

You are given an array non-negative integers `heights` which represent an elevation map. Each value `heights[i]` represents the height of a bar, which has a width of `1`.

Return the maximum area of water that can be trapped between the bars.

##### Example 1
```
Input: height = [0,2,0,3,1,0,1,3,2,1]

Output: 9
```
#### Solution 1
```
class Solution:
    def trap(self, height: List[int]) -> int:  
        if not height: return 0
  
        l, r = 0, len(height) - 1
        leftMax, rightMax, res = height[l], height[r], 0
        while l < r:
            if leftMax < rightMax:
                l += 1
                leftMax = max(leftMax, height[l])
                res += leftMax - height[l]
            else:
                r -= 1
                rightMax = max(rightMax, height[r])
                res += rightMax - height[r]

        return res
```
#### Solution 2
```
class Solution:
    def trap(self, height: List[int]) -> int:
        if not height: return 0
        
        leftMax = [0] * len(height)
        leftMax[0] = height[0]

        for i in range(1, len(height)):
            leftMax[i] = max(leftMax[i - 1], height[i])

        rightMax = [0] * len(height)
        rightMax[-1] = height[-1]
        
        for i in range(len(height) - 2, -1, -1):
            rightMax[i] = max(rightMax[i + 1], height[i])
  
        res = 0
        for i in range(len(height)):
            res += min(leftMax[i], rightMax[i]) - height[i]

        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Two Pointers]]
#### Important Subdetails

- Intuition of this problem hinges on the fact that at each point you are calculating the amount of rain you can trap it hinges on two factors. The maximum wall size to the left and the maximum wall size bounding it to the right. The minimum value of of those two is then subtracted by the height of the wall at that position and that is what gives you how much rain water can get held.
- From there it becomes an issue of how to calculate the left max and right max. Second solution is a brute force way that sets up an array where each position represents the left max and right max of those positions. From there just loop through the arrays once last time and subtract the min of those maxes by the heights
- Other intuitive way is to keep a running track of the left max and right max by starting at opposite ends of the array with two pointers. Move the max that is lesser. When you move that max than you know it is bounded by that max so the rainwater calculation is done with that max.
#### Runtime of Optimal Solution

- 2nd solution is O(n) runtime and O(n) space complexity
- 1st solution is O(n) runtime and O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-10 09:17
