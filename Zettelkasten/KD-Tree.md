# KD-Tree

## Summary

- Stands for K-Dimensional Tree
- Space partitioning data structure that organizes points in k-dimensional space
- Used for efficient spatial queries
	- Useful for finding nearest neighbors to a point
	- Finding all points within a certain radius of a point
- The KD Tree organizes points by recursively dividing spaces into half-spaces
- Allows for eliminating large portions of the search space when querying which makes radius searches much faster (typically O(log n))
	- Better than a brute force calculation of the distance of each point from the centroid and then checking if the radius would be in the span as that would be an O(n) operation

## Subtopics

## Details

- Used it with my WPA model to extract clusters of kill locations across counter strike maps
## Conclusion


Type :: #topic
Links :: [[Computer Science]] [[Machine Learning]]
Creator ::
Date ::  2025-01-05 14:42