# Count Number of Bad Pairs

#### Problem statement

You are given a **0-indexed** integer array `nums`. A pair of indices `(i, j)` is a **bad pair** if `i < j` and `j - i != nums[j] - nums[i]`.

Return _the total number of **bad pairs** in_ `nums`.
##### Example 1
```
**Input:** nums = [4,1,3,3]
**Output:** 5
**Explanation:** The pair (0, 1) is a bad pair since 1 - 0 != 1 - 4.
The pair (0, 2) is a bad pair since 2 - 0 != 3 - 4, 2 != -1.
The pair (0, 3) is a bad pair since 3 - 0 != 3 - 4, 3 != -1.
The pair (1, 2) is a bad pair since 2 - 1 != 3 - 1, 1 != 2.
The pair (2, 3) is a bad pair since 3 - 2 != 3 - 3, 1 != 0.
There are a total of 5 bad pairs, so we return 5.
```
##### Example 2
```
**Input:** nums = [1,2,3,4,5]
**Output:** 0
**Explanation:** There are no bad pairs.
```
#### Solution
```
class Solution(object):
    def countBadPairs(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """

        res = {}
        bad_pairs = 0

  

        for i, num in enumerate(nums):
            diff = i - num

            good_pairs = res.get(diff, 0)

			#total amount of bad pairs are going to be the = the current number minus the amount of good pairs there are so far aka numbers with the same difference as the current index
            bad_pairs += i - good_pairs

  

            res[diff] = good_pairs + 1

  

        return bad_pairs
```

###### Programming Language Utilized:

 - [[Python]]
###### Data structure utilized:

 - [[Hashmap]]
#### Important Subdetails

- Hinges on that we ccan rewrite the equation to j - nums[j] = i - num[i]

#### Runtime of Optimal Solution

- O(n) runtime
---
Links :: [[#Example Code]] [[Computer Science]] [[Leetcode Daily Contests]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-02-09 17:11
