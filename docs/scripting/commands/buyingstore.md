# `buyingstore()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
buyingstore(<slots>);
```

## Description

Invokes buying store preparation window like the skill 'Open Buying Store', without the item requirement. Amount of slots is limited by the server to a maximum of 5 slots by default. Works with clients version `2010-04-27aRagexeRE` or newer.

## Examples

```c
buyingstore(4);
```

!!! info
	Gives the player opportunity to buy 4 different kinds of items.

## See Also

- [`searchstores()`](searchstores.md)
