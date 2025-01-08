# Delete Node in a BST

#### Problem statement

Given a root node reference of a BST and a key, delete the node with the given key in the BST. Return _the **root node reference** (possibly updated) of the BST_.

Basically, the deletion can be divided into two stages:

1. Search for a node to remove.
2. If the node is found, delete the node.
##### Example 1
```
```
##### Example 2
```
```
#### Solution
```
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution(object):
    def deleteNode(self, root, key):
        """
        :type root: Optional[TreeNode]
        :type key: int
        :rtype: Optional[TreeNode]
        """
        def successor(root):
            root = root.right
            while root.left:
                root = root.left
            return root.val

        def predecessor(root):
            root = root.left
            while root.right:
                root = root.right
            return root.val

        if not root:
            return None

        if key > root.val:
            root.right = self.deleteNode(root.right, key)
 
        if key < root.val:
            root.left = self.deleteNode(root.left, key)

        if key == root.val:
            if not (root.left or root.right):
                root = None

            #not a leaf node in that case will first try to replace with successor
            elif root.right:
                #swap the successors value into this ndoe
                root.val = successor(root)
                #go down the right tree to find the successor and delete it
                root.right = self.deleteNode(root.right, root.val)
            else:
                #swap the predecessors value into this node
                root.val = predecessor(root)
                #go down the tree to find the predecessor and delete it
                root.left = self.deleteNode(root.left, root.val)

        return root
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Binary Search Tree]]
#### Important Subdetails

- Hinges on the concept of a binary search tree which guarantees an in order traversal. Means that when removing a node we have to either remove it completely as it is a leaf node or if it has a successor or predecssor replace it with that appropraiately (favoring the successor)
- Way we solve it is by first finding the node to delete. if its a leaf node simply set it to none
	- first if the roots val is > key that means the node to delete will be in the left subtree and vice versa
	- otherwise if its not a leaf we have to find the successor or predecessor value swap its value into the current node and then continue down the tree to remove that successor or ppredecssor as well
#### Runtime of Optimal Solution

- O(log n) runtime
- O(H) is height of the tree and space complexity. Could be O(log N) for a balanced tree
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-01-02 16:58
