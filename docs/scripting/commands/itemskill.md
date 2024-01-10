# `itemskill()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
itemskill(<skill id>, <skill level>);
```

```c
itemskill(<"skill name">, <skill level>);
```

## Description

This command meant for item scripts to replicate single-use skills in usable items. It will not work properly, if there is a visible dialog window or menu. If the skill is self or auto-targeting, it will be used immediately otherwise a target cursor is shown.

## Examples

```
605,Anodyne,Anodyne,11,2000,0,100,,,,,10477567,2,,,,,{ itemskill(8, 1); },{}
```

!!! info
	When Anodyne is used, it will cast Endure (8), Level 1, as if the actual skill has been used from skill tree.
