# Valid Parenthesis String

#### Problem statement

You are given a string `s` which contains only three types of characters: `'('`, `')'` and `'*'`.

Return `true` if `s` is **valid**, otherwise return `false`.

A string is valid if it follows all of the following rules:

- Every left parenthesis `'('` must have a corresponding right parenthesis `')'`.
- Every right parenthesis `')'` must have a corresponding left parenthesis `'('`.
- Left parenthesis `'('` must go before the corresponding right parenthesis `')'`.
- A `'*'` could be treated as a right parenthesis `')'` character or a left parenthesis `'('` character, or as an empty string `""`.
##### Example 1
```
Input: s = "((**)"

Output: true
```
##### Example 2
```
Input: s = "(((*)"

Output: false
```
#### Solution (Greedy)
```
class Solution:
    def checkValidString(self, s: str) -> bool:

        leftMin = leftMax = 0
        for ch in s:
            if ch == '(':
                leftMin, leftMax = leftMin + 1, leftMax + 1
            elif ch == ')':
                leftMin, leftMax = leftMin - 1, leftMax - 1
            else:
                leftMin, leftMax = leftMin - 1, leftMax + 1
  
            if leftMax < 0:
                return False

            if leftMin < 0:
                leftMin = 0

        return leftMin == 0
```


#### Solution (Top Down/Memoization)
```
class Solution:
    def checkValidString(self, s: str) -> bool:
        memo = {}
        def dfs(i, open):
            if (i, open) in memo:
                return memo[(i, open)]
            if open < 0:
                return False
            if i == len(s):
                return open == 0
            if s[i] == '(':
                memo[(i, open)] = dfs(i + 1, open + 1)
                return memo[(i, open)]
            elif s[i] == ')':
                memo[(i, open)] = dfs(i + 1, open - 1)
                return memo[(i, open)]
            else:
                memo[(i, open)] = dfs(i + 1, open) or dfs(i + 1, open + 1) or dfs(i + 1, open - 1)
                return memo[(i, open)]

        return dfs(0, 0)
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Greedy]]
#### Important Subdetails

In this problem, we're actually tracking two greedy parameters simultaneously through `leftMin` and `leftMax` - they represent the bounds of a range:

1. `leftMin`: Represents the minimum number of unclosed left parentheses possible by greedily trying to use `*` as `)` whenever possible (minimizing)
2. `leftMax`: Represents the maximum number of unclosed left parentheses possible by greedily trying to use `*` as `(` whenever possible (maximizing)

- When we reset `leftMin` to 0, we're essentially saying: "Okay, we tried to use too many closing parentheses here. Let's backtrack and only use our wildcards as closing parentheses up to the number of opening parentheses we actually have."
	- Leftmin and max represent the range of our possible valid strings. Negative values are never valid so we essentially throw away accounting for the minimum values of wildcards that lead us to negative values

- Top down approach is standard dfs with memoization
	- We track index and also the number of open parentheses both of which make up the cache key


#### Runtime of Optimal Solution
- O(n^3) runtime for top down and O(n^2) space complexity
- O(n) runtime for greedy, O(1) space
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-06 18:40
