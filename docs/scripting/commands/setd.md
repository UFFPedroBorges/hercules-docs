# `setd()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
setd("<variable name>", <value>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
Works almost identical as [[set]], just that the variable name is identified as a string, 
thus can be constructed dynamically.

This command is equivalent to:
 set [[getd]]("variable name"),<value>;

==Examples==
 set .@mob_id, 1002;
 setd ".prize_" + .@mob_id, 911; // sets the value of .prize_1002 to 911
