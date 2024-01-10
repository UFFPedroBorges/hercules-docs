# `awake()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
awake("NPC Name");
```

## Description

These commands are used to control the pause of a NPC.

Commands [`sleep()`](sleep.md) and [`sleep2()`](sleep2.md) will pause the script for the given amount of milliseconds.

`awake()` is used to cancel a sleep. When `awake()` is called on a NPC it will run as
if the sleep timer ran out, and thus making the script continue. [`sleep()`](sleep.md) and [`sleep2()`](sleep2.md) basically do the same, but the main difference is that [`sleep()`](sleep.md) will not keep the [RID](../RID.md), while [`sleep2()`](sleep2.md) does.

## Examples

```c
sleep(10000); // pause the script for 10 seconds and ditch the RID (so no player is attached anymore)
sleep2(5000); //pause the script for 5 seconds, and continue with the RID attached.
awake("NPC"); //Cancels any running sleep timers on the NPC 'NPC'.
```
