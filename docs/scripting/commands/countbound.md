# `countbound()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
countbound({<bound type>});
```

## Description

This function will return the number of bounded items in the character's
inventory, and sets an array `@bound_items[]` containing all item IDs of the
counted items. If a bound type is specified, only those items will be counted.

For a list of bound types see [`getitembound()`](getitembound.md).

## Example

```c
mes("You currently have " + countbound() + " bounded items.");
next();
mes("The list of bounded items include:");
for (set .@i, 0; .@i < getarraysize(@bound_items); set(.@i, .@i + 1))
	mes(getitemname(@bound_items[.@i]));
close();
```

## See Also

- [`getitembound()`](getitembound.md)
- [`getitembound2()`](getitembound2.md)
