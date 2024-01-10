# `rand()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
rand(<number>{, <number>});
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
This function returns a number, randomly positioned between 0 and the number you 
specify (if you only specify one) and the two numbers you specify if you give it 
two.
==Examples==
 	[[set]] .number,rand(10);    // Gives Output between 0 to 10 (0,1,2,3,4,5,6,7,8,9,10)
 	[[set]] .number,rand(2,10); // Gives Output between 2 to 10 (2,3,4,5,6,7,8,9,10)
