# Counting Bits

#### Problem statement

Given an integer `n`, count the number of `1`'s in the binary representation of every number in the range `[0, n]`.

Return an array `output` where `output[i]` is the number of `1`'s in the binary representation of `i`.
##### Example 1
```
Input: n = 4

Output: [0,1,1,2,1]
```
#### Solution
```
class Solution:
    def countBits(self, n: int) -> List[int]:
        output = []

        for i in range(n + 1):
            count = 0
            for j in range(10):
                if i & (1 << j):
                    count += 1

            output.append(count)

        return output
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Bit Manipulation]]
#### Important Subdetails

- The shift operator only shifts the one to the specific bit position. It doesn't fill in rest of bit positions with 1's it fills them with 0's.
- The  & with the number checks if that specific j position on the number has a 1 or 0. if it has  1 that will evaluate to true and count is incremented by one
- Range over 10 because the constraints of hte probelm was 0 <= n <= 1000 so don't need to check excessive bits

#### Runtime of Optimal Solution

- O(n) runtime and O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-16 10:02
