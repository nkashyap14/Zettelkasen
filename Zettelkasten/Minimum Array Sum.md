# Minimum Array Sum

#### Problem statement

You are given an integer array `nums` and three integers `k`, `op1`, and `op2`.

You can perform the following operations on `nums`:

- **Operation 1**: Choose an index `i` and divide `nums[i]` by 2, **rounding up** to the nearest whole number. You can perform this operation at most `op1` times, and not more than **once** per index.
- **Operation 2**: Choose an index `i` and subtract `k` from `nums[i]`, but only if `nums[i]` is greater than or equal to `k`. You can perform this operation at most `op2` times, and not more than **once** per index.

**Note:** Both operations can be applied to the same index, but at most once each.

Return the **minimum** possible **sum** of all elements in `nums` after performing any number of operations.
##### Example 1
```
**Input:** nums = [2,8,3,19,3], k = 3, op1 = 1, op2 = 1

**Output:** 23

**Explanation:**

- Apply Operation 2 to `nums[1] = 8`, making `nums[1] = 5`.
- Apply Operation 1 to `nums[3] = 19`, making `nums[3] = 10`.
- The resulting array becomes `[2, 5, 3, 10, 3]`, which has the minimum possible sum of 23 after applying the operations.
```
##### Example 2
```
**Input:** nums = [2,4,3], k = 3, op1 = 2, op2 = 1

**Output:** 3

**Explanation:**

- Apply Operation 1 to `nums[0] = 2`, making `nums[0] = 1`.
- Apply Operation 1 to `nums[1] = 4`, making `nums[1] = 2`.
- Apply Operation 2 to `nums[2] = 3`, making `nums[2] = 0`.
- The resulting array becomes `[1, 2, 0]`, which has the minimum possible sum of 3 after applying the operations.
```
#### Solution
```
class Solution(object):
    def minArraySum(self, nums, k, op1, op2):
        """
        :type nums: List[int]
        :type k: int
        :type op1: int
        :type op2: int
        :rtype: int
        """        

        def dp(i, seen, w1=op1, w2=op2):
            if i == len(nums):
                return 0
            if (i, w1, w2) in seen:
                return seen[(i, w1, w2)]

            skip = nums[i] + dp(i + 1, seen, w1, w2)
            o1 =  o2 = both = float('inf')
            if w1 > 0:
                o1 = ((nums[i] + 1 ) // 2) + dp(i + 1, seen, w1 - 1, w2)
            if w2 > 0 and nums[i] >= k:
                o2 = nums[i] - k + dp(i + 1, seen, w1, w2 - 1)
            if w1 > 0 and w2 > 0:
                temp = dp(i + 1, seen, w1 - 1, w2 - 1)
                if nums[i] >= k:
                    both = ((nums[i] + 1 - k) // 2) + temp
                if (nums[i] + 1) // 2 >= k:
                    both = min(both, ((nums[i] + 1) // 2) - k + temp)
            seen[(i, w1, w2)] = min(skip, o1, o2, both)
            return seen[(i, w1, w2)]

        return dp(0, {})
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Dynamic Programming]]
#### Important Subdetails

- This solution is a 3d Dynamic programming solution
- Each time we have a few choices
	- Either skip the number
	- Apply op1 on the number
	- Apply op2 on the number
	- Apply both on the number
		- In the both case we need to get the minimum value from the rest of the array
		- Then we sum that onto both the numbers in different orderings depending on if conditions apply ie if n // 2 > k so we can sub k
		- then we take the min of that value 
	- We also memoize aka keep a hashmap and store the seen results so that recalculation doesn't have to be done
#### Runtime of Optimal Solution

- Runtime is O(n * op1 * op2) n being the array size
- Space complexity is O(n * op1 * op2) due to the memoization
---
Links :: [[#Example Code]] [[Computer Science]] [[Amazon Leetcode Problem]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-03 04:12
