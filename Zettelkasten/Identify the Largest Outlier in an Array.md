# Identify the Largest Outlier in an Array

#### Problem statement

You are given an integer array `nums`. This array contains `n` elements, where **exactly** `n - 2` elements are **special** **numbers**. One of the remaining **two** elements is the _sum_ of these **special numbers**, and the other is an **outlier**.

An **outlier** is defined as a number that is _neither_ one of the original special numbers _nor_ the element representing the sum of those numbers.

**Note** that special numbers, the sum element, and the outlier must have **distinct** indices, but _may_ share the **same** value.

Return the **largest** potential **outlier** in `nums`.
##### Example 1
```
**Input:** nums = [2,3,5,10]

**Output:** 10

**Explanation:**

The special numbers could be 2 and 3, thus making their sum 5 and the outlier 10.
```
##### Example 2
```
**Input:** nums = [-2,-1,-3,-6,4]

**Output:** 4

**Explanation:**

The special numbers could be -2, -1, and -3, thus making their sum -6 and the outlier 4.
```
#### Solution
```
class Solution(object):
    def getLargestOutlier(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """

        total = sum(nums)
        count = Counter(nums)
        res = float('-inf')
        for num in nums:
            #outlier = total - sum - sum
            outlier = total - num - num
            if count[outlier] > (outlier == num):
                res = max(res, outlier)
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
#### Important Subdetails

- Main idea of this problem hinges around total sum manipulation
	- sum - outlier = 2 * x
		- where x is the sum of the remaining special numbers
		- 2  because x1-xn -2 are the sum and then the remaining number is = to the sum of those numbers
	- or outlier = total - x - x
- (outlier == num) = 0 when outlier doesnt = num and 1 when outlier does = num
	- so the if statement checks that if the outlier is also the num value then is the outlier in the arrya twice or if the outlier isnt = to the num then is the outlier present twice

#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Amazon Leetcode Problem]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-02 15:27
