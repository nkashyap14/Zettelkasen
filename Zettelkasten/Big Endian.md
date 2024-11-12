# Big Endian

- Is a storing schema for how computers stores a sequence of bytes in memory
- In the case of Big Endian the most significant byte or the "big end" is stored at the lowest memory address. Also known as network byte order
- In the case of my [[golang consistent hashing implementation]] I am taking the first four bytes of a hash which is stored in big endian format. So because the slice grows in memory and the initial indexes are at the lowest memory addresses this means the most significant bytes are at the first 4 and that is what I am taking of the hash function

---
Links :: [[Computer Science]] [[memory]] [[Byte]] [[Little Endian]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-11-03 08:49
