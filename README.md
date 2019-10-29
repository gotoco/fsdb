# Extensions to FSDB

Goal of this project is to provide useful extension to the NetBSD FSDB  

## Abstract: Why we need this?

## Functionalities

### Formatted Parser 
Additional `pf` command for fsdb that allows to investigate in-core (on-disk) structures.

#### inode	<number=>	<format=>

		Print inode with all fields, if no other parameters provided printing current inode.
		Number: describe inode number to be printed
		Format: describe particular impelmentation, if not specified  

#### superblock 	<location=> 	<format=>

		Print superblock with all fields, 
		Location is optional parameter and specify the potantial copy of sb on the disk
		Format specify the File System specific layout of the structure.

#### parse 	<address=>	[inode|superblock|cylinder_group]

		Parse specified Disk address to the structure, can be provided in hex (with 0x) or decimal format.
		Currently supported structures: inode, super block, cylinder group.


### Formatted Editor
This functionality is currently under development. Allows user in convinient way to manipulate on disk structures.
