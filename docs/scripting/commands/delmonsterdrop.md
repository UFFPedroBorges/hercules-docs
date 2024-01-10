# `delmonsterdrop()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
delmonsterdrop(<mob id or name>, <item id>);
```

## Description

This command will temporarily remove a drop from an existing monster.

Both the monster and the item must be valid.

Return value will be 1 in case of success (the item was removed), and 0
otherwise (the monster didn't have the specified item in its drop list).

## Example

```c
// Remove Jellopy (909) from the Poring's (1002) drops
delmonsterdrop(1002, 909);
```

## See Also

- [`addmonsterdrop()`](addmonsterdrop.md)
