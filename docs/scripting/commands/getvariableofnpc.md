# `getvariableofnpc()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getvariableofnpc(<variable>, <"npc name">);
```

## Description

This function retrieves a variable reference to a [permanent npc variable](../Variables.md#NPC_Variables) in an another NPC script. Note, that the return value behaves like a variable, not like a value, which means, the return value of this function can be used in other script commands, which expect a variable as parameter.

## Examples

```c
mes("The current name of my co-worker is " + getvariableofnpc(.npcname$, "Site Co-Worker"));
```

!!! info
	Prints the value of the variable `.npcname$` as if it was used inside the NPC "Site Co-Worker".

```c
mes("Let's give him an another name...");
set(getvariableofnpc(.npcname$, "Site Co-Worker"), "Sleeping Tom");
```

!!! info
	Sets the variable `.npcname$` of the NPC "Site Co-Worker" to "Sleeping Tom".

```c
set(.mynpcnamecopy$, getvariableofnpc(.npcname$, "Site Co-Worker"));
set(.mynpcnamecopy$, "Sleeping Tom");
```

!!! info
	Will change the variable `.mynpcnamecopy$` to "Sleeping Tom", but keep the variable `.npcname$` of NPC "Site Co-Worker" unaffected, because the first call to set copies the value of `.npcname$` to `.mynpcnamecopy$`, rather than the reference.
