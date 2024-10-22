# Find Minimum in Rotated Sorted Array

#### Problem statement

You are given an array of length `n` which was originally sorted in ascending order. It has now been **rotated** between `1` and `n` times. For example, the array `nums = [1,2,3,4,5,6]` might become:

- `[3,4,5,6,1,2]` if it was rotated `4` times.
- `[1,2,3,4,5,6]` if it was rotated `6` times.

Notice that rotating the array `4` times moves the last four elements of the array to the beginning. Rotating the array `6` times produces the original array.

Assuming all elements in the rotated sorted array `nums` are **unique**, return the minimum element of this array.

A solution that runs in `O(n)` time is trivial, can you write an algorithm that runs in `O(log n) time`?

##### Example 1
```
Input: nums = [3,4,5,6,1,2]

Output: 1
```
##### Example 2
```
Input: nums = [4,5,0,1,2,3]

Output: 0
```
#### Solution
```
class Solution:
    def findMin(self, nums: List[int]) -> int:
        l, r = 0, len(nums) - 1
        mini = float('inf')
        while l < r:
            mid = (l + r) // 2
            mini = min(mini, nums[mid])

            if nums[mid] > nums[r]:
                l = mid + 1
            else:
                r = mid - 1

        return min(mini, nums[l])
```

###### Programming Language Utilized:

###### Data structure utilized:

- [[Binary Search]]
#### Important Subdetails

- The way this works is when we rotate the array we know that essentially there are two two sorted arrays:
	- If the mid point we calculate is greater than the end of the right array then we know we want to search the right sorted array so we set l = mid + 1
		- because we know the mid point is in the greater part of hte array. we want to search the smaller of the two sorted arrays
	- Otherwise we search the left sorted array for the min
		- because the mid point is less than the right end point so we know we are in the right end of the array. from there we just set right to mid - 1 and search the sorted smaller left portion
- At the end we need to compare the calculated min so far with the leftmost pointer as there is always a possibility the left most pointer at the end holds the minimum value in case we end up searching over solely one portion of the sorted array (or even the array has been rotated n) times so we end up with the same sorted array

#### Runtime of Optimal Solution

- O(log n) runtime
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-15 08:17
