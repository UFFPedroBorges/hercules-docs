# `attachnpctimer()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
attachnpctimer({"Character Name"});
```

## Description

`attachnpctimer()` allows you to attach a player to a NPC later on. This can only be done to the NPC Timer that is in the same NPC as where this command is used. To attach a player, you will simply have to give his account id or RID (or UID/GID in some devs words) as a parameter. The [`setnpctimer()`](setnpctimer.md) command will explicitly set the timer to a given tick. [`getnpctimer()`](getnpctimer.md) provides timer information. Its parameter defines what type

## Examples

```c
attachnpctimer(getcharid(3)); // Attaches current player to the NPC Timer.
attachnpctimer(2000000); // Attaches the player with account id 2000000 to the NPC Timer, if he is online.
```
