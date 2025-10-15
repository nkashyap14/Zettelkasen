# Binary Tree Preorder Iterative Traversal

#### Pattern statement

- Traverses a [[binary tree]] in a pre order manner. Pre order meaning that first some work is conducted on the root node. Then we go traverse the subtrees. Normally going to left sub tree first and then right subtree.
- Fundamentally this is a [[depth first search]] algorithm
- The interesting part about this is that it doesn't maintain a stack while traveling down the tree which saves space. 
- Core idea is to create temporary threads (links) from nodes back to their ancestors so that we can traverse without a stack

##### Implementation
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def preorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        node, output = root, []
        while node:
	        #if there is no left subtree
	        #process the current node and go right. Simple part of preorder traversal
		    #while processing the left subtree we eventually reach the rightmost node of that left subtree. 
            if not node.left:
                output.append(node.val)
                node = node.right # we have followed the thread back up the tree theoretically
            else:
				
				#find the immediate predecessor of the current node
				#the node that would come before this node in an inorder traversal
                pred = node.left
                while pred.right and pred.right is not node:
                    pred = pred.right

				#two options ended the loop. first case is that we ended up at a leaf node that doesnt have a pred.right!
				#in that case we must link it back to its next node aka the node that comes after it in an in order traversal
                if not pred.right:
	                #we know we have reached the RIGHT MOST node in the node's left subtree
	                #as it is preorder we can immediatlye process this node. then we can go explore its left subtreee
		            #process the node
                    output.append(node.val)
                    #create a link back. This functions as a breadcrumb so that when we finish the left subtree and reach back to pred we can follow the thread back up to node and then process node's right subtree. This is how we save the stack space
                    pred.right = node
                    #begin processing the nodes left subtree
                    node = node.left
                else: # we have reached a predecssor that points back to the current node aka we are processing this node twice. break the thread to fix the tree structure and then begin processing the nodes right subtree
                    pred.right = None
                    node = node.right
        return output


```

###### Programming Language Utilized:

[[Python]]

#### Runtime + Space Complexity

- O(n) runtime: We have a 2 x because ew hit every node twice beofr efinding its predecssor and breaking the thread 
- O(1) space complexity
---
Links :: [[#Example Code]] [[Leetcode]] [[Leetcode Pattern Implementation]] [[Binary Tree]] 
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-15 16:46
