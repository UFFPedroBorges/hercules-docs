# `setnpcdisplay()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
setnpcdisplay("<npc name>", "<display name>"{, <class id>{, <size>}});
```

```c
setnpcdisplay("<npc name>", <class id>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

== Description ==
Changes the display name and/or display class of the target NPC.

Returns 0 is successful, 1 if the NPC does not exist.

Size is 0 = normal 1 = small 2 = big.

== Examples ==
 setnpcdisplay("Test","Test NPC","1002","2"); //The NPC 'Test' will receive the name 'Test NPC', the disguise of a Poring, and be large like a Mastering.
 setnpcdisplay("Test","Test NPC","1002"); //The NPC 'Test' will receive the name 'Test NPC' and the disguise of a Poring.
 setnpcdisplay("Test","Test NPC"); //The NPC 'Test' will receive the name 'Test NPC'.
 setnpcdisplay("Test",1002); //The NPC 'Test' will receive the disguise of a Poring.
