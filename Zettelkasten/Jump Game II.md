# Jump Game II

#### Problem statement

You are given an array of integers `nums`, where `nums[i]` represents the maximum length of a jump towards the right from index `i`. For example, if you are at `nums[i]`, you can jump to any index `i + j` where:

- `j <= nums[i]`
- `i + j < nums.length`

You are initially positioned at `nums[0]`.

Return the minimum number of jumps to reach the last position in the array (index `nums.length - 1`). You may assume there is always a valid answer.
##### Example 1
```
Input: nums = [2,4,1,1,1,1]

Output: 2
```
##### Example 2
```
Input: nums = [2,1,2,1,0]

Output: 2
```
#### Solution
```
class Solution:
    def jump(self, nums: List[int]) -> int:
        l = r = 0
        res = 0
        while r < len(nums) - 1:
            farthest = 0
            for i in range(l, r + 1):
                farthest = max(farthest, i + nums[i])
            l = r + 1
            r = farthest
            res += 1
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Greedy]]
#### Important Subdetails

- Essentially implementing one dimension [[Breadth First Search]]
	- each level represents positions reachable with the same number of jumps
	- l, r are bfs queue boundaries/ nodes to process at that level
	- when r hits the end we've found the end point
	- each level contains nodes reachable from previous level
#### Runtime of Optimal Solution

- O(n) runtime
- O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-05 20:21
