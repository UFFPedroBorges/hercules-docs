# `getequipid()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getequipid(<equipment slot>);
```

## Description

This function returns the item ID of the item equipped in the equipment slot specified on the invoking character. If nothing is equipped on the specified slot, command returns -1.

| Equipment Slots: |   |
| ---------------- | - |
| `EQI_HEAD_TOP` (1) | Upper head gear |
| `EQI_ARMOR` (2) | Armor (Where you keep your Jackets and Robes) |
| `EQI_HAND_L` (3) | What is in your Left hand. |
| `EQI_HAND_R` (4) | What is in your Right hand. |
| `EQI_GARMENT` (5) | The garment slot (Mufflers, Hoods, Manteaus) |
| `EQI_SHOES` (6) | What foot gear the player has on. |
| `EQI_ACC_L` (7) | Accessory 1. |
| `EQI_ACC_R` (8) | Accessory 2. |
| `EQI_HEAD_MID` (9) | Middle Headgear (masks and glasses) |
| `EQI_HEAD_LOW` (10) | Lower Headgear (beards, some masks) |
| `EQI_COSTUME_HEAD_LOW` (11) | Lower Costume Headgear |
| `EQI_COSTUME_HEAD_MID` (12) | Middle Costume Headgear |
| `EQI_COSTUME_HEAD_TOP` (13) | Upper Costume Headgear |
| `EQI_COSTUME_GARMENT` (14) | Costume Garment |
| `EQI_SHADOW_ARMOR` (15) | Shadow Armor |
| `EQI_SHADOW_WEAPON` (16) | Shadow Weapon |
| `EQI_SHADOW_SHIELD` (17) | Shadow Shield |
| `EQI_SHADOW_SHOES` (18) | Shadow Shoes |
| `EQI_SHADOW_ACC_R` (19) | Shadow Accessory 2 |
| `EQI_SHADOW_ACC_L` (20) | Shadow Accessory 1 |

## Examples

```c
mes("You should wear a cotton shirt to continue the quest");
if (getequipid(EQI_ARMOR) == Cotton_Shirt)
	goto(L_WearingShirt);
mes("Come Back when you have Cotton Shirt Equipped.");
close();
```

## See Also

- [`getequipname()`](getequipname.md)
