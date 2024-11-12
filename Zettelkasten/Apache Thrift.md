# Apache Thrift

- [[Developed at Facebook]]
- Thrift Interface Definition Language used to define schemas
- Has 2 different binary encoding formats:
	- BinaryProtocol
		- no field names in encoding
		- Contains field tags which are the numbers in the schema definition.
			- Act as aliases for field
	- CompactProtocol
		- Semantically equivalent to binary protocol
		- Does this by packing field type and tag number into a single byte
		- Uses variable length integers
			- Ie for number 1337 encodes it in 2 bytes instead of 8 (64 bit) by using top bit of each byte to indiciate whether more bytes are still to come
---
Links :: [[Computer Science]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-10 07:51
