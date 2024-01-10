# `OnTouch:` / `OnTouchNPC:` / `OnUnTouch:`

## Syntax

```c

Map,X,Y,facing	script	NPCName	ID,triggerX,triggerY,

OnTouch:
OnTouchNPC:
OnUnTouch:
```

## Description

Defines an area that when walked into will trigger one of two event labels. If it is a Player, trigger `OnTouch:` label. If it is a monster, trigger `OnTouchNPC:` label.
The `OnUnTouch:` label works opposite way. This label trigger when a player leave the area.

### Calculating spawned area==

`[[File:Ontouch.jpg|thumbnail|A 7*7 area spawned by X:3 Y:3]]`

These triggers will define an area, centered on the NPC and spanning `triggerX` cells in every direction across X coordinate axis and `triggerY` cells in every direction across Y coordinate axis. Thus each one will have N*2 cells, where N is `triggerX` or `triggerY`, plus the one that the NPC is.

Unlike in arithmetics X and Y will also be taken into account when calculating the area that will trigger the NPC. There are four quadrants, each with `triggerX * triggerY` cells plus both axes.

!!! note
	Note that each coordinate is a **cell** and does not represent map coordinates!

```
4 * (x * y) + 2 * x + 2 * y + 1
```

A simple way to measure the area of any polygon that will be covered by `OnTouch` is `(triggerX * 2 + 1) * (triggerY * 2 + 1)`

!!! tip
	Trick: Using `end;` at the beginning of the script stops players from executing the script by clicking on the NPC, so they can only execute it if they walk into the specified area.

### Event labels

Two event labels are defined and each one handles one of two block types `BL_PC` or `BL_MOB` <i>id est</i> a player or a mob.

```c
OnTouch:
```

!!! info
	Handles player types (`BL_PC`)

```c
OnTouchNPC:
```

!!! info
	Handles mob types (BL_MOB)

If no trigger label is defined the code will execute from the beginning of the script, the same way that it would if someone clicked on the NPC.

### Example

```c
prontera,147,153,3	script	Mary	71,3,3,{
	end;
 
OnTouch:
	mes("[Mary]");
	mes("Have you seen my lamb?");
	close();
OnTouchNPC: // NO ONE IS ATTACHED!
	announce("A mob passed here", bc_blue | bc_all);
	end;
}
```

!!! note
	This script will spawn 3 cells in each direction plus a cell in the center.
	```
	(3 * 2 + 1) * (3 * 2 + 1) =
	7*7 = 49
	```
