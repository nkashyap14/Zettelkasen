# Lowest Common Ancestor of a Binary Tree

#### Problem statement

Given a binary tree, find the lowest common ancestor (LCA) of two given nodes in the tree.

According to the [definition of LCA on Wikipedia](https://en.wikipedia.org/wiki/Lowest_common_ancestor): “The lowest common ancestor is defined between two nodes `p` and `q` as the lowest node in `T` that has both `p` and `q` as descendants (where we allow **a node to be a descendant of itself**).”

##### Example 1
```
**Input:** root = [3,5,1,6,2,0,8,null,null,7,4], p = 5, q = 1
**Output:** 3
**Explanation:** The LCA of nodes 5 and 1 is 3.
```
##### Example 2
```
**Input:** root = [3,5,1,6,2,0,8,null,null,7,4], p = 5, q = 4
**Output:** 5
**Explanation:** The LCA of nodes 5 and 4 is 5, since a node can be a descendant of itself according to the LCA definition.
```
#### Solution 1
```
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def lowestCommonAncestor(self, root, p, q):
        """
        :type root: TreeNode
        :type p: TreeNode
        :type q: TreeNode
        :rtype: TreeNode
        """        

        def dfs(curr):
            if not curr:
                return False
            #prefix order
            #check if left has p or q
            left = dfs(curr.left)
            #check if right has p or q
            right = dfs(curr.right)
            #check if the current node is p or q
            mid = curr == p or curr == q
            #if our boolean values add up to 2 truths than we set our answer to the current node
            if mid + left + right >= 2:
                self.res = curr
            return mid or left or right

        dfs(root)

  

        return self.res


=======================================================================================
Alternate way of coding the same thing
class Solution(object):
    def __init__(self):
        self.ans = None
    def lowestCommonAncestor(self, root, p, q):
        # We choose a different subproblem to be solved by recursion. Getting the answer to the original question is a 
        # side effect in the process. This is why most recursive solutions of this problems are hard to understand.
        # They mixes the original problem, the sub-problem we chose to solve and the side effects.
        def isPOrQInTheSubtree(root, p, q):
            if root == None:
                return False

            targetInLeftTree = isPOrQInTheSubtree(root.left, p, q)
            targetInRightTree = isPOrQInTheSubtree(root.right, p, q)
            rootIsTarget = (root == p) or (root == q)

            # the only line that has side effect.
            if (targetInLeftTree and targetInRightTree) or (targetInLeftTree and rootIsTarget) or (targetInRightTree and rootIsTarget):
                self.ans = root

            return targetInLeftTree or targetInRightTree or rootIsTarget

        isPOrQInTheSubtree(root, p, q)
        return self.ans

```


#### Solution 2: Iterative

```
class Solution(object):
    def lowestCommonAncestor(self, root, p, q):
        """
        :type root: TreeNode
        :type p: TreeNode
        :type q: TreeNode
        :rtype: TreeNode
        """      
        stack = [root]
        parent = {root: None}

        while p not in parent or q not in parent:
            node = stack.pop()
            if node.left:
                parent[node.left] = node
                stack.append(node.left)
            if node.right:
                parent[node.right] = node
                stack.append(node.right)

        ancestors = set()
        while p:
            ancestors.add(p)
            p = parent[p]

        while q not in ancestors:
            q = parent[q]
        return q
```
###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[binary tree]]
- 
#### Important Subdetails

- Second solution is an iterative solution that involves using a stack for depth first search and keeping a mapping of nodes to their parent pointers
- After populating the parents
	- Terminate the population after both p and q are in parent
- From there populate the complete set of ancestors for one of the nodes, p
- Then iterate through all of q's ancestors till you find the first ancestor that is in p's ancestors
- Return that
- The recursive solution is simple however it does a couple things. When making the recursive call assume you are getting the correct value
- You are checking for 3 things, if p or q are in left subtree, right subtree or they are equal to the current nodes value
- If 2 of the three boolean conditions are right than you know it is the lowest common ancestor

#### Runtime of Optimal Solution
- Solution 1's runtime would be O(n) where n is the number of nodes in the binary tree as in the worst case we might visit all nodes of the binary tree
- Similarly its space complexity is O(n) in the worst case of a skewed binary tree whose height is N
- Solution 2 is also O(n) for both for the same reason
--- 
Links :: [[#Example Code]] [[Computer Science]] [[Amazon Leetcode Problem]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-04 13:33
