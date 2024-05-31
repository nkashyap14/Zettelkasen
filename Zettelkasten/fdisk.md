# fdisk

- Command line utility ([[Bash]]) that provides disk partitioning functions
- fdisk -l
	- lists all available partitions on the disk
	- Used to help identify new disks
- fdisk /dev/sdc
	- Opens the fdisk utility for the specified disk
	- Enter a session where we can manage [[partition(file system)|partitions]]
- Fdisk utilizes a [[Master Boot Record|MBR]] partitioning scheme
	- Limit of 4 primary partitions of max size 2 TB due to 32 bit addressing
---
Links :: [[Computer Science]] [[Linux]] [[File System]] [[Utility]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-23 10:32
