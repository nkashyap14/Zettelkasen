# LRUCache

#### Problem statement

Implement the [Least Recently Used (LRU)](https://en.wikipedia.org/wiki/Cache_replacement_policies#LRU) cache class `LRUCache`. The class should support the following operations

- `LRUCache(int capacity)` Initialize the LRU cache of size `capacity`.
- `int get(int key)` Return the value corresponding to the `key` if the `key` exists, otherwise return `-1`.
- `void put(int key, int value)` Update the `value` of the `key` if the `key` exists. Otherwise, add the `key`-`value` pair to the cache. If the introduction of the new pair causes the cache to exceed its capacity, remove the least recently used key.

A key is considered used if a `get` or a `put` operation is called on it.

Ensure that `get` and `put` each run in O(1)O(1) average time complexity.
##### Example 1
```
Input:
["LRUCache", [2], "put", [1, 10],  "get", [1], "put", [2, 20], "put", [3, 30], "get", [2], "get", [1]]

Output:
[null, null, 10, null, null, 20, -1]

Explanation:
LRUCache lRUCache = new LRUCache(2);
lRUCache.put(1, 10);  // cache: {1=10}
lRUCache.get(1);      // return 10
lRUCache.put(2, 20);  // cache: {1=10, 2=20}
lRUCache.put(3, 30);  // cache: {2=20, 3=30}, key=1 was evicted
lRUCache.get(2);      // returns 20 
lRUCache.get(1);      // return -1 (not found)
```

#### Solution
```
class Node:
    def __init__(self, key, val):
        self.key, self.val = key, val
        self.prev = self.next = None

class LRUCache:
    def __init__(self, capacity: int):
        self.cache = {}
        self.capacity = capacity

        #dummy nodes. left.right is the least recently used, right.prev is the most recently used
        self.left, self.right = Node(0, 0), Node(0, 0)
        self.left.next, self.right.prev = self.right, self.left

    #removes the node from our doubly linked list
    def remove(self, node):
        prev, nxt = node.prev, node.next
        prev.next, nxt.prev = nxt, prev

    #inserts the node as the most recently used
    def insert(self, node):
        prev, nxt = self.right.prev, self.right
        prev.next = nxt.prev = node
        node.next, node.prev = nxt, prev

    def get(self, key: int) -> int:
        if key in self.cache:
            self.remove(self.cache[key])
            self.insert(self.cache[key])
            return self.cache[key].val
        return -1

  

    def put(self, key: int, value: int) -> None:
        if key in self.cache:
            self.remove(self.cache[key])
        self.cache[key] = Node(key, value)
        self.insert(self.cache[key])

        if len(self.cache) > self.capacity:
            lru = self.left.next
            self.remove(lru)
            del self.cache[lru.key]
```

###### Programming Language Utilized:
 - [[Python]]
###### Data structure utilized:

- [[Doubly Linked List]]
- [[Linked List]]
- [[hashmap]]
#### Important Subdetails

- The general idea of this solution hinges on two data structures
- One data structure you maintain is a simple hashmap. This maps keys to nodes to provide O(1) return for the get command
- The second data structure we maintain is a doubly linked list. The left side of the linked list is used as the least recently used side of the keys in the cache. The right side of the linked list is the most recently used value.
	- We make sure to maintain dummy nodes that hold no real values to provide easy access to both ends
	- From there we just have to make sure that when we add to the cache or get a value from the cache we move the nodes to the right side
	- When we delete a value from the cache we simply remove the leeast recently used which is as simple as getting the next value of the left pointer and pointing it at the node to the right of next and pointing that node back at the left pointer
- Make sure to do a check where when we exceed capacity we grab the least recently used value and delete that key from the cache as well
	- Make sure to remove it two locations
	- Hashmap mapping and the doubly linked list that functions as a cache
- Maintain two helper methods that 1.) remove a node from the cache by just pointing its prev and next nodes at each other
	- dont have to worry about null checks as left and right dummy nodes exist
	- Another helper method that adds a node to the right end (most recently used end) of the doubly linked list 
#### Runtime of Optimal Solution

- O(1) for put and get 
- O(n) space complexity
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-10 13:32
