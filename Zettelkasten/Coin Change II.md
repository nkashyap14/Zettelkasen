# Coin Change II

#### Problem statement

You are given an integer array `coins` representing coins of different denominations (e.g. 1 dollar, 5 dollars, etc) and an integer `amount` representing a target amount of money.

Return the number of distinct combinations that total up to `amount`. If it's impossible to make up the amount, return `0`.

You may assume that you have an unlimited number of each coin and that each value in `coins` is unique.
##### Example 1
```
Input: amount = 4, coins = [1,2,3]

Output: 4
```
##### Example 2
```
Input: amount = 7, coins = [2,4]

Output: 0
```
#### Solution Bottom up:
```
class Solution:
    def change(self, amount: int, coins: List[int]) -> int:

        n = len(coins)
        coins.sort()

        #so the dp columns represents the amount from 0 to amountn in 0 index
        #dp rows represent taking into account coin i in a 1 based index so 0 row = when you have 0 coins
        #the dp[coin][amount] == number of distinct ways to make up amount with the number of coins available
        #aka up to coin - 1 from coins array
        #when coins are 0 aka first row there is always 0 ways
        dp = [[0] * (amount + 1) for _ in range(n + 1)]

        #populate base case aka at amount 0 there is always 1 way to make it up. just take no coins
        #looping over the total number of coins
        for i in range(n + 1):
            dp[i][0] = 1


        #loop over the coins backward because we have sorted the coins
        for i in range(n - 1, -1 , -1):
            #loop over all possible amounts
            for a in range(amount + 1):
                if a >= coins[i]:
                    #the number of ways to make this amount is = number of ways to make this combination including this coin and the larger coins than  it
                    dp[i][a] = dp[i + 1][a]
                    #incremented by the number of ways to use this coin and coins greater than it to make the amount subtracted by this coins value
                    dp[i][a] += dp[i][a - coins[i]]

        return dp[0][amount]
```


#### Top Down Memoized
```
class Solution:
    def change(self, amount: int, coins: List[int]) -> int:
        #stk = []
        memo = {}
        def dfs(i, total):

            if (i, total) in memo:
                return memo[(i, total)]
            if total > amount:
                memo[(i, total)] = 0
                return 0

            if total == amount:
                memo[(i, total)] = 1
                return 1

            if i >= len(coins):
                return 0

            res = 0

            #decision to include the ith coin and consider taking it more times
            #stk.append(coins[i])
            res += dfs(i, total + coins[i])
            #stk.pop()
            #decision to not include the ith coin
            res += dfs(i + 1, total)
            #decision to include the ith coin and not take it more times than this current amountn
            #stk.append(coins[i])
            #res += dfs(i + 1, total + coins[i])
            # stk.pop()

            memo[(i, total)] = res

            return memo[(i, total)]

        return dfs(0, 0)
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[2D Dynamic Programming]]
#### Important Subdetails

#### Runtime of Optimal Solution

- both are O(n * a) for space and time complexity where a is amount and n is number of coins
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-09 15:12
