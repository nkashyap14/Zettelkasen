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


#### Solution 2: Optimized:

```
class Solution(object):
    def buildTree(self, preorder, inorder):
        # Create HashMap for O(1) lookup of inorder indices
        indexes = {val : idx for idx, val in enumerate(inorder)}

        def dfs(pre_start, pre_end, in_start, in_end):
            if pre_start > pre_end:
                return None
            
            # First element in preorder is always root
            root = TreeNode(preorder[pre_start])

            # Get root's position in inorder traversal
            index = indexes[root.val]
            
            # Calculate number of nodes in left subtree
            # (everything before root in inorder is in left subtree)
            left_sub = index - in_start

            # Left subtree:
            # preorder: take left_sub nodes after root
            # inorder: take everything before root
            root.left = dfs(pre_start + 1,           # skip root
                          pre_start + left_sub,      # take left_sub nodes
                          in_start,                  # keep same start
                          index - 1)                 # end before root

            # Right subtree:
            # preorder: take remaining nodes after left subtree
            # inorder: take everything after root
            root.right = dfs(pre_start + left_sub + 1,  # skip root and left subtree
                           pre_end,                     # take until end
                           index + 1,                   # start after root
                           in_end)                      # keep same end

            return root

        length = len(preorder)
        return dfs(0, length - 1, 0, length - 1)
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
- Solution 2
1. left_sub = index - in_start tells us how many nodes are in the left subtree
    - index is root's position in inorder array
    - in_start is where current inorder portion begins
    - Their difference tells us size of left subtree because in inorder, everything before root is in left subtree
2. For left subtree recursion:
    - pre_start + 1: we skip the root in preorder
    - pre_start + left_sub: we take only left_sub number of nodes (size of left subtree)
    - in_start: keep same start in inorder
    - index - 1: stop before root in inorder
3. For right subtree recursion:
    - pre_start + left_sub + 1: skip root and left subtree nodes in preorder
    - pre_end: take remaining nodes
    - index + 1: start after root in inorder
    - in_end: keep same end in inorder
#### Runtime of Optimal Solution

- The first runtime is O(n^2) in reality because we are running the index operation n times which is a n call 
- The second is more optimized because of two reasons, we create a hashmap of index mappings and we also refrain from using slices of array which requires a copy each time in python but instead pass in start and end indexes to each array
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
