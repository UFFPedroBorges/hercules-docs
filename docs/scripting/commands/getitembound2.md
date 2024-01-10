# `getitembound2()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getitembound2(<item id>, <amount>, <identify>, <refine>, <attribute>, <card1>, <card2>, <card3>, <card4>, <bound type>);
```

```c
getitembound2("<item name>", <amount>, <identify>, <refine>, <attribute>, <card1>, <card2>, <card3>, <card4>, <bound type>);
```

## Description

This command behaves identically to [`getitem2()`](getitem2.md), but the items created will be
bound to the target character as specified by the bound type. All items created
in this manner cannot be dropped, sold, vended, auctioned, or mailed, and in
some cases cannot be traded or stored.

For a list of bound types see [`getitembound()`](getitembound.md).

Default is 0 if not defined.

## Example

```c
getitembound2(1602, 1, 1, 2, 0, 4004, 4004, 4004, 4004, 1); // The person will receive 1 Account bounded "Rod with 4 Drops card" on it.
```

!!! example
	See example script in `npc/costum/itembind.txt`

## See Also

- [`getitembound()`](getitembound.md)
- [`countbound()`](countbound.md)
