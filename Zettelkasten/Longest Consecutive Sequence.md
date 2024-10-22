# Longest Consecutive Sequence

#### Problem statement
Given an array of integers `nums`, return _the length_ of the longest consecutive sequence of elements.

A _consecutive sequence_ is a sequence of elements in which each element is exactly `1` greater than the previous element.

You must write an algorithm that runs in `O(n)` time.
##### Example 1
```
Input: nums = [2,20,4,10,3,4,5]

Output: 4
```
##### Example 2
```
Input: nums = [0,3,2,5,4,6,1,1]

Output: 7
```
#### Solution
```
class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        numset = set(nums)
        longest = 0

        for n in nums:
            if n - 1 not in numset:
                length = 0
                while (n + length) in numset:
                    length += 1
                longest = max(longest, length)

        return longest
```

###### Programming Language Utilized:

###### Data structure utilized:
#### Important Subdetails

#### Runtime of Optimal Solution

- O(n) solution
- O(n) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-09 13:52
