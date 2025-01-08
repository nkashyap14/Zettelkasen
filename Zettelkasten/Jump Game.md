# Jump Game

#### Problem statement

You are given an integer array `nums` where each element `nums[i]` indicates your maximum jump length at that position.

Return `true` if you can reach the last index starting from index `0`, or `false` otherwise.
##### Example 1
```
Input: nums = [1,2,0,1,0]

Output: true
```
##### Example 2
```
Input: nums = [1,2,1,0,1]

Output: false
```
#### Solution
```
class Solution:
    def canJump(self, nums: List[int]) -> bool:
        goal = len(nums) - 1

        for i in range(len(nums) - 1, -1 , -1):
	        #reason this changes to the goal is because if this check evals to true than
	        #that means from the ith index we can reach our current goal and as such we
	        #just need to find a path to this current index to know we can reach the end
            if i + nums[i] >= goal:
                goal = i

        return goal == 0
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Greedy]]
#### Important Subdetails

- Essentially we are working backwards from the goal. From the goal we find the closest location that can jump to the goal. That in essence becomes our new goal as we just need to make sure there is a path to that tile and then we know we can reach the end
- Theoretically at the end of the loop if there is a path available the goal should be at index 0. If its greater than index 0 than we know we can't reach the end from the 0th index

#### Runtime of Optimal Solution

- O(n) runtime
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-05 19:55
