# Binary Search

#### Problem statement


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
            calc = l + int((r - l) / 2)
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
