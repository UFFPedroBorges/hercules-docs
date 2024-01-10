# `getequiprefinerycnd()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getequiprefinerycnt(<equipment slot>);
```

## Description

This returns the current refine level for a particular item in the specified equipment slot. 


### Slot Values

| Value | Type | Constant Defined |
| ----- | ---- | ---------------- |
| 1 | Upper Headgear | EQI_HEAD_TOP |
| 2 | Armor | EQI_ARMOR |
| 3 | Left Hand | EQI_HAND_L |
| 4 | Right Hand | EQI_HAND_R |
| 5 | Garment | EQI_GARMENT |
| 6 | Foot Gear | EQI_SHOES |
| 7 | Accessory 1 | EQI_ACC_L |
| 8 | Accessory 2 | EQI_ACC_R |
| 9 | Middle Headgear | EQI_HEAD_MID |
| 10 | Lower Headgear | EQI_HEAD_LOW |

## Example

```c
	if (getequiprefinerycnt(EQI_HEAD_TOP) < 10)
		goto L_Refine_HeadGear;
	mes("Sorry, it's not possible to refine hats better than +10");
	close();
L_Refine_HeadGear:
	mes("I will now upgrade your " + getequipname(EQI_HEAD_TOP));
```

!!! info
    This can be used to check if you have reached a maximum refine value, default for this is +10:
