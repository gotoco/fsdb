# Extensions to FSDB

Goal of this project is to provide useful extension to the NetBSD FSDB  

## Abstract: Why we need this?
Filesystems are one of the most important parts of general-purpose Operating System. 
FS is a place responsible for storing user data, where any software bug can potentially cause damage and data corruption. 
From a users perspective, stored data needs to be safe and bulletproof.    
Any data corruption may imminently cause users to switch to other software stacks, and never touch again the project that caused any data loss.
To provide such level of the quality Filesystems needs tools for testing, but also debugging any problems to efficiently solve them.  

**FSDB** is Filesystem debugger and is designed to be a tool that developers and system administrators can use to narrow down and find the root cause of any FileSystem related problems.
Currently, FSDB does not provide significant value in root causing FS issues, just a limited view on the correct FS structures.
This project aims to fill the gap and provide missing functionalities to make debugging Filesystems easier and similar to the enterprise tools.  

## Current support:
 - Currently only ufs1, uf2 supported (inline with head fsdb support)

## Functionalities

### Formatted Parser 
Additional `pf` command for fsdb that allows to investigate in-core (on-disk) structures.

#### inode	<number=>	<format=[ufs1|ufs2]>

		Print inode with all fields, if no other parameters provided printing current inode.
		Number: describe inode number to be printed
		Format: describe particular impelmentation, if not specified the fsck detection used.

#### superblock 	<location=> 	<format=[ufs1|ufs2]>

		Print superblock with all fields, 
		Location is optional parameter and specify the potantial copy of sb on the disk
		Format specify the File System specific layout of the structure.

#### parse 	<address=>	[inode|superblock|cylinder_group]

		Parse specified Disk address to the structure, can be provided in hex (with 0x) or decimal format.
		Currently supported structures: inode, super block, cylinder group.


### Formatted Editor
This functionality is currently under development. Allows user in convinient way to manipulate on disk structures.
