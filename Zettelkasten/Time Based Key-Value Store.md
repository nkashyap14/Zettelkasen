# Time Based Key-Value Store

#### Problem statement
Implement a time-based key-value data structure that supports:

- Storing multiple values for the same key at specified time stamps
- Retrieving the key's value at a specified timestamp

Implement the `TimeMap` class:

- `TimeMap()` Initializes the object.
- `void set(String key, String value, int timestamp)` Stores the key `key` with the value `value` at the given time `timestamp`.
- `String get(String key, int timestamp)` Returns the most recent value of `key` if `set` was previously called on it _and_ the most recent timestamp for that key `prev_timestamp` is less than or equal to the given timestamp (`prev_timestamp <= timestamp`). If there are no values, it returns `""`.

Note: For all calls to `set`, the timestamps are in strictly increasing order.

##### Example 1
```
Input:
["TimeMap", "set", ["alice", "happy", 1], "get", ["alice", 1], "get", ["alice", 2], "set", ["alice", "sad", 3], "get", ["alice", 3]]

Output:
[null, null, "happy", "happy", null, "sad"]

Explanation:
TimeMap timeMap = new TimeMap();
timeMap.set("alice", "happy", 1);  // store the key "alice" and value "happy" along with timestamp = 1.
timeMap.get("alice", 1);           // return "happy"
timeMap.get("alice", 2);           // return "happy", there is no value stored for timestamp 2, thus we return the value at timestamp 1.
timeMap.set("alice", "sad", 3);    // store the key "alice" and value "sad" along with timestamp = 3.
timeMap.get("alice", 3);           // return "sad"
```
#### Solution
```
class TimeMap:
    def __init__(self):
        self.keyStore = {}

    def set(self, key: str, value: str, timestamp: int) -> None:
        if key not in self.keyStore:
            self.keyStore[key] = []
        self.keyStore[key].append([value, timestamp])

    def get(self, key: str, timestamp: int) -> str:
        res, values = "", self.keyStore.get(key, [])
        l, r = 0, len(values) - 1
        while l <= r:
            m = (l + r) // 2
            if values[m][1] <= timestamp:
                res = values[m][0]
                l = m + 1
            else:
                r = m - 1
        return res
```

###### Programming Language Utilized:

- [[Python]]
###### Data structure utilized:

- [[Binary Search]]
#### Important Subdetails

- Pay attention to constraints and see if you can glean information. in this problem the constraint was that timestamp is increasing order so that allows us to know that the timestamp list will always be in sorted order allowing us to meet the precondition of [[Binary Search]] and allowing us to run a log(n) search
#### Runtime of Optimal Solution
- O(log n) as the runtime conmes from binary search and we know that getting in a hashmap is O(1) operation
---
Links :: [[#Example Code]] [[Computer Science]] [[Neetcode 150]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-22 13:34
