# `getequipweaponlv()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getequipweaponlv(<equipment slot>);
```

## Description

This function returns the weapon level for the weapon equipped in the specified equipment slot on the invoking character. For a list of equipment slots see [`getequipid()`](getequipid.md).

Only `EQI_HAND_L` and `EQI_HAND_R` normally make sense, since only weapons have a weapon level. You can, however, probably, use this field for other equippable custom items as a flag or something. If no item is equipped in this slot, or if it doesn't have a weapon level according to the database, 0 will be returned.

## Examples

```c
switch (getequipweaponlv(EQI_HAND_R)) {
case 1:
case 2:
case 3:
case 4:
	mes("You are holding a lvl " + getequipweaponlv(EQI_HAND_R) + " weapon");
	break;
case 5:	// Level 5 Doesn't Exist in Server, You have to edit the source.
	mes("You are holding a lvl 5 weapon, hm, must be a custom design");
	break;
default:
	mes("Seems you don't have a weapon on");
	break;
}
```

Or for the left hand, cause it can hold a weapon or a shield:

```c
	if(getequipid(EQI_HAND_R) == 0)
		goto(L_NothingEquiped);
	switch (getequipweaponlv(EQI_HAND_L)) {
	case 0:
		mes("You are holding a shield, so it doesnt have a level");
		break;
	case 1:
	case 2:
	case 3:
	case 4:
		mes("You are holding a lvl " + getequipweaponlv(EQI_HAND_L) + " weapon");
		break;
	case 5:
		mes("You are holding a lvl 5 weapon, hm, must be a custom design");
		break;
	}
	close();

L_NothingEquiped:
	mes("Seems you have nothing equipped");
	close();
```
