# fstab

- Stands for [[File System|file system]] table
- Configuration file located in [[etc]] folder that contains information about the various file system and storage devices available on the system
- Is used by the mount command to determine which options to use when mounting a specified file system or storage device
- Contains 6 fields separated by white spaces
	- Device: UUID or device file
	- Mount Point
	- File system type: [[ext4]], [[xfs]], [[ntfs]]
	- Options: Mount options that control the way the file system is mounted and behaves 
	- Dump: A field used by the dump utility to determine if the file system needs to be backed up 
	- Pass: Controls the order in which [[fsck]] checks the file systems at boottime
---
Links :: [[Computer Science]] [[Linux]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-04 15:09
