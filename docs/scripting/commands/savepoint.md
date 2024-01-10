# `savepoint()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
savepoint(<"map name">, <x>, <y>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
This command stores the location, where the [[RID#Usage|invoking character]] will be warped to, when re-spawning after death, getting warped out of a [[WoE]] castle or using skill Teleport Lv2. Map flags, which would otherwise prohibit setting a save point or warping to a map, are ignored by this script command.

==Examples==
 [[mes]] "[Kafra Employee]";
 mes "Your Respawn Point";
 mes "has been saved here";
 mes "in the city of Payon.";
 mes "Thank you for using";
 mes "the Kafra Services.";
 savepoint "payon", 257, 242;
 [[close2]];
 [[cutin]] "", 255;
 [[end]];
