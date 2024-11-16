# Hot Spot Remedy

- One solution to stop the skews that result from hot spots is by adding a random number to the beginning or the end of the key
	- I.e. a 2 digit random number at beginning can lead to 100 different keys
	- Affects reads however as there needs to be a way to read the data from all the key
	- Only makes sense for a small number of hot keys
	- Keys with [[low write]] would only incur unnecessary overhead
---
Links :: [[Computer Science]] [[System Design]] [[hash functions]] 
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-06-14 12:30
