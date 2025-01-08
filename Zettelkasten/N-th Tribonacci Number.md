# N-th Tribonacci Number

#### Problem statement

Given a number `n`, calculate the corresponding Tribonacci number. The Tribonacci sequence TnTn​ is defined as:
$$
T_0 = 0, T_1 = 1, T_2 = 2, T_n = (T_{n - 1} + T_{n - 2} + T_{n - 3})
$$

The input number, `n`, is a non-negative integer.

**Constraints:**

- 0≤0≤ `n` ≤37≤37
- The answer is guaranteed to fit within a 32-bit integer, i.e., answer ≤231−1≤231−1
##### Example 1
```
Input: 0
Answer: 0
```
##### Example 2
```
Input: 2
Answer: 1
```
#### Solution
```
def find_tribonacci(n):
    if not n:
      return 0
    if n == 1 or n == 2:
      return 1
    # Replace this placeholder return statement with your code
    dp = [0] * (n + 1)
    dp[2], dp[1] = 1, 1 
    
    for i in range(3, n + 1):
      dp[i] = dp[i - 1] + dp[i - 2] + dp[i - 3]
    return dp[n]
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Dynamic Programming]]
#### Important Subdetails

- The solultion shown is a bottom up approach where we build a dp array. This is a 1d dp problem where the state being indexed on is n where the array value represents the nth fibonacci number
- The reason we can do this is because each tribonacci number is a number that can be built off of subproblems whose results can be found in the array

#### Runtime of Optimal Solution
- O(n) runtime and O(n) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-27 15:52
