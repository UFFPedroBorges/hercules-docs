# `getinventorylist()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getinventorylist();
```

## Description

This command sets a bunch of arrays with a complete list of whatever the invoking character has in its inventory, including all the data needed to recreate these items perfectly if they are destroyed. Here's what you get:

- `@inventorylist_id[]` - array of item ids.
- `@inventorylist_amount[]` - their corresponding item amounts.
- `@inventorylist_equip[]` - whether the item is equipped or not.
- `@inventorylist_refine[]` - for how much it is refined.
- `@inventorylist_identify[]` - whether it is identified.
- `@inventorylist_attribute[]` - whether it is broken.
- `@inventorylist_card1[]`, `@inventorylist_card2[]`, `@inventorylist_card3[]`, `@inventorylist_card4[]` - These four arrays contain card data for the items. These data slots are also used to store names inscribed on the items, so you can explicitly check if the character owns an item made by a specific craftsman.
- `@inventorylist_expire[]` - expire time (Unix time stamp). 0 means never expires.
- `@inventorylist_count` - the number of items in these lists.
- `@inventorylist_bound` - whether it is an account bounded item or not.

This could be handy to save/restore a character's inventory, since no other command returns such a complete set of data, and could also be the only way to correctly handle an NPC trader for carded and named items who could resell them - since NPC objects cannot own items, so they have to store item data in variables and recreate the items.

Notice that the variables this command generates are all temporary, attached to the character, and integer.

!!! remark
	Be sure to use `@inventorylist_count` to go through these arrays, and not [`getarraysize()`](getarraysize.md), because the arrays are not automatically cleared between runs of `getinventorylist()`.

## Example

!!! note
	Visit `npc/custom.itembind.txt`
