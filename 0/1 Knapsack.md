# 1 Knapsack

#### Problem statement

## Statement

You are given nn items whose weights and values are known, as well as a knapsack to carry these items. The knapsack cannot carry more than a certain maximum weight, known as its **capacity**.

You need to maximize the total value of the items in your knapsack, while ensuring that the sum of the weights of the selected items does not exceed the capacity of the knapsack.

If there is no combination of weights whose sum is within the capacity constraint, return 0

**Constraints:**

- 1≤1≤ `capacity` ≤1000≤1000
- 1≤1≤ `values.length` ≤500≤500
- `weights.length` ==== `values.length`
- 1≤1≤ `values[i]` ≤1000≤1000
- 1≤1≤ `weights[i]` ≤≤ `capacity`
##### Example 1
```
```
##### Example 2
```
```
#### Solution 1: Bottom Up
```
def find_max_knapsack_profit(capacity, weights, values):

    # Replace this placeholder return statement with your code
    #i represents the item while j represents the current capacity
    dp = [[0] * (capacity + 1) for _ in range(len(weights) + 1)]
    for i in range(1, len(weights) + 1):
      for j in range(1, capacity + 1):
        #second case is the case where we exclude the current item. first case is the case where we include the 
        #current item. we have to pick whatever maximizes between the two 
        #values[i - 1] because we are 1 indexing in the dp array
        #same with the - weights[i - 1]
        #dp[i - 1] represents the best combinations with i - 1 items so not considering the current item
        #so we are getting the best possible values combination of i - 1 items at the previous capacity
        #and adding it to the value of the current item
        if weights[i - 1] <= j:
          dp[i][j] = max(values[i - 1] + dp[i-1][j - weights[i - 1]], dp[i - 1][j])
        #the weight of hte current item is too big so we can't incnlude it
        else:
          dp[i][j] = dp[i - 1][j]
    return dp[-1][-1]

```

#### Solution 2: Top Down
```
def find_max_knapsack_profit(capacity, weights, values):
  n = len(weights)
  dp = [[-1 for i in range(capacity + 1) for _ in range(n + 1)]]
  
  return find_max_knapsack_profit_helper(capacity, weights, values, n, dp)

def find_max_knapsack_profit_helper(capacity, weights, values, n, dp):
  if n == 0 or capacity == 0:
    return 0
    
  if dp[n][capacity] != -1:
    return dp[n][capacity]
    
  if weights[n - 1] <= capacity:
    dp[n][capacity] = max(
      values[n - 1] + find_max_knapsack_profit_helper(capacity-weights[n - 1], weights, values, n - 1, dp),
      find_max_knapsack_profit_helper(capacity, weights, values, n - 1, dp)
      )
      return dp[n][capacity]
      
  dp[n][capacity] = find_max_knapsack_profit_helper(capacity, weights, values, n - 1, dp)
  return dp[n][capacity]
```

#### Alternative Top Down Solution

```
def find_max_knapsack_profit(capacity, weights, values):
  def helper(curr_cap, i, seen):
    if i == len(weights) or curr_cap == 0:
        return 0
      
    if (i, curr_cap) in seen:
       return seen[(i, curr_cap)]
       
    if weights[i] <= curr_cap:
      seen[(i, curr_cap)] = max(
        values[i] + helper(curr_cap - weights[i], i + 1, seen),
        helper(curr_cap, i + 1, seen))
      return seen[(i, curr_cap)]
      
    seen[(i, curr_cap)] = helper(curr_cap, i + 1, seen)
    
    return seen[(i, curr_cap)]

  return helper(capacity, 0, {})
```
#### Solution 3: Bottom Up Space Optimized:

```
import copy
def find_max_knapsack_profit(capacity, weights, values):
  n = len(weights)
  
  #the previous row that is used to fill the ith row
  dp = [0] * (capacity + 1)
  
  #the current row
  temp = [0] * (capacity + 1)
  
  for i in range(0, n ):
    for j in range(1, capacity + 1):
      if weights[i] <= j:
        temp[j] = max(values[i] + dp[j - weights[i]], dp[j])
      else:
        temp[j] = dp[j]
    dp = copy.deepcopy(temp)
  
  return dp[capacity]
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Dynamic Programming]]
#### Important Subdetails

- In the top down solution with memoization with the dict I need to track both index and curr_capacity as each index can be part of different subproblems depending on what the current capacity is left.
- Space optimized solution hinges on the idea that to calculate the ith items values for capacity we only need the i -1 item adn we don't need the rest of the i - 2 items so we only need 2 arrays of length capacity + 1
#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Educative Leetcode Problem]] 
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-04 06:26
