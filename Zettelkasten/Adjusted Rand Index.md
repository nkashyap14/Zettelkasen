# Adjusted Rand Index

## Definition:

- [[Regular Rand Index]] gives a measurement of similarity between true clustering assignments (true labels) and the predicted clustering assignments (predicted labels)
- Adjusted Rand Index (ARI) is a corrected-for-chance version of the regular one
	- Score is adjusted so random clustering assignments will not have a good score
	- Ranges from -1 to 1
		- Negative = bad labeling
		- Random labeling = score near 0
		- Perfect labeling score of near 1
- [[Adjusted Rand Index sklearn]]
- Used when true clusters are large and approximately equally sized
- When true clusters are unablanced in size and there are small clusters use [[Adjusted Mutual Information (AMI)]]
---
Links ::  [[Computer Science]] [[Machine Learning]] [[Clustering]] [[Metric]]
Reference ::  [[Educative]]
Type :: #definition
Discussion ::
Date :: 2024-09-12 12:15