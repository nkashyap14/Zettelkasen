# Copy List with Random Pointer

#### Problem statement

You are given the head of a linked list of length `n`. Unlike a singly linked list, each node contains an additional pointer `random`, which may point to any node in the list, or `null`.

Create a **deep copy** of the list.

The deep copy should consist of exactly `n` **new** nodes, each including:

- The original value `val` of the copied node
- A `next` pointer to the new node corresponding to the `next` pointer of the original node
- A `random` pointer to the new node corresponding to the `random` pointer of the original node

Note: None of the pointers in the new list should point to nodes in the original list.

_Return the head of the copied linked list._

In the examples, the linked list is represented as a list of `n` nodes. Each node is represented as a pair of `[val, random_index]` where `random_index` is the index of the node (0-indexed) that the `random` pointer points to, or `null` if it does not point to any node.
##### Example 1
```
Input: head = [[3,null],[7,3],[4,0],[5,1]]

Output: [[3,null],[7,3],[4,0],[5,1]]
```
##### Example 2
```
Input: head = [[1,null],[2,2],[3,2]]

Output: [[1,null],[2,2],[3,2]]
```
#### Solution
```
"""
# Definition for a Node.
class Node:
    def __init__(self, x: int, next: 'Node' = None, random: 'Node' = None):
        self.val = int(x)
        self.next = next
        self.random = random

"""

class Solution:
    def copyRandomList(self, head: 'Optional[Node]') -> 'Optional[Node]':
        oldToCopy = {None: None}
        
        curr = head
        while curr:
            oldToCopy[curr] = Node(curr.val)
            curr = curr.next

        curr = head

        while curr:
            oldToCopy[curr].next = oldToCopy[curr.next]
            oldToCopy[curr].random = oldToCopy[curr.random]
            curr = curr.next

        return oldToCopy[head]
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Linked List]]
- [[hashmap]]
#### Important Subdetails

- Initialize the hashmap with a mapping of none to none so that if a random or next points to None then the hashmap doesn't error out with the key
- Requires two passes of the linked list to go through. first tiem we initialize the hashmap with the copy nodes
- Second run through we initialize the random and next pointers. Each need to point to a new copy so that's why we had to wait to the second run through to initalize it
#### Runtime of Optimal Solution

- O(n) runtime
- O(n) space complexity as we keep a mapping of the old nodes to new nodes
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-13 09:11
