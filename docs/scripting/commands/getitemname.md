# `getitemname()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getitemname(<item id>);
```

## Description

Retrieves the display name for an item given by ID from the 3rd column in the item database. If there is no such item, "null" is returned as name.

## Examples

```c
mes("See? Whenever you find some " + getitemname(512) + ", bring it to me.");
```

!!! note
	Output will be: "See? Whenever you find some Apple, bring it to me."

```c
mes("See? Whenever you find some " + getitemname(12) + ", bring it to me.");
```

!!! note
	Since there is usually no item with ID 12, so output will be: "See? Whenever you find some null, bring it to me."
