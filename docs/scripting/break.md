# `break`

## Syntax

```c
break;
```

## Description

This command lets you break out of a [loop](loops.md) or a [switch](switch.md) block. After the `break;` command has been issued, the script will continue where needed.

## Examples

```c
switch (getequipweaponlv(EQI_HAND_L)) {
case 0:
	mes("You are holding a shield, so it doesnt have a level");
	break;
case 1:
case 2:
case 3:
case 4:
	mes("You are holding a lvl "+ getequipweaponlv(EQI_HAND_L) +" weapon");
	break;
case 5:
	mes("You are holding a lvl 5 weapon, hm, must be a custom design");
	break;
}
close();
```

## See Also

- [Loops - break and continue](loops.md#Break_and_Continue)
