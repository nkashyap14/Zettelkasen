# Formats for encoding data

## General Details

- Programs work with data in 2 representations:
	- In memory:
		- Data kept in objects, structs, lists, arrays, hash tables, trees etc
		- Optimized for efficient access and manipulation by [[CPU]]
	- Written data to a file or sent over the network
		- Encoded as some kind of self contained sequence of bytes
- Requires translation between 2 representations
	- [[Encoding]]
	- [[Decoding]]
- Bad idea to use languages built in encoding for anything other than transient purposes
	- Couples to the specific language
		- Python to pickle
		- Java to io.serializable
			- Poor performance
	- Versioning data becomes afterthought
	- Not very efficient
- Standardized human readable (textual) encoding methods:
	- [[JSON]]
		- Popular due to built in support by web browsers + simplicity
		- No int and floating point distinguishing
	- [[XML]]
		- criticized as too verbose and unnecessarily complicated
		- No distinguishing between string of numbers and a number
- Binary Encoding:
	- Formats that are more compact or faster to parse
	- Binary formats for json/xml not widely adopted because they still require you to include the field names in the binary encoding which adds overhead
	- [[Apache Thrift]]
	- [[Protocol Buffers]]
		- Both require a schema for data that is encoded
		- Both have code generation tool that takes a schema definition and produces classes that implement the schema in various programming languages
		- Field tags/aliases to fields can't be changed. Can add new fields to the schema provided that each new field is given a new tag number
			- old code tries to read new data it can simply ignore fields with new tag numbers
		- Can't add a new field and make it required
			- Check would fail if new code reads data written by old code
		- Can only remove optional fields
		- Can never use the same tag number again
	- [[Apache Avro]]
- Benefits of binary encoding:
	- More compact than varrious binary json variants since they can omit field names
	- Schema is a valuable form of documentation + can be sure it is up to date as it is used for decoding
	- Keeping a database of schemas allows you to check forward and backward compatability of schema changes

## Subtopics

## Terms defined

- [[Backward Compatability]]
- [[Forward Compatability]]


Type :: #topic
Links :: [[Computer Science]]
Book :: [[Designing Data Intensive Applications]]
Date ::  2024-11-10 07:41