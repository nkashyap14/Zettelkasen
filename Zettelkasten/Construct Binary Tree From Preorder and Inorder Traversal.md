# Construct Binary Tree From Preorder and Inorder Traversal

#### Problem statement

You are given two integer arrays `preorder` and `inorder`.

- `preorder` is the preorder traversal of a binary tree
- `inorder` is the inorder traversal of the same tree
- Both arrays are of the same size and consist of unique values.

Rebuild the binary tree from the preorder and inorder traversals and return its root.
##### Example 1
```
Input: preorder = [1,2,3,4], inorder = [2,1,3,4]

Output: [1,2,3,null,null,null,4]
```
##### Example 2
```
Input: preorder = [1], inorder = [1]

Output: [1]
```
#### Solution
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
  
class Solution:
    def buildTree(self, preorder: List[int], inorder: List[int]) -> Optional[TreeNode]:
        if not preorder or not inorder:
            return None
        root = preorder[0]
        mid = inorder.index(preorder[0])
        root.left = self.buildTree(preorder[1 : mid + 1], inorder[:mid])
        root.right = self.buildTree(preorder[mid + 1:], inorder[mid + 1:])
  
        return root
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Binary Tree]]
- [[In order traversal]]
- [[Pre order traversal]]
#### Important Subdetails

- Preorder traversal the root is always at index 0
- if either of the lists are empty we've hit our base case and can return. We've built out that side of the tree
- In order traversal the index of the root is the midpoint of the array. We can use that to pass in the values before it into the recursive left child subcase and the values after it into the right child subcase
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
Date :: 2024-10-11 10:16
