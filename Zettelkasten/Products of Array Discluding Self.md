# Products of Array Discluding Self

#### Problem statement

Given an integer array `nums`, return an array `output` where `output[i]` is the product of all the elements of `nums` except `nums[i]`.

Each product is **guaranteed** to fit in a **32-bit** integer.

Follow-up: Could you solve it in O(n) time without using the division operation?
##### Example 1
```
Input: nums = [1,2,4,6]

Output: [48,24,12,8]

```
##### Example 2
```
Input: nums = [1,2,4,6]

Output: [48,24,12,8]
```
#### Solution
```
class Solution:

    def productExceptSelf(self, nums: List[int]) -> List[int]:
        res = [1] * len(nums)
        
        for i in range(1, len(nums)):
            res[i] = res[i - 1] * nums[i - 1]
            
        postfix = 1
        for i in range(len(nums) - 1, -1 , -1):
            res[i] *= postfix
            postfix *= nums[i]
            
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Python Array]]
#### Important Subdetails

- This solution hinges on the intuition that when you are asked to make a product discluding that one number rather than having to divide the total product you are in reality being asked to get the product of two numbers, all the numbers before that numbers index (prefix), and all the numbers after that numbers index, the postfix
- The solution sets up the result array and in an initial pass multiplies the array of 1 values by the numbers so that each index is valued as the prefix or the product of all the numbers before it
	- the beginning number is 1 always as index 0 has no number before it
	- similar case for the postfix the final value is 1 which is why initialize the postfix to 1
- Then it iterates over the numbers backwards and multiplies each index in the result array by the postfix and continues to accumulate the postfix
	- there is no need to set up a postfix array
	- a running accumulation works

#### Runtime of Optimal Solution

- O(n) as we are simply making O(2n) passes and the 2 gets cancelled out by the larger magnitude n
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-03 09:27
