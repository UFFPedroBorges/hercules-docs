# `doevent()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
doevent(<"event label">);
```

## Description

This command invokes a script at given event label in an another [NPC](../NPC.md). The parameter `event label` has the form `"NpcName::OnLabel"` and unlike in [`donpcevent()`](donpcevent.md), it cannot target multiple NPCs by omitting the NPC name. It works much like a [`goto()`](goto.md) command into an another NPC. If there was an [RID](../RID.md) attached to the invoking script, it will be attached to the invoked script as well.

This command is not used very much, because it is more limited than [`donpcevent()`](donpcevent.md) and passing RID to another script is usually not required.

## Examples

```c
prontera,150,150,3	script	NPC1	53,{
	mes("Let's see, no one look, so let as deal.");
	next();
	doevent("NPC2::OnTalk");
	mes("Damn, we were spotted, so no trade for you.");
	close();
}

prontera,152,150,5	script	NPC2	53,{
	// ...
OnTalk:
	npctalk("Everyone look, " + strcharinfo(0) + " tries to buy forbidden goods!");
	end;
}
```

!!! info
	Every time a player talks to NPC1, NPC2 will scream into it's area, what the player is about to do. Since `doevent()` passes the RID to NPC2, it can use [`strcharinfo()`](strcharinfo.md) to retrieve the player's name.
