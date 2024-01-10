# `getguildmaster()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getguildmaster(<guild id>);
```

## Description

This function return the name of the master of the guild which has the specified ID number. If there is no such guild, "null" will be returned.

```c
// Would return the guild master of guild 10007, whatever that might be.
mes(getguildmaster(10007) + " runs " + getguildname(10007));
```

Can be used to check if the character is the guild master of the specified guild.

## Example

Maybe you want to make a room only guild masters can enter:

```c
	set(@GID, getcharid(2));
	if (@GID == 0)
		goto(L_NoGuild);
	if (strcharinfo(0) == getguildmaster(@GID))
		goto(L_GuildMaster);
	mes("Sorry you don't own the guild you are in");
	close();
L_NoGuild:
	mes("Sorry you are not in a guild");
	close();
L_GuildMaster:
	mes("Welcome guild master of " + getguildname(@GID));
	close();
```

## See Also

- [`getguildmasterid()`](getguildmasterid.md)
