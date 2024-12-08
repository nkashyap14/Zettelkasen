# Spiral Matrix

#### Problem statement

Given an `m x n` matrix of integers `matrix`, return a list of all elements within the matrix in _spiral order_.
##### Example 1
```
Input: matrix = [[1,2],[3,4]]

Output: [1,2,4,3]
```
##### Example 2
```
Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]

Output: [1,2,3,6,9,8,7,4,5]
```
#### Solution 1
```
class Solution(object):
    def spiralOrder(self, matrix):
        """
        :type matrix: List[List[int]]
        :rtype: List[int]
        """
        res = []

        rows, columns = len(matrix), len(matrix[0])

        up = left = 0
        right = columns - 1
        down = rows - 1

        while len(res) < rows * columns:
            
            #left to right
            for col in range(left, right + 1):
                res.append(matrix[up][col])
            
            #up to down
            for row in range(up + 1, down + 1):
                res.append(matrix[row][right])

            # right to left
            if up != down:
                #go right to left
                for col in range(right - 1, left - 1, -1):
                    res.append(matrix[down][col])

            # down to up
            if left != right:
                for row in range(down - 1, up, -1):
                    res.append(matrix[row][left])

            left += 1
            right -= 1
            down -= 1
            up += 1
    
        return res

```

#### Solution 2:

```
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        res = []
        left, right = 0, len(matrix[0])
        top, bottom = 0, len(matrix)

        while left < right and top < bottom:
            #get every i in the top row
            for i in range(left, right):
                res.append(matrix[top][i])
            top += 1

            #get every i in the right col
            for i in range(top, bottom):
                res.append(matrix[i][right - 1])
            right -= 1

            if not (left < right and top < bottom):
                break
                
            #get every i in the bottom row
            for i in range(right - 1, left - 1, -1):
                res.append(matrix[bottom - 1][i])
            bottom -= 1

            #get every i in the left column
            for i in range(bottom - 1, top - 1, -1):
                res.append(matrix[i][left])
                left += 1

        return res
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:
#### Important Subdetails

- 4 boundaries
- We are shrinking the boundaries every time
- If top == bottom or left == right than we know we have a single row or single column matrix so we don't want to put repeat elements

#### Runtime of Optimal Solution

- O(m * n) runtime
---
Links :: [[#Example Code]] [[Computer Science]] [[Amazon Leetcode Problem]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-04 11:39
