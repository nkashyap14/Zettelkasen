# Kth Smallest Element in a BST

#### Problem statement

Given the `root` of a binary search tree, and an integer `k`, return the `kth` smallest value (**1-indexed*) in the tree.

A **binary search tree** satisfies the following constraints:

- The left subtree of every node contains only nodes with keys **less than** the node's key.
- The right subtree of every node contains only nodes with keys **greater than** the node's key.
- Both the left and right subtrees are also binary search trees.

##### Example 1
```
Input: root = [2,1,3], k = 1

Output: 1
```
##### Example 2
```
Input: root = [4,3,5,2,null], k = 4

Output: 5
```
#### Solution
```
class Solution:
    def kthSmallest(self, root: Optional[TreeNode], k: int) -> int:
        stack = []
        curr = root

        while stack or curr:
            while curr:
                stack.append(curr)
                curr = curr.left

            curr = stack.pop()
            k -= 1
            if k == 0:
                return curr.val

            curr = curr.right
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Binary Search Tree]]
- [[Stack]]
#### Important Subdetails

- This is [[In order traversal]] except done iteratively. We can also do it recursively just need to populate a stack and hten return the k index

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
Date :: 2024-10-10 14:57
