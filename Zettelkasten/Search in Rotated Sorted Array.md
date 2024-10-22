# Search in Rotated Sorted Array

#### Problem statement

You are given an array of length `n` which was originally sorted in ascending order. It has now been **rotated** between `1` and `n` times. For example, the array `nums = [1,2,3,4,5,6]` might become:

- `[3,4,5,6,1,2]` if it was rotated `4` times.
- `[1,2,3,4,5,6]` if it was rotated `6` times.

Given the rotated sorted array `nums` and an integer `target`, return the index of `target` within `nums`, or `-1` if it is not present.

You may assume all elements in the sorted rotated array `nums` are **unique**,

A solution that runs in `O(n)` time is trivial, can you write an algorithm that runs in `O(log n) time`?
##### Example 1
```
Input: nums = [3,4,5,6,1,2], target = 1

Output: 4
```
##### Example 2
```
Input: nums = [3,5,6,0,1,2], target = 4

Output: -1
```
#### Solution
```
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        l, r = 0, len(nums) - 1

        while l <= r:
            mid = (l + r) // 2
            if target == nums[mid]:
                return mid
            if nums[mid] <= nums[r]:
                if target < nums[mid] or target > nums[r]:
                    r = mid - 1
                else:
                    l = mid + 1
            else:
                if target > nums[mid] or target < nums[l]:
                    l = mid + 1
                else:
                    r = mid - 1
        return -1
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Binary Search]]
#### Important Subdetails

- The first part of the loop is to determine if mid is in the right sorted part or the left sorted part. if the mid is less than the right endpoint than we know we are in the right sorted array. from there we need to check if the target is in the bounds of the right sorted array or not, we check that by checking if target < mid or greater than the right endpoint. If it does meet those conditions than we know we are not in the right sorted array so we need to move our bounds to the left sorted array so we move right to mid - 1. If we are in the right sorted array and the target is in there too than what we know is we need to stay in the right sorted array but make the checking conditions smaller so we move left to mid + 1
- The else is when we know we are in the left sorted array. Similar to the right sorted array we need to check if the target is still in the left sorted array or outside its bounds. We check that by determining if target is greater than mid or less than the left endpoint which mieans we know we need to go to the right sorted array so we set l to mid + 1. if its in the bounds than we just collapse right to mid -1 
#### Runtime of Optimal Solution

- O(log n) as it is a binary search problem
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-21 10:24
