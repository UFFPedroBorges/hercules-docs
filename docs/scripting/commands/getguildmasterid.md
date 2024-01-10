# `getguildmasterid()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getguildmasterid(<guild id>);
```

## Description

This function will return the character ID number of the guild master of the guild specified by the ID. 0 if the character is not a guild master of any guild.

## Examples

```c
prontera,155,180,5	script	guildmasterID	89,{
	if (getcharid(2) != 0) {
		mes(getguildmasterid(getcharid(2)) + " it's  your guildmaster id");
		close();
	}
}
```

## See Also

- [`getguildmaster()`](getguildmaster.md)
