# `setwall()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
setwall("<map name>", <x>, <y>, <size>, <dir>, <shootable>, "<wallname>");
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
Creates an invisible wall, an array of "setcell" starting from x,y and doing a
line of the given size in the given direction. The difference with setcell is
this one updates the client part too, to avoid the glitch problem. Directions are the 
same as NPC sprite facing directions: 0=north, 1=northwest, 2=west, etc.

==Examples==
 -	script	setwall	-1,{
 	[[end]];
 [[OnInit]]:
 	setwall "prontera",64,102,4,2,0,"PrtWall";
 }
----

==See Also==
* [[Delwall]]
