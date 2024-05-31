# Apache Avro

- Binary encoding format developed by hadoop
- Uses a value-only data encoding style and relies on schema version defined in the data reader for field identification
- Has two main schema languages
	- [[Avro IDL]] for human editing
	- [[JSON]] based that is more easily machine readable
- Handles schema transitions efficiently
- Encoding consists of values concatenated together
	- String is a length prefix followed by [[UTF-8]] [[byte|bytes]]
	- Means that the binary data transmitted over the wire can only be decoded if the code reading the data is using the exact same schema as the code that wrote the data
- [[Writer's Schema]]
- [[Reader's Schema]]
- Readers schema and Writers schema don't have to be the same they just have to be compatible
- May only add or remove fields that have a default value
- More friendly to dynamically generated schemas compared to something like [[Protocol Buffers]] or [[Apache Thrift]]
---
Links :: [[Computer Science]] [[Binary Format]] [[encoding]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-03 17:17
