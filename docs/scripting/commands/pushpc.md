# `pushpc()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
pushpc(<direction>, <cells>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

== Description ==
This command will push the [[RID|currently attached player]] to given direction by given amount of square cells. Direction is the same as used when declaring NPCs, and can be specified by using one of the DIR_* constants [`db/const.txt`](https://github.com/HerculesWS/Hercules/blob/stable/db/const.txt)

The knock-back is not restricted by items or map flags, only obstacles are taken into account. If there is not enough space to perform the push (e.g. due to a wall), the character is pushed only up to the obstacle.

== Examples ==
 // pushes the character 5 cells in 3 o'clock direction from it's current position.
 pushpc DIR_EAST, 5;
