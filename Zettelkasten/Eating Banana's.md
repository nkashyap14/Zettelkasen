# Eating Banana's

#### Problem statement
You are given an integer array `piles` where `piles[i]` is the number of bananas in the `ith` pile. You are also given an integer `h`, which represents the number of hours you have to eat all the bananas.

You may decide your bananas-per-hour eating rate of `k`. Each hour, you may choose a pile of bananas and eats `k` bananas from that pile. If the pile has less than `k` bananas, you may finish eating the pile but you can not eat from another pile in the same hour.

Return the minimum integer `k` such that you can eat all the bananas within `h` hours.

##### Example 1
```
Input: piles = [1,4,3,2], h = 9

Output: 2
```
##### Example 2
```
Input: piles = [25,10,23,4], h = 4

Output: 25
```
#### Solution
```
class Solution:
    def minEatingSpeed(self, piles: List[int], h: int) -> int:
        l, r = 1, max(piles)
        res = r

        while l <= r:
            k = (r + l) // 2
            hours = 0
            
            for p in piles:
                hours += math.ceil(float(p) / k)

            if hours <= h:
                res = k
                r = k - 1
            else:
                l = k + 1

        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Binary Search]]
#### Important Subdetails

- This becomes a binary search problem except the range of values we are searching over now is the range of banana per hour eating rate of k. We define that range from 1 (have to minimum eat one) to the max value of piles (because eating more would be inefficient as at that point we know each pilie would take 1 hour same as any increased)
- From there we calculate the hours. if the hours don't meet the max limit than we have to reduce the range we can check in from the top whereas if it reaches the limit we can reduce the range from the minimum values as we need to check larger values.
#### Runtime of Optimal Solution

- O(log n)
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-10 15:45
