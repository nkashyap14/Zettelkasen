# Binary Search

#### Problem statement

You are given an array of **distinct** integers `nums`, sorted in ascending order, and an integer `target`.

Implement a function to search for `target` within `nums`. If it exists, then return its index, otherwise, return `-1`.

Your solution must run in O(logn) time.

**Constraints:**

- `1 <= nums.length <= 10000`.
- `-10000 < nums[i], target < 10000`
##### Example 1
```
Input: nums = [-1,0,2,4,6,8], target = 4

Output: 3
```
##### Example 2
```
Input: nums = [-1,0,2,4,6,8], target = 3

Output: -1
```
#### Solution
```
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        l, r = 0, len(nums) - 1
        //important for = as the target can be at the index where l == r
        while l <= r:
	        //calculated like this because we are looking for midpoint of current bounds. Done by adding half of the total length to the left most bound
            calc = (l + r) // 2
            if nums[calc] == target:
                return calc
            elif nums[calc] < target:
                l = calc + 1 //shift left bounds to above what we know is too little
            else:
                r = calc - 1 // shift right bounds to below what we know is to much
        return -1
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Two Pointers]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(log n)
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
Date :: 2024-10-08 06:57
