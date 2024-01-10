# `getequipname()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getequipname(<equipment slot>);
```

## Description

Returns the jname of the item equipped in the specified equipment slot on the invoking character, or an empty string ("") if nothing is equipped in that position.

Does the same thing as [`getitemname`](getitemname.md)`(`[`getequipid`](getequipid.md)`(<slot>))`. Useful for an NPC to state what your are wearing, or maybe saving as a string variable.

See [`getequipid()`](getequipid.md) for a full list of valid equipment slots.

## Examples

```c
if (getequipname(EQI_HAND_L) == "") {
	mes("You are wearing nothing on Left Hand");
} else {
	mes("You are wearing " + getequipname(EQI_HAND_L) + " on Left Hand");
}
```

## See Also

- [`getequipid()`](getequipid.md)
- [`getitemname()`](getitemname.md)
