# Meeting Rooms II

#### Problem statement

Given an array of meeting time intervals `intervals` where `intervals[i] = [starti, endi]`, return _the minimum number of conference rooms required_.
##### Example 1
```
**Example 1:**

**Input:** intervals = [[0,30],[5,10],[15,20]]
**Output:** 2
```
##### Example 2
```
**Example 2:**

**Input:** intervals = [[7,10],[2,4]]
**Output:** 1
```
#### Solution 1
```
class Solution(object):
    def minMeetingRooms(self, intervals):
        """
        :type intervals: List[List[int]]
        :rtype: int
        """

        starts = []
        ends = []

        for i in intervals:
            starts.append(i.start)
            ends.append(i.end)

        starts.sort()
        ends.sort()

        s = e = 0
        numRooms = available = 0
        while s < len(starts):
            if starts[s] < ends[e]:
                if available == 0:
                    numRooms += 1
                else:
                    available -= 1
                s += 1
            else:
                available += 1
                e += 1

        return numRooms
```

#### Solution 2
```
def minMeetingRooms(self, intervals):
        intervals.sort(key=lambda x:x[0])
        heap = []  # stores the end time of intervals
        for i in intervals:
            if heap and i[0] >= heap[0]:
                # means two intervals can use the same room
                heapq.heapreplace(heap, i[1])
            else:
                # a new room is allocated
                heapq.heappush(heap, i[1])
        return len(heap)
```

#### Solution 3
```
class Solution:
    def minMeetingRooms(self, intervals: List[Interval]) -> int:
        start = sorted([interval.start for interval in intervals])
        end = sorted([interval.end for interval in intervals])

        i = j = count = res = 0
        while i < len(start):
            if start[i] < end[j]:
                count += 1
                i += 1
            else:
                count -= 1
                j += 1
            res = max(res, count)
        return res

```
###### Programming Language Utilized:
- [[Python]]
###### Data structure utilized:
- [[Minheap]]
#### Important Subdetails

- Solution to this problem revolves around the idea that two intervals can share a room if the start of one interval is after the end of another
- Solution 1 sets up 2 arrays, start and end which both are sorted. from there you need to iterate over all the start times of the array
	- if a start time is lower than an endtime it means we need to either spin up a new room or use an available room. we track available rooms and num rooms. if availabel rooms are 0 we need to spin up a new room otherwise we just decrement available rooms.  we also increment our start pointer. we have an end pointer as well
	- in the case that our start time is after our end time it means we have a meeting that can end before we start. so we increment available and also increment our end pointer to go to the next instance
	- at the end we return our counter of numrooms
- Solution 2 takes advantage of this by first sorting the array by the start times
- from there you populate a heap such that at the end of the population the length of the heap is the amount of rooms you need
	- you do this by pushing onto the heap end times of a room if you need a new room
		- this occurs either when the heap is empty or the start time of the current room is less than the endtime of the minimum end time on the heap (minimum because it is minheap)
	- if the start time of the current meeting is greater than the end time of the earliest room being finished means we know that this current meeting can take over the room of the current meeting on the heap. so we run a heapreplace on the value and push the end time of the new meeting to replace it
#### Runtime of Optimal Solution
---
Links :: [[#Example Code]] [[Computer Science]] [[Amazon Leetcode Problem]]
Reference ::
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-12-02 12:17
