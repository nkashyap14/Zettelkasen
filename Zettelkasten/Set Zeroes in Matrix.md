# Set Zeroes in Matrix

#### Problem statement
Given an `m x n` matrix of integers `matrix`, if an element is `0`, set its entire row and column to `0`'s.

You must update the matrix _in-place_.

**Follow up:** Could you solve it using `O(1)` space?

##### Example 1
```
Input: matrix = [
  [0,1],
  [1,1]
]

Output: [
  [0,0],
  [0,1]
]
```
##### Example 2
```
Input: matrix = [
  [1,2,3],
  [4,0,5],
  [6,7,8]
]

Output: [
  [1,0,3],
  [0,0,0],
  [6,0,8]
]
```
#### Solution
```
class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:

        ROWS, COLS = len(matrix), len(matrix[0])

        rowZero = False

        #determine which rows and columns need to be 0
        #reason we can use the first values in the row/col and overwrite them
        #is we have alread;y seen their value by the time we overwrite them to indicate
        #they need to be zeroed out

        for r in range(ROWS):
            for c in range(COLS):
                if matrix[r][c] == 0:
                    #first value in a column tells us which column needs to be zeroed
                    #marked for later
                    matrix[0][c] = 0


                    #first value in a row tells us which row needs to be zeroed
                    if r > 0:
                        matrix[r][0] = 0

                    #except for the case of it being the first row as we allocate that first value to
                    #the column to be zeroed so we can just a boolean var
                    else:
                        rowZero = True

        #zero out most of the matrix
        for r in range(1, ROWS):
            for c in range(1, COLS):
                if matrix[0][c] == 0 or matrix[r][0] == 0:
                    matrix[r][c] = 0

  

        #zero out first column if we need to. 0, 0 index tells us if we 0 out first column
        #first value in row holds whether or not we zeor out the row except for the first row/column which is handled
        #by a boolean as we can't overlap
        if matrix[0][0] == 0:
            for r in range(ROWS):
                matrix[r][0] = 0

        if rowZero:
            for c in range(COLS):
                matrix[0][c] = 0
```

###### Programming Language Utilized:

 - [[Python]]
###### Data structure utilized:
#### Important Subdetails

#### Runtime of Optimal Solution

- O(m x n) runtime. O(1) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-19 12:46
