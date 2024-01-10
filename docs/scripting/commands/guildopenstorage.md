# `guildopenstorage()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
guildopenstorage();
```

## Description

This function works the same as [`openstorage()`](openstorage.md) but will open a guild storage window instead for the guild storage of the guild the invoking character belongs to. This is a function because it returns a value - 0 if the guild storage was opened successfully and 1 if it wasn't. (Notice, it's a ZERO upon success.) Since guild storage is only accessible to one character at one time, it may fail if another character is accessing the guild storage at the same time.

This will also fail and return 2 if the character does not belong to any guild.

## Example

!!! example
	from `npc/kafras/functions_kafras.txt`

```c
if (guildopenstorage() == 1) {
	mes("[Kafra Employee]");
	mes("I'm sorry but another guild member is using the guild storage");
	mes("right now.  Please wait until that person is finished.");
	close2();
	cutin("", 255);
	end;
}
```
