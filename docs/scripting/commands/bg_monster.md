# `bg_monster()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
bg_monster(<BG Team ID>, "<mapname>", <x>, <y>, "<name>", <mob id>{, "<event>"});
```

## Description

This command is part of the Battleground System and works nearly the same as [`monster()`](monster.md), but the spawned monster will fight for the selected BG team and `bg_monster()` returns the GID of the spawned monster. The GID can be useful for commands like [`bg_monster_set_team()`](bg_monster_set_team.md).
