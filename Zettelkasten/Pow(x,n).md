# Pow(x,n)

#### Problem statement
`Pow(x, n)` is a mathematical function to calculate the value of `x` raised to the power of `n` (i.e., `x^n`).

Given a floating-point value `x` and an integer value `n`, implement the `myPow(x, n)` function, which calculates `x` raised to the power `n`.

You may **not** use any built-in library functions.
##### Example 1
```
Input: x = 2.00000, n = 5

Output: 32.00000
```
##### Example 2
```
Input: x = 2.00000, n = -3

Output: 0.12500
```
#### Solution
```
class Solution:
    def myPow(self, x: float, n: int) -> float:
        memo = {0: 1, 1: x}
        def dfs(exp):
            if exp in memo:
                return memo[exp]

            if exp % 2 == 1:
                memo[exp] = dfs(exp // 2) * dfs(exp // 2) * x
                return memo[exp]

            memo[exp] = dfs(exp // 2) * dfs(exp // 2)
            return memo[exp]

  

        return dfs(n) if n > 0 else 1 / dfs(abs(n)
```

###### Programming Language Utilized:

-  [[Python]]
###### Data structure utilized:

- [[Dynamic Programming]]
#### Important Subdetails

#### Runtime of Optimal Solution

- O(log n) runtime and space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-20 09:51
