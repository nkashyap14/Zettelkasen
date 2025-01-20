# Rotate Matrix

#### Problem statement

Given a square `n x n` matrix of integers `matrix`, rotate it by 90 degrees _clockwise_.

You must rotate the matrix _in-place_. Do not allocate another 2D matrix and do the rotation.
##### Example 1
```
Input: matrix = [
  [1,2],
  [3,4]
]

Output: [
  [3,1],
  [4,2]
]
```
##### Example 2
```
Input: matrix = [
  [1,2,3],
  [4,5,6],
  [7,8,9]
]

Output: [
  [7,4,1],
  [8,5,2],
  [9,6,3]
]
```
#### Solution
```
class Solution:
    def rotate(self, matrix: List[List[int]]) -> None:

        L, R = 0, len(matrix) - 1

        while L < R:
            #iterate over the entire row except the last element
            #so r - l - 1 or r - l as range is exclusive for the value
            for i in range(R - L):

                top, bottom = L, R

                #get top left while iterating over the top row
                #top left position we move one spot to the right so col + i
                topLeft = matrix[top][L + i]

  

                #move bottom left into top left
                #for bottom left we move one spot up so row - i
                matrix[top][L + i] = matrix[bottom - i][L]

                #move bottom right into bottom left
                #from bottom right we move one spot to the left so col - i
                matrix[bottom - i][L] = matrix[R][bottom - i]

                #move top right into bottom left
                #from top right we move one spot down so row + i
                matrix[R][bottom - i] = matrix[top + i][R]

                #move top left into top right
                matrix[top + i][R] = topLeft

            L += 1

            R -= 1
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
#### Important Subdetails

#### Runtime of Optimal Solution

- O(n^2) runtime and O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-19 12:24
