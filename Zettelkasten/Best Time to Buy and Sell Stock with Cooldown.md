# Best Time to Buy and Sell Stock with Cooldown

#### Problem statement

You are given an integer array `prices` where `prices[i]` is the price of NeetCoin on the `ith` day.

You may buy and sell one NeetCoin multiple times with the following restrictions:

- After you sell your NeetCoin, you cannot buy another one on the next day (i.e., there is a cooldown period of one day).
- You may only own at most one NeetCoin at a time.

You may complete as many transactions as you like.

Return the **maximum profit** you can achieve.
##### Example 1
```
```
##### Example 2
```
```
#### Solution
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        # dp array
        # m = rows = indices of the prices array
        # n = cols = indices of the prices array
  
        memo = {}
        def dfs(i, buying):
            if (i, buying) in memo:
                return memo[(i, buying)]
  
            if i >= len(prices):
                return 0

            coolDown = dfs(i + 1, buying)

            if buying:
                res = dfs(i + 1, not buying) - prices[i]
            else: #are selling so we book prices[i] profit
                # we add dfs(i + 2, not buying) because each dfs call represents the max profit we can make
                #from other parts of the array. in that we are already accounting for subtracting profit when
                #buying
                res = prices[i] + dfs(i + 2, not buying)

            memo[(i, buying)] = max(coolDown, res)
            return memo[(i, buying)]

        return dfs(0, True)
```


#### Solution 2: Bottom Down
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        n = len(prices)
        dp = [[0] * 2 for _ in range(n + 1)]  

        for i in range(n - 1, -1, -1):
            for buying in [True, False]:
                if buying:
                    buy = dp[i + 1][False] - prices[i]
                    cooldown = dp[i + 1][True]
                    dp[i][1] = max(buy, cooldown)
                else:
                    sell = dp[i + 2][True] + prices[i] if i + 2 < n else prices[i]
                    cooldown = dp[i + 1][False]
                    dp[i][0] = max(sell, cooldown)

        return dp[0][1]
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
- [[Memoization]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(n) runtime
- O(n) space complexity in memoized approach
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-07 17:43
