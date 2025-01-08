# Coin Change

#### Problem statement

You are given an integer array `coins` representing coins of different denominations (e.g. 1 dollar, 5 dollars, etc) and an integer `amount` representing a target amount of money.

Return the fewest number of coins that you need to make up the _exact_ target amount. If it is impossible to make up the amount, return `-1`.

You may assume that you have an unlimited number of each coin.
##### Example 1
```
Input: coins = [1,5,10], amount = 12

Output: 3
```
##### Example 2
```
Input: coins = [2], amount = 3

Output: -1
```
#### Solution: Top Down with Memoization
```
class Solution(object):
    def coinChange(self, coins, amount):
        memo = {}

		#top down approach
        def dfs(curr):
            if curr == 0:
                return 0

            if curr < 0:
                return float('inf')

            if curr in memo:
                return memo[curr]


            res = float('inf')
            for coin in coins:
                res = min(res, dfs(curr - coin) + 1)

            memo[curr] = res
            return res

        res = dfs(amount)
        return res if res != float('inf') else -1
```

#### Bottom Up Approach
```
class Solution:
    def coinChange(self, coins: List[int], amount: int) -> int:
        dp = [float('inf')] * (amount + 1) # to account for dp[0] or dp[amount], dp[i] = amont i
        dp[0] = 0

        for amt in range(1, amount + 1):
            for c in coins:
                if amt - c >= 0:
                    dp[amt] = min(dp[amt - c] + 1, dp[amt])
        return dp[amount] if dp[amount] != float('inf') else -1
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Dynamic Programming]]
#### Important Subdetails

- The second solution (bottom up ) to the coin change problem requires us to keep track of state as bottom up solutions do. In this case the state we are indexing on is just the amount and what the array actually holds is the correct result for that specific amount and then we build from the bottom up
#### Runtime of Optimal Solution

- Top down: because we memoize
	- O(t) space complexity
	- O(n * t) runtime
	- Where t = total amount, n = length of coins
	- Otherwise without memo it would be O(n^t) as for each of up to t amount branches we would have n decisions to make and calculate for the coins
- Bottom up:
	- O(n * time) is runtime
	- O(t) space complexity for the dp array
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-10 13:08
