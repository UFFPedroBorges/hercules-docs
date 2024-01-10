# `bg_monster_set_team()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
bg_monster_set_team(<GID>, <Battle Group>);
```

## Description
This command will change the allegiance if a monster in battlegrounds. [GID](../GID.md) can be set when spawning the monster via the [`bg_monster()`](bg_monster.md) command.

## Examples

```c
	end;

OnEnable:
	mapannounce("bat_b01", "A guardian has been summoned for Battle Group 2!", bc_map, 0xFFCE00);
	set($@Guardian, bg_monster($@BG_2, "bat_a01", 268, 204, "Guardian", 1949, "NPCNAME::OnMyMobDead"));
	initnpctimer();
	end;

OnTimer1000:
	stopnpctimer();
	mapannounce("bat_b01", "Erm, sorry about that! This monster was meant for Battle Group 1.", bc_map, 0xFFCE00);
	bg_monster_set_team($@Guardian, $@BG_1);
	end;
```
