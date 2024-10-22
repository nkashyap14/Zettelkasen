# Generate Parentheses

#### Problem statement

You are given an integer `n`. Return all well-formed parentheses strings that you can generate with `n` pairs of parentheses.
##### Example 1
```
Input: n = 1

Output: ["()"]
```
##### Example 2
```
Input: n = 3

Output: ["((()))","(()())","(())()","()(())","()()()"]
```
#### Solution
```
class Solution:
    def generateParenthesis(self, n: int) -> List[str]:
        stack = []
        res = []

        def dfs(opened, close):
            if n == opened == close:
                res.append("".join(stack))
                return

            if opened < n:
                stack.append("(")
                dfs(opened + 1, close)
                stack.pop()

            if close < opened:
                stack.append(")")
                dfs(opened, close + 1)
                stack.pop()

        dfs(0, 0)
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Stack]]
- [[Backtracking]]
#### Important Subdetails

- 
#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-10 10:02
