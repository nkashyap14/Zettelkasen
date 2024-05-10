# Data Formats

## Summary

## Subtopics
- [[JSON]]
- [[XML]]
- [[CSV]]
- [[Binary Format]]
## Details

- Programs work with data in 2 different representations:
	- In memory
		- Kept in objects, structs, lists, arrays, hash tables, trees etc
		- Optimized for efficient access and manipulation by the CPU
	- Writing data to a file, sending data over a network
		- requires encoding
		- A pointer wouldn't make sense to any other process so instead we encode a sequence of bytes representation that looks very different to ones used in memory
		- Requires translation between two representations
			- [[encoding]]
			- [[decoding]]
- Generally a bad idea to use a language's built in encoding for anything other than transient purposes
	- Efficiency is an afterthought, java.io.Serializable is very inefficient
	- Get tightly coupled to the language
- [[XML]] may be preferable to [[JSON]] when the data contains complex structures, such as those found in books, articles, and other datasets. XML can represent documents containing various data structures because it represents data in a tree-like format, making it easier to manage different data structures in an organized manner.
- Recommendations:
	- [[JSON]] is ideal for small groups of systems, especially those developed in Javascript
## Conclusion


Type :: #topic
Links :: [[Computer Science]] [[API]]
Creator ::
Date ::  2024-04-03 17:09