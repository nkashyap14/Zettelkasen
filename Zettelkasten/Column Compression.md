# Column Compression

- Used to further reduce demands on disk throughput 
- Done by compressing [[Column-Oriented Storage]] data which happens to lend itself well to compression
- Types of techniques
	- [[Bitmap Encoding]]
		- Can take a column with n distinct values and turn it into n separate bitmaps
		- One bit map for each distinct value with one bit for each row, 1 if row has the value 0 if not
		- If n is very small bitmaps can be stored with 1 bit per row, but if n is bigger there will be large numbers of zeros in th bit map which we can do further encoding on
	- Run length encoding:
		- Encode number of 1's, 0's 
			- Ex: 9,1,5:
				- 9 0's 1 1 and 5 0's again
- Allows for more efficient use of CPU cycles as it reduces function calls and conditions for each record process by operating on a chunk of compressed column data
---
Links :: [[Computer Science]] [[Database]]
Reference :: [[Designing Data Intensive Applications]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-27 13:16
