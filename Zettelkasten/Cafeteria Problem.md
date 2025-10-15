# Cafeteria Problem

#### Problem statement

A cafeteria table consists of a row of N seats, numbered from 1 to N from left to right. Social distancing guidelines require that every diner be seated such that K seats to their left and K seats to their right (or all the remaining seats to that side if there are fewer than K) remain empty.

There are currently M diners seated at the table, the ith of whom is in seat Si​. No two diners are sitting in the same seat, and the social distancing guidelines are satisfied.

Determine the maximum number of additional diners who can potentially sit at the table without social distancing guidelines being violated for any new or existing diners, assuming that the existing diners cannot move and that the additional diners will cooperate to maximize how many of them can sit down.
##### Example 1
```
N = 10
K = 1
M = 2
S = [2, 6]

Return 3
```
##### Example 2
```
N = 15
K = 2
M = 3
S = [11, 6, 14]

Return 1
```
#### Solution
```
from typing import List
# Write any import statements here

def getMaxAdditionalDinersCount(N: int, K: int, M: int, S: List[int]) -> int:
  # Write your code here
  
  S.sort()
  
  res = (S[0] - 1) // (K + 1)
  
  for i in range(1, len(S)):
    res += (S[i] - S[i - 1] - K - 1) // (K + 1)
    
  res += (N - S[-1]) // (K + 1)
  return res
  
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Greedy]]
#### Important Subdetails

- Idea is to find how many blocks of size (K + 1) can fit in a range between two already seated diners
	- Reason is (K + 1) is the distance needed to place another diner. k is the empty seats and then the + 1 to accomodate for the diner
- Because diners already seaten we can fit blocks from S[I] only up to:
	- S[i + 1] - (K + 1)
- Sort seating arrangemnet as input isnt sorted
- First check how many we can fit in between 1 and S[0]
	- this is done by S[0] - 1 // (K + 1)
- Then check for each of the diner segments how many we can fit
	- (S[i] - s[i - 1] - K - 1 )// (K + 1)
	- First we get the distance of the segment
	- This is from (s[i] - (k + 1)) to s[i - 1]
		- Reason you subtract (K + 1) is that you know from the next diner you will need at least a (k + 1) distance
- Then finally once out of hte loop do an ending calculation from the final seat to the end of range
	- this is N - S[-1] // (k + 1)
- return the result
#### Runtime of Optimal Solution

- Time complexity is O(m log m) for sorting + O(m) for the forloop calculation
- Results in O(m log m)
- O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Meta Coding Puzzles]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-04-10 15:01
