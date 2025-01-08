# Dynamic Programming

## Summary

- Some computational problems that can be solved by recursively applying a divide and conquer approach have an optimal substructure
	- The solution to a smaller problem helps us solve the bigger one
- Two approaches to saving computations by reusing previous calculations of subproblems
	- Top-Down Approach
		- A recursive approach that stores the results of redundant function calls to avoid repeating calculations
		- Also called memoization
		- Usually implemented as an enhancement of the naïve recursive solution
		- Takes up additional space in memory because it stores intermediate results in a lookup table
	- Bottom-Up Approach:
		- An iterative strategy that systematically fills a table with results of subproblems to solve larger problems efficiently
		- Also known as tabulation
		- The smallest problem is solved first
		- Results are saved
		- And then larger subproblems are computed based on evaluated results
		- For larger subproblems we fetch the results of the preceding subproblems and use the results to get the solution to the current subproblem
- When to use Dynamic Programming:
	- Overlapping Subproblems:
		- There are overlapping subproblems where you can use the results of one subproblem when solving another possibly larger subproblem
	- Optimal Substructure:
		- Problems where the final solution can be constructed from optimal solutions to its subproblems
## Subproblems

- [[0/1 Knapsack]]
- [[Coin Change]]
- [[N-th Tribonacci Number]]
- [[Maximum Product Subarray]]
- [[Word Break]]
- [[Longest Increasing Subsequence]]
- [[Partition Equal Subset Sum]]
## Details

## Terms Defined


Type :: #topic
Links :: [[Computer Science]]
Reference :: [[Educative]]
Date ::  2024-12-04 05:41