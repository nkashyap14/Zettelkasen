# Buy and Sell Crypto

#### Problem statement
You are given an integer array `prices` where `prices[i]` is the price of NeetCoin on the `ith` day.

You may choose a **single day** to buy one NeetCoin and choose a **different day in the future** to sell it.

Return the maximum profit you can achieve. You may choose to **not make any transactions**, in which case the profit would be `0`.
##### Example 1
```
Input: prices = [10,1,5,6,7,1]

Output: 6
```
##### Example 2
```
Input: prices = [10,8,7,5,2]

Output: 0
```
#### Solution
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        lowest = prices[0]
        res = 0
        for price in prices:
            if price < lowest:
                lowest = price
            res = max(price - lowest, res)
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Algorithm utilized:

- [[Sliding Window]]
#### Important Subdetails

#### Runtime of Optimal Solution
- O(n) as one pass through prices list
- O(1) as fixed count of variables used
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-04 16:13
